# Quellen

Stand der Quellen: 2026-09-29 · Wortlisten `2026-09-29+sha256:e5a9a85281a8`

Jede Quelle ist auf genau eine Datei festgelegt: Adresse, Version und
SHA-256-Prüfsumme. Die Anbieter erzeugen ihre Dateien regelmäßig neu
(kaikki.org wöchentlich, OpenThesaurus täglich) und halten alte Stände nicht
vor; unter derselben Adresse liegt deshalb heute meist eine neuere Fassung mit
anderer Prüfsumme. Den Wiktionary-Stand stellt man notfalls mit wiktextract aus
den Wikimedia-Dumps der genannten Tage nach.

Alle Werke werden von ihren Urheberinnen und Urhebern ohne Gewähr
bereitgestellt; es gilt der Haftungsausschluss der jeweiligen Lizenz.

## In den Daten enthalten

### 1. Wiktionary, deutschsprachige Ausgabe

| | |
| --- | --- |
| Urheber | Autorinnen und Autoren des deutschsprachigen Wiktionary, <https://de.wiktionary.org>; wer an einem Eintrag mitgeschrieben hat, zeigt dessen Versionsgeschichte |
| Aufbereitung | kaikki.org mit wiktextract von Tatu Ylonen, <https://kaikki.org/dewiktionary/>, <https://github.com/tatuylonen/wiktextract> |
| Datei | `kaikki.org-dictionary-Deutsch.jsonl.gz`, 310 MB, nur Einträge der Sprache Deutsch |
| Adresse | <https://kaikki.org/dewiktionary/Deutsch/kaikki.org-dictionary-Deutsch.jsonl.gz> |
| Version | Dump des deutschsprachigen Wiktionary vom 2026-09-01, extrahiert am 2026-09-27 mit wiktextract `1a05e46` und wikitextprocessor `e3d6d4e` |
| SHA-256 | `038ff3f7f3faf3b1ee869ba506996bec4279a7849e7a3d0f0662ebbfd8a8fdd7` |
| Lizenz | CC BY-SA 4.0 und GFDL; wir nutzen CC BY-SA 4.0. Beleg: Lizenzhinweis am Fuß jeder Wiktionary-Seite, [Nutzungsbedingungen der Wikimedia Foundation](https://foundation.wikimedia.org/wiki/Policy:Terms_of_Use), [Hinweise von kaikki.org](https://kaikki.org/dewiktionary/) ¹ |
| Verwendet für | Rückgrat beider Listen: Stichwörter, Wortarten, alle Flexionsformen (Tabellen und die Einträge „Deklinierte Form“, „Konjugierte Form“, Partizipien, Steigerungsformen), Markierungen (vulgär, derb, abwertend, veraltet, mundartlich, regional …), Eigennamen, Abkürzungen, Kurzwörter und Anglizismen (aus der Herkunft), alte und Schweizer Schreibungen. Übernommen sind Wortformen, Grundformen und Wortarten, keine Bedeutungstexte. |

¹ Ältere Beiträge wurden unter CC BY-SA 3.0 eingestellt. Version 3.0 erlaubt,
Bearbeitungen unter einer späteren Version derselben Lizenz weiterzugeben
(Abschnitt 4 b); die abgeleiteten Daten stehen deshalb einheitlich unter
CC BY-SA 4.0.

### 2. Wiktionary, englischsprachige Ausgabe, deutsche Einträge

| | |
| --- | --- |
| Urheber | Autorinnen und Autoren des englischsprachigen Wiktionary, <https://en.wiktionary.org> |
| Aufbereitung | kaikki.org mit wiktextract von Tatu Ylonen, <https://kaikki.org/dictionary/German/> |
| Datei | `kaikki.org-dictionary-German.jsonl.gz`, 98 MB, nur Einträge der Sprache Deutsch |
| Adresse | <https://kaikki.org/dictionary/German/kaikki.org-dictionary-German.jsonl.gz> |
| Version | Dump des englischsprachigen Wiktionary vom 2026-09-02, extrahiert am 2026-09-25 mit wiktextract `1a05e46` |
| SHA-256 | `5759fef52efbb5c578301b0842c8e0217b9683b05ada69ec172870509a9b1828` |
| Lizenz | CC BY-SA 4.0 und GFDL; wir nutzen CC BY-SA 4.0. Beleg: [Wiktionary:Copyrights](https://en.wiktionary.org/wiki/Wiktionary:Copyrights) |
| Verwendet für | nur Hinweise, keine Wörter: Kurzwörter („Clipping of …“, *Reha*, *Kita*), die Markierungen *vulgar*, *offensive* und *slur* als zweite Meinung für die Filterliste, Eigennamen (ein Wort, das hier nur als Name vorkommt, wie *Bundeswehr* oder *Olympia*, ist kein Zielwort) |

### 3. wordfreq

| | |
| --- | --- |
| Urheber | Robyn Speer, <https://github.com/rspeer/wordfreq>; Urheberrechtshinweis des Pakets: „Copyright 2022 Robyn Speer“ |
| Paket | `wordfreq` 3.1.1 von PyPI, <https://pypi.org/project/wordfreq/3.1.1/> |
| Version | 3.1.1; der Datenstand ist um 2021 eingefroren, wordfreq wird nicht mehr aktualisiert |
| SHA-256 | Paket (Wheel) `4b1c6ecffc6198be3396d5cf871c4423ca71c907c231348d352dd54d62b97473`; Daten `wordfreq/data/large_de.msgpack.gz` `8ef04d3f4a28fb48d800d25fa80a96d90a5f80c8496c9a453f99f887c6ad3c12`, `wordfreq/data/large_en.msgpack.gz` `dffae8066b78dce0a6667cf5f58e567054f902674667090a7ac8a8a44628b05c` |
| Lizenz | Daten CC BY-SA 4.0, Code Apache 2.0; der Code ist nicht Teil dieser Daten |
| Enthaltene Quellen | Laut wordfreq-Dokumentation stammen die deutschen Häufigkeiten aus Wikipedia, Untertiteln (OPUS OpenSubtitles 2018 und SUBTLEX-DE), Nachrichten (NewsCrawl 2014, GlobalVoices), Büchern (Google Books Ngrams 2012, <http://books.google.com/ngrams>), Webtexten (OSCAR), Twitter und Reddit. **SUBTLEX-DE** stammt von Marc Brysbaert et al. und ist frei verfügbar (Adresse laut wordfreq: <http://crr.ugent.be/programs-data/subtitle-frequencies>; Veröffentlichung siehe Zitierhinweise); Robyn Speer darf es mit Erlaubnis von Marc Brysbaert für jeden Zweck weitergeben, sofern die SUBTLEX-Autoren genannt werden. Die **OpenSubtitles**-Daten stammen vom Projekt OpenSubtitles, <http://www.opensubtitles.org/>, über OPUS. |
| Verwendet für | Häufigkeit jeder Wortform auf der Zipf-Skala: Spalte `zipf` in `ziel.tsv` und alle Schwellen der Auswahl. Die englische Tabelle nur als Gegenprobe: Ist eine Schreibung im Englischen häufiger, ist ihre deutsche Häufigkeit verdächtig (*Air*, *Jeans*). |

wordfreq faltet ß zu ss und Groß- zu Kleinschreibung. Die Häufigkeit eines
gefalteten Schlüssels (*masse*) ist deshalb im Verhältnis der
FrequencyWords-Zählungen auf die Schreibungen verteilt, die es gibt (*Masse*,
*Maße*).

### 4. FrequencyWords

| | |
| --- | --- |
| Urheber | Hermit Dave, <https://github.com/hermitdave/FrequencyWords>; Urheberrechtshinweis im Repository: „Copyright (c) 2016 Hermit Dave“ |
| Datei | `content/2018/de/de_full.txt`, 17 MB |
| Adresse | <https://raw.githubusercontent.com/hermitdave/FrequencyWords/525f9b560de45753a5ea01069454e72e9aa541c6/content/2018/de/de_full.txt> |
| Version | Git-Commit `525f9b5` vom 2022-02-07, Daten „OpenSubtitles 2018“ |
| SHA-256 | `a5fc13f4efaaf70fd9226d11295fd3cd4c2264852ee1fad22c0abaf64acec8dc` |
| Lizenz | Inhalte CC BY-SA 4.0, Code MIT (laut README des Repositorys) |
| Herkunft der Zählungen | Untertitel des Projekts OpenSubtitles, <http://www.opensubtitles.org/>, über OPUS OpenSubtitles 2018, <https://opus.nlpl.eu/> |
| Verwendet für | zweites Häufigkeitssignal: Aufteilung der wordfreq-Häufigkeit auf ß- und ss-Schreibungen, Entscheidung bei Schweizer Doppelgängern (*strasse* gegen *straße*), Bestätigung deutscher Wörter mit englischem Zwilling (*See*) |

## Nur beim Bau verwendet, nicht in den Daten

Diese beiden Quellen dienen allein dazu, anstößige Wörter auszusortieren. Aus
ihnen steht kein Wort und keine Angabe in den Dateien dieses Repositorys; die
Filterliste, in die sie eingehen, wird nicht veröffentlicht.

### 5. OpenThesaurus

| | |
| --- | --- |
| Urheber | OpenThesaurus, <https://www.openthesaurus.de> |
| Datei | `OpenThesaurus-Textversion.zip`, 1,6 MB |
| Adresse | <https://www.openthesaurus.de/export/OpenThesaurus-Textversion.zip> |
| Version | Export vom 2026-09-28, 23:01 Uhr |
| SHA-256 | `107c7921127dcb5753ec91e860e87b15e89fc6c4fc15c092b009486cfac74ad1` |
| Lizenz | wahlweise CC BY-SA 4.0 oder LGPL 2.1, <https://www.openthesaurus.de/about/download> |
| Verwendet für | Filterliste: Einzelwörter, die in jedem Vorkommen als `derb` oder `vulg.` markiert sind, sofern Wiktionary sie nicht als neutrales Wort kennt |

### 6. List of Dirty, Naughty, Obscene, and Otherwise Bad Words (LDNOOBW), Deutsch

| | |
| --- | --- |
| Urheber | Mitwirkende des Projekts, <https://github.com/LDNOOBW/List-of-Dirty-Naughty-Obscene-and-Otherwise-Bad-Words> |
| Datei | `de`, 66 Einträge |
| Adresse | <https://raw.githubusercontent.com/LDNOOBW/List-of-Dirty-Naughty-Obscene-and-Otherwise-Bad-Words/5faf2ba42d7b1c0977169ec3611df25a3c08eb13/de> |
| Version | Git-Commit `5faf2ba` vom 2020-07-13 |
| SHA-256 | `ebe44d7772897390e27f7bec412fdcdf0efc294e4db157f8487c4cd8d4fabd55` |
| Lizenz | CC BY 4.0, <https://creativecommons.org/licenses/by/4.0/deed.de> |
| Verwendet für | Filterliste, ausgenommen neutrale Einträge wie *nackt* oder *Kimme* |

## Geprüft und nicht verwendet

DWDS-Lemmadatenbank, DeReWo (IDS Mannheim), Leipzig Corpora Collection,
igerman98/hunspell, die Wortliste der Trennmustermannschaft und
enz/german-wordlist wurden geprüft und nicht verwendet, wegen ihrer Lizenz- oder
Nutzungsbedingungen oder nach Abwägung. Kein Werkzeug lädt oder liest sie.

## Zitierhinweise

Für wissenschaftliche Arbeiten bitten die Quellen um diese Zitate:

- Tatu Ylonen: Wiktextract: Wiktionary as Machine-Readable Structured Data.
  Proceedings of the 13th Conference on Language Resources and Evaluation
  (LREC), S. 1317–1325, Marseille, 20.–25. Juni 2022.
- Robyn Speer (2022): rspeer/wordfreq: v3.0 (v3.0.2). Zenodo.
  <https://doi.org/10.5281/zenodo.7199437>
- Brysbaert, M., Buchmeier, M., Conrad, M., Jacobs, A. M., Bölte, J. & Böhl, A.
  (2011): The word frequency effect: A review of recent developments and
  implications for the choice of frequency estimates in German. Experimental
  Psychology, 58, 412–424. <https://doi.org/10.1027/1618-3169/a000123>
- P. Lison und J. Tiedemann (2016): OpenSubtitles2016: Extracting Large
  Parallel Corpora from Movie and TV Subtitles. Proceedings of the 10th
  International Conference on Language Resources and Evaluation (LREC 2016).

## Lizenztexte

- CC BY-SA 4.0: [LICENSE](LICENSE) (englisch), deutsche Fassung
  <https://creativecommons.org/licenses/by-sa/4.0/legalcode.de>, Übersicht
  <https://creativecommons.org/licenses/by-sa/4.0/deed.de>
- CC BY 4.0 (nur LDNOOBW, nicht in den Daten):
  <https://creativecommons.org/licenses/by/4.0/legalcode.de>
