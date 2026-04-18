---
titel: "Gefahrstoff-Abfrage bei Feuerwehr-Einsatz"
typ: skill
ebene:
saule: 2
land_ars:
kreis_ars:
verband_ars:
gemeinde_ars:
land:
kreis:
verband:
gemeinde:
endpoints:
  - brandmeister
extensions:
  - Feuerwehr
  - Gefahrgut
stand: 2026-04-18
beschreibung: "Handlungsanleitung für das LLM: Gefahrstoff-Identifikation (UN-Nummer, CAS, Stoffname), Profil-Lookup, Übergabe-Regeln (WGK, AwSV), Rechtstext-Zitat. Für brandmeister.ai — ab Phase G3 vollständig einsetzbar."
---

## Inhaltsverzeichnis
- un_nummer_bekannt [UN-Nummer als Einstieg → Stoff-Profil + Übergabe]
- stoffname_bekannt [Stoffname/CAS → Alias-Lookup → Profil]
- unbekannter_stoff [Eingrenzung über Eigenschaften, Aussehen, Kontext]
- uebergabe_ableiten [WGK + Stoffklasse → Übergabe-Regeln + Rechtsgrundlage]
- allgemein_einsatz [Allgemeines Vorgehen bei Gefahrgut-Einsatz]

### un_nummer_bekannt
Wenn der Nutzer eine UN-Nummer nennt (z.B. "UN 1203", "UN1203", "1203"):

1. UN-Nummer normalisieren: führende Nullen auffüllen auf 4 Stellen, "UN"-Präfix entfernen.
2. Stoff-Profil abrufen:
   `RAGSource_db_query({ db: "gefahrstoff", filter: { un_nr: "1203" } })`
3. Aus dem Treffer ablesen:
   - `rigoletto_wgk` (Wassergefährdungsklasse, 0–3)
   - `bam_klasse` (Gefahrgutklasse nach ADR, z.B. "3" für entzündbare Flüssigkeiten)
   - `niosh_psa` (persönliche Schutzausrüstung)
   - `erg_guide_nr` (ERG-Leitfaden-Nummer für Ersteinsatz)
   - `erg_abstand_klein_m`, `erg_abstand_gross_m` (Sicherheitsabstände)
4. Übergabe-Regeln ableiten (→ Abschnitt `uebergabe_ableiten`).
5. Bei mehreren Treffern (identische UN-Nr, verschiedene CAS): alle aufführen, Nutzer rückfragen.

**Hinweis (bis Phase G3):** RAGSource_db_query ist noch nicht mit Daten befüllt. Bis dahin: Stoff-Eigenschaften aus dem Trainingswissen des LLM nennen, ausdrücklich als "aus Trainingswissen, nicht aus verifizierter Einsatzdatenbank" kennzeichnen.

### stoffname_bekannt
Wenn der Nutzer einen Stoffnamen oder eine CAS-Nummer nennt:

1. Häufige Stoffe aus Trainingswissen:
   - "Benzin" → CAS 86290-81-5, UN 1203
   - "Diesel" → CAS 68476-34-6, UN 1202
   - "Heizöl EL" → CAS 68476-30-2, UN 1202
   - "Methanol" → CAS 67-56-1, UN 1230
   - "Ethanol" → CAS 64-17-5, UN 1170
   - "Ammoniak (wässrig)" → CAS 1336-21-6, UN 2672
2. Bei Unsicherheit oder unbekanntem Stoff: Alias-Lookup:
   `RAGSource_db_query({ db: "stoff_aliases", filter: { alias_norm_like: "benzin" } })`
   (alias_norm ist lowercase, Umlaute normalisiert: ä→ae, ö→oe, ü→ue, ß→ss)
3. Bei mehreren Treffern: alle CAS-Nummern aufführen, Nutzer nach Kontext fragen.
4. Mit gefundener CAS/UN-Nummer weiter wie `un_nummer_bekannt`.

