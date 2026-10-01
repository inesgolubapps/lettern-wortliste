# Dateiformate

Stand 2026-10-01 · Wortlisten `2026-09-29+sha256:e5a9a85281a8`

Alle Dateien sind UTF-8 in Unicode-Normalform NFC, mit Zeilenende LF. Die
TSV-Dateien haben eine Kopfzeile und trennen Spalten mit einem Tabulator; es
gibt keine Anführungszeichen und keine Escapes. Dezimalzahlen haben einen Punkt.

**Wortformen** (`form`, `lemma`, `w`, `leit`, `bonus`) sind klein geschrieben
und bestehen nur aus a–z, ä, ö, ü und ß. Eine Form in den Listen hat 3 bis 10
Buchstaben, eine Grundform (`lemma`) kann kürzer oder länger sein (*du*).
Sortiert ist nach Unicode-Codepunkten: erst a–z, dann ß, ä, ö, ü. Das ist keine
Wörterbuchreihenfolge; *ähnlich* steht hinter *zwölf*.

## daten/ziel.tsv — Zielwortschatz

Die Wörter, die ein Rätsel als Lösung verlangen kann. Eine Zeile je **Lesart**:
Gehört eine Form zu mehreren Grundformen, steht sie mehrmals da. Die erste
Zeile einer Form ist die wahrscheinlichste Lesart; ihre Schreibung zeigt die
App. Die Zeilen sind nach `form` sortiert, innerhalb einer Form nach dieser
Rangfolge.

| Spalte | Inhalt | Beispiel |
| --- | --- | --- |
| `form` | die Wortform | `pflanzen` |
| `show` | Schreibung in dieser Lesart: groß bei Substantiven und bei Wörtern, deren Wiktionary-Stichwort groß geschrieben ist, sonst klein | `Pflanzen` |
| `lemma` | Grundform dieser Lesart (Wiktionary-Stichwort, klein) | `pflanze` |
| `pos` | Wortart dieser Lesart: `noun` Substantiv, `verb` Verb, `adj` Adjektiv, `adv` Adverb, `pron` Pronomen, `prep` Präposition, `conj` Konjunktion, `num` Zahlwort, `other` Artikel und Partikeln | `noun` |
| `zipf` | Häufigkeit der Form auf der Zipf-Skala, zwei Nachkommastellen; in allen Zeilen einer Form gleich | `4.59` |

```
pflanzen	Pflanzen	pflanze	noun	4.59
pflanzen	pflanzen	pflanzen	verb	4.59
trägt	trägt	tragen	verb	4.85
```

- **Zipf** ist der Zehnerlogarithmus der Vorkommen je Milliarde Wörter: 3
  heißt etwa einmal je Million Wörter, 6 einmal je tausend. Die Werte stammen
  aus wordfreq (siehe QUELLEN.md). Einige Wörter liegen unter der Schwelle von
  3,2 und sind trotzdem Ziel, weil eine Handliste sie aufnimmt
  (`kuratierung/ziel-pflicht.txt`).
- Haben zwei Lesarten dieselbe Grundform als Zeichenkette, steht nur eine Zeile
  da: das Verb *essen* und das Substantiv *das Essen* teilen sich `essen`.
- Pronomen hängen oft an mehreren Grundformen (*deiner* an *du*, *dein*,
  *ihr* …), weil Wiktionary bei ihnen ganze Tabellen führt.
- Ein Rätsel verlangt höchstens eine Form je Grundform.

12.762 Formen in 16.244 Zeilen; die ersten Lesarten gehören zu
8.824 Grundformen.

## daten/bonus.tsv — Akzeptanzliste

Jede Wortform, die das Spiel annimmt, mit ihrer Schreibung. Jede Form aus
`ziel.tsv` steht auch hier. Sortiert nach `form`.

| Spalte | Inhalt | Beispiel |
| --- | --- | --- |
| `form` | die Wortform | `anger` |
| `show` | Schreibung, unterscheidet sich von `form` höchstens im ersten Buchstaben | `Anger` |

```
anger	Anger
nagt	nagt
straße	Straße
```

- Ein Zielwort schreibt sich hier wie in seiner ersten Zeile in `ziel.tsv`.
- Für alle anderen Formen folgt die Schreibung aus ihrer wahrscheinlichsten
  Lesart: groß bei Substantiven und bei groß geschriebenen Stichwörtern
  (*Berliner*), sonst klein. Diese Schreibungen sind automatisch bestimmt und
  nicht einzeln geprüft.

259.798 Formen, davon 101.998 groß geschrieben.

## daten/levels.json, daten/daily.json — Rätsel

Beide Dateien haben dasselbe Format: ein JSON-Objekt, in `levels.json` eine
Seite je Zeile.

| Feld | Inhalt |
| --- | --- |
| `v` | Formatversion, derzeit `1` |
| `lexicon` | Stand der Wortlisten, gegen den die Rätsel erzeugt und geprüft wurden (gleich `lexikon` in `VERSION`). Datum des Quellenstands und ein Kürzel einer Prüfsumme über die Listen; das Kürzel lässt sich mit diesem Repository nicht nachrechnen, weil es auch die nicht veröffentlichte Filterliste umfasst |
| `generator` | Programm und Version, die die Rätsel erzeugt haben |
| `pages` | die Seiten |

### Eine Seite

| Feld | Inhalt |
| --- | --- |
| `page` | Seitenzahl, im Buch 1–640; bei Tagesrätseln die laufende Nummer |
| `bogen` | Bogen 1–40, je 16 Seiten; bei Tagesrätseln `0` |
| `kind` | `kreuz` (Kreuzgitter) oder `freisatz` (Wörter ohne Kreuzungen, untereinander) |
| `theme` | nur im Buch ab Bogen 3: Thema des Bogens, z. B. `garten`; Umlaute als ae, oe, ue |
| `leit` | Leitwort: das Zielwort, das alle Steine verwendet |
| `tiles` | die Steine des Rads in Ausgangsstellung, im Uhrzeigersinn von oben: Großbuchstaben `A`–`Z`, `Ä`, `Ö`, `Ü`, das `ß` und die Doppelsteine `CH` und `CK` |
| `cols`, `rows` | nur bei `kreuz`: Breite und Höhe des Gitters in Feldern, höchstens 10 × 8 |
| `words` | die Zielwörter, siehe unten |
| `bonus` | die Extrawörter: jede Form der Akzeptanzliste, die sich aus den Steinen bilden lässt und kein Zielwort der Seite ist; vollständig und sortiert |
| `bonusShow` | Schreibung jedes Extraworts, an derselben Stelle wie in `bonus` |
| `difficulty` | Schwierigkeitsmaß zwischen 0 und 1, drei Nachkommastellen; dient nur dem Einsortieren |
| `seed` | Startwert des Generators (hexadezimal); ohne den nicht veröffentlichten Generator ohne Bedeutung |

Ein Zielwort in `words`:

| Feld | Inhalt |
| --- | --- |
| `w` | die Wortform |
| `show` | Schreibung, wie die Seite „Gelöst.“ sie zeigt |
| `r`, `c` | nur bei `kreuz`: Zeile und Spalte des ersten Buchstabens, gezählt ab 0 von oben links |
| `d` | nur bei `kreuz`: Richtung, `H` waagrecht nach rechts, `V` senkrecht nach unten |

Reihenfolge der Zielwörter: auf `kreuz`-Seiten das Leitwort zuerst, dann nach
Länge absteigend; auf `freisatz`-Seiten in Anzeigereihenfolge, nach Länge und
innerhalb einer Länge alphabetisch (DIN 5007-1).

**Bildbar** heißt: Die Buchstaben des Worts lassen sich mit den Steinen legen,
jeder Stein höchstens einmal. Ein Doppelstein `CH` oder `CK` zählt nur ganz;
auf einer Seite mit `CH` liefert er das *ch* in *Tische*, ein einzelnes C oder
H gibt es dort nicht.

Beispiel, Seite 3 des Buchs (umbrochen):

```json
{"page":3,"bogen":1,"kind":"kreuz","leit":"rot","tiles":["T","R","O"],
 "cols":3,"rows":3,
 "words":[{"w":"rot","r":0,"c":0,"d":"H","show":"rot"},
          {"w":"ort","r":0,"c":1,"d":"V","show":"Ort"}],
 "bonus":["tor"],"bonusShow":["Tor"],"difficulty":0.037,"seed":"0x5b84928ec5aadfcf"}
```

ergibt das Gitter

```
R O T
. R .
. T .
```

### Das Buch (levels.json)

640 Seiten in 40 Bögen zu je 16 Seiten; die letzte Seite jedes
Bogens (16, 32, …, 640) ist ein `freisatz`. Der Doppelstein `CH` kommt ab Seite
41 vor, `ß` ab Seite 44, `CK` ab Seite 60. 5.894 Zielwörter und
29.057 Extrawörter.

### Die Tagesrätsel (daily.json)

420 Rätsel. Rätsel Nummer *n* gehört zum Tag 28. September 2026
plus *n* − 1 Tage, Nummer 1 ist also Montag, der 28. September 2026; nach dem
letzten Rätsel beginnt die Folge von vorn. Die Rätsel folgen einem
Wochenrhythmus und haben keine Doppelsteine und kein ß:

| Wochentag | Steine | Zielwörter |
| --- | ---: | ---: |
| Montag | 5 | 5–7 |
| Dienstag | 6 | 6–8 |
| Mittwoch | 6 | 7–9 |
| Donnerstag | 6 | 8–10 |
| Freitag | 7 | 9–11 |
| Samstag | 7 | 12–14 |
| Sonntag (`freisatz`) | 6 | 7–9 |

3.478 Zielwörter und 14.818 Extrawörter.

## kuratierung/kuratierung.tsv — Protokoll der Einzelprüfung