### unbekannter_stoff
Wenn der Stoff nicht identifizierbar ist:

1. Rückfrage nach verfügbaren Informationen:
   - Kennzeichnung: orangefarbene Gefahrguttafel (ADR-Nummer/UN-Nummer)?
   - GHS-Piktogramme auf Behälter/Transportdokument?
   - Aussehen: Farbe, Konsistenz, Geruch?
   - Aggregatszustand: flüssig, gasförmig, fest?
   - Kontext: Tanklastzug, Betrieb, Labor, Baustelle?

2. Grob-Klassifizierung aus Piktogrammen (GHS):
   - Flamme → entzündbar (Klasse 3 oder 2.1)
   - Totenkopf → akut toxisch
   - Ausrufezeichen → gesundheitsschädlich/reizend
   - Ätzwirkung → korrosiv (Klasse 8)
   - Umwelt → wassergefährdend (WGK beachten)
   - Gas unter Druck → Druckgas (Klasse 2)
   - Explodierende Bombe → explosiv (Klasse 1)

3. Bis zur Identifikation: worst-case-Annahmen (WGK 3, toxisch) für Schutzmaßnahmen.
4. Empfehlung: Experten der Leitstelle oder BAM-Notfalltelefon (+49 30 18 455 5000) hinzuziehen.

### uebergabe_ableiten
Wenn WGK und Stoffklasse bekannt sind:

1. Übergabe-Regeln abfragen:
   `RAGSource_db_query({ db: "uebergabe_regeln", filter: { wgk: 2, stoffklasse: "3" } })`
2. Aus dem Treffer:
   - `kanalisation_freigabe`: "nein" / "nur nach UWB-Freigabe" / "ja"
   - `entsorgungspfad`: wie entsorgen?
   - `benachrichtigung_pflicht`: wen benachrichtigen? (JSON-Array)
   - `rechtsgrundlage_source_id` + `rechtsgrundlage_section_ref`: Rechtstext abrufen
3. Rechtstext zitieren:
   `RAGSource_get({ source: "D_AwSV", sections: ["§ 18"] })`
4. Ausgabe als GAMS-Block + Übergabe-Checkliste:
   - Gefahrstoff: [Bezeichnung, UN-Nr, CAS, WGK]
   - Absperr-/Sicherheitsbereich: [ERG-Abstände in Metern]
   - Maßnahmen: [Kanalisation absperren ja/nein, PSA, Erstmaßnahmen]
   - Entsorgung: [Pfad, AVV-Schlüssel]
   - Benachrichtigungen: [Behörden, Schwellenwerte]
   - Rechtsgrundlage: [Zitat aus AwSV/TRGS]

**Hinweis (bis Phase G4):** db_uebergabe_regeln ist noch nicht befüllt. Bis dahin: allgemeine Hinweise aus AwSV geben, ausdrücklich kennzeichnen.

### allgemein_einsatz
Allgemeine Grundsätze beim Gefahrgut-Einsatz (ohne spezifischen Stoff):

1. **Selbstschutz zuerst:** Sicherheitsabstand einhalten (mindestens 50 m bis zur Identifikation).
2. **Informationsbeschaffung:** Gefahrguttafel lesen (Gefahrnummer + UN-Nummer), Begleitpapiere, Sicherheitsdatenblatt anfordern.
3. **Leitstelle informieren:** Meldung mit UN-Nummer oder Gefahrnummer.
4. **Zugriffssteuerung:** Kanalisation und Gewässer schützen, Zündquellen eliminieren.
5. **Fachberatung:** BAM-Notfalltelefon (+49 30 18 455 5000), TUIS-System (Chemikalien-Industrie).
6. **Rechtsquellen nutzen:** FwDV 500 (Feuerwehr-Dienstvorschrift), AwSV (Gewässerschutz), TRGS 900 (Arbeitsplatzgrenzwerte).
   → `RAGSource_get({ source: "D_FwDV_500", sections: ["..."] })`