Eine Zeile je Entscheidung über eine Wortform, mit Grund. Das Protokoll wirkt
nicht auf die Listen; die Wirkung haben die Handlisten unten. Steht eine Form
mehrmals da, gilt die Zeile mit dem höheren `pass`.

| Spalte | Inhalt |
| --- | --- |
| `form` | die Wortform |
| `entscheidung` | `ok` bleibt Zielwort · `kein-ziel-ok` ist zu Recht kein Zielwort · `ziel-nein` gültiges Extrawort, nie Zielwort · `ziel-pflicht` wird Zielwort · `lesart-vorrang` bleibt Zielwort, angezeigte Lesart festgelegt · `kurzwort-ok` Kurzwort, das als gewöhnliches Wort gilt |
| `grund` | Begründung in Stichworten |
| `pass` | Durchgang: `1` am 2026-09-29, `2` und `3` am 2026-09-30 |

```
abbau	ok	Ziel bleibt	1
abgibt	kein-ziel-ok	zu Recht kein Ziel (form-unter-schwelle)	1
abartig	ziel-nein	abwertend	1
```

**Regelnamen** in Klammern bei `kein-ziel-ok`: `form-unter-schwelle` (die Form
ist zu selten), `lemma-unter-schwelle` (die übrigen Formen des Worts sind zu
selten), `nur-genitiv/zu-infinitiv/gerundiv` (nur Genitiv Singular,
zu-Infinitiv oder Gerundiv), `nur-imperativ-unter-schwelle` (nur Befehlsform,
zu selten), `nur-nebenform` (nur Verkleinerung oder Schreibvariante),
`keine-neutrale-bedeutung` (jede Bedeutung ist markiert, etwa umgangssprachlich,
veraltet oder regional), `anglizismus-englische-schreibung` (englisches
Lehnwort in englischer Schreibung), `englisch-dominant` (die Häufigkeit stammt
aus englischem Text), `homograph-eines-gesperrten-worts` (gleich geschrieben wie
ein Wort der Filterliste).

**Prüfhinweise** nach „Flag geprüft:“ wurden angesehen und verworfen:
`wf-fw-abweichung` (wordfreq und FrequencyWords weichen stark voneinander ab),
`auch-eigenname` (es gibt einen gleich geschriebenen Namen), `englisch?` und
`englisch-häufiger` (möglicherweise englisch; im Englischen häufiger),
`kurzwort`, `umgangssprachlich`, `regional`, `abwertend`, `en-anstößig` (das
englischsprachige Wiktionary markiert es als anstößig), `heikel` (heikles
Thema wie Krankheit oder Tod), `name?` (vermutlich ein Name).

Das Protokoll hält jede Entscheidung so fest, wie sie damals fiel. Spätere
Regeländerungen haben einige Zeilen überflüssig gemacht; so stehen *Gabel* und
*Pudel* noch mit `kurzwort-ok` da, obwohl die Erkennung sie inzwischen selbst
richtig einordnet und sie in `kurzwort-ok.txt` nicht mehr vorkommen. Die
39 Zeilen, die die Filterliste betreffen, sind nicht
veröffentlicht.

## kuratierung/*.txt — Handlisten

Die Listen, die beim Bau wirken. Eine Wortform je Zeile, klein; `#` beginnt
einen Kommentar bis zum Zeilenende. Die Kommentare sind Arbeitsnotizen mit dem
Grund; sie verweisen teils auf Skripte und Dokumente der nicht veröffentlichten
Werkzeuge (etwa `scripts/build_lexicon.py`, `out/diag/…`, „KONZEPT“).

| Datei | Format | Wirkung |
| --- | --- | --- |
| `ziel-nein.txt` | `form  # Grund` | gültiges Extrawort, aber nie Zielwort. Steht hier die Grundform eines englischen Lehnworts, gilt das für alle Formen (*baby* → auch *babys*) |
| `ziel-pflicht.txt` | `form  # Grund` | Zielwort, sofern die Form in der Akzeptanzliste steht. Steht hier die Grundform eines englischen Lehnworts, gilt das Wort als eingebürgert (*trick* → auch *tricks*) |
| `lesart-vorrang.txt` | `form  lemma[:wortart]  # Grund` | legt die erste Lesart einer Form in `ziel.tsv` und damit ihre Schreibung fest (`kommunen  kommune:noun`); ändert nie, ob eine Form Zielwort ist |
| `kurzwort-ok.txt` | `form  # Grund` | Kurzwort, das als gewöhnliches Wort gilt und deshalb nicht als Abkürzung herausfällt |

## VERSION und SHA256SUMS

`VERSION` nennt in Zeilen `schlüssel: wert` den Stand dieses Repositorys
(`stand`), der Wortlisten (`lexikon`), der Quellen (`quellenstand`) und die
Version der App (`app`). `SHA256SUMS` enthält die SHA-256-Prüfsumme jeder Datei;
prüfen mit `shasum -a 256 -c SHA256SUMS` (macOS) oder `sha256sum -c SHA256SUMS`
(Linux).
