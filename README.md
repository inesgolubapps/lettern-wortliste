# Lettern-Wortliste

Die Wortlisten und Rätseldaten des iPhone-Worträtsels **Lettern** von Tickwork,
offen unter [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.de).

Stand 2026-10-01 · Wortlisten `2026-09-29+sha256:e5a9a85281a8` · Lettern 0.9.0 ·
[English summary below](#english)

In Lettern bildet man aus einem Rad von Buchstaben Wörter und füllt damit ein
kleines Kreuzgitter. Welche Wörter das Spiel als Lösung verlangt und welche es
als Extrawort annimmt, steht in diesem Repository, ebenso jede Seite des Buchs
und jedes Tagesrätsel. Die Daten sind aus freien Quellen abgeleitet, vor allem
aus dem Wiktionary, und stehen deshalb wie diese unter CC BY-SA 4.0.

## Inhalt

| Datei | Inhalt | Umfang |
| --- | --- | --- |
| `daten/ziel.tsv` | Zielwortschatz: Wörter, die ein Rätsel als Lösung verlangen kann, mit Schreibung, Grundform, Wortart und Häufigkeit | 12.762 Wortformen in 16.244 Zeilen |
| `daten/bonus.tsv` | Akzeptanzliste: alle Wortformen, die als Extrawort zählen, mit Schreibung | 259.798 Wortformen |
| `daten/levels.json` | das Buch: jede Seite mit Steinen, Gitter, Ziel- und Extrawörtern | 640 Seiten in 40 Bögen |
| `daten/daily.json` | die Tagesrätsel, im selben Format | 420 Rätsel |
| `kuratierung/kuratierung.tsv` | Protokoll der Einzelprüfung: eine Zeile je Entscheidung, mit Grund | 15.385 Zeilen |
| `kuratierung/ziel-nein.txt` | gültige Wörter, die nie als Lösung verlangt werden, mit Grund | |
| `kuratierung/ziel-pflicht.txt` | Wörter, die Zielwörter sind, obwohl eine Regel sie sonst ausschlösse | |
| `kuratierung/lesart-vorrang.txt` | festgelegte Lesart und damit Schreibung (*Regen*, nicht *regen*) | |
| `kuratierung/kurzwort-ok.txt` | Kurzwörter, die als gewöhnliche Wörter gelten (*Auto*, *Kino*) | |
| `QUELLEN.md` | alle Quellen mit Version, Prüfsumme und Lizenz | |
| `FORMAT.md` | Spalten und Felder jeder Datei | |
| `LICENSE` | Lizenztext CC BY-SA 4.0 im englischen Original | |
| `VERSION`, `SHA256SUMS` | Stand und Prüfsummen aller Dateien | |

Wie die Dateien aufgebaut sind, steht in [FORMAT.md](FORMAT.md).

## Welche Wörter zählen

- **Zielwörter** sind Wörter, die man im Alltag kennt, in Grundform oder einer
  gängigen Form wie *Tage* oder *trägt*. Nur sie verlangt ein Rätsel als
  Lösung.
- **Extrawörter** sind alle Formen der Wörter, die im deutschsprachigen
  Wiktionary stehen, auch gebeugt und selten. Sie werden angenommen, aber nie
  verlangt.
- Nicht dabei sind Namen, Abkürzungen und Schimpfwörter. Die Listen enthalten
  Wörter mit 3 bis 10 Buchstaben. Ä, Ö und Ü sind eigene Buchstaben, ß ist ß;
  Schweizer und alte Schreibungen (*Strasse*, *daß*) zählen nicht.

## Namensnennung der Quellen

Die Daten sind aus diesen Werken abgeleitet. Dateien, Versionen und
Prüfsummen stehen in [QUELLEN.md](QUELLEN.md).

1. **Wiktionary, deutschsprachige Ausgabe** – von den Autorinnen und Autoren
   des deutschsprachigen Wiktionary, <https://de.wiktionary.org>.
   Maschinenlesbar aufbereitet von kaikki.org mit wiktextract (Tatu Ylonen),
   <https://kaikki.org/dewiktionary/>. Stand: Wiktionary-Dump vom 2026-09-01.
   Lizenz: CC BY-SA 4.0 (zusätzlich GFDL; wir nutzen CC BY-SA 4.0).
2. **Wiktionary, englischsprachige Ausgabe, deutsche Einträge** – von den
   Autorinnen und Autoren des englischsprachigen Wiktionary,
   <https://en.wiktionary.org>. Aufbereitet von kaikki.org mit wiktextract,
   <https://kaikki.org/dictionary/German/>. Stand: Wiktionary-Dump vom
   2026-09-02. Lizenz: CC BY-SA 4.0 (zusätzlich GFDL; wir nutzen
   CC BY-SA 4.0).
3. **wordfreq** 3.1.1 – von Robyn Speer, <https://github.com/rspeer/wordfreq>.
   Lizenz der Daten: CC BY-SA 4.0. Die deutschen Häufigkeiten enthalten
   **SUBTLEX-DE** von Marc Brysbaert et al. (frei verfügbare Daten, laut
   wordfreq unter <http://crr.ugent.be/programs-data/subtitle-frequencies>)
   und Untertitel des Projekts **OpenSubtitles** (<http://www.opensubtitles.org/>) über OPUS,
   außerdem Wikipedia, Nachrichten, Bücher (Google Books Ngrams), Webtexte,
   Twitter und Reddit (Einzelheiten in QUELLEN.md).
4. **FrequencyWords** – von Hermit Dave,
   <https://github.com/hermitdave/FrequencyWords>, Stand Commit `525f9b5`.
   Lizenz der Inhalte: CC BY-SA 4.0. Die Zählungen stammen aus Untertiteln des
   Projekts OpenSubtitles (<http://www.opensubtitles.org/>), über OPUS
   OpenSubtitles 2018.

Diese Werke werden von ihren Urheberinnen und Urhebern ohne Gewähr
bereitgestellt; es gilt der Haftungsausschluss ihrer Lizenz (für
CC BY-SA 4.0 Abschnitt 5, siehe [LICENSE](LICENSE)).

## Was wir verändert haben

Die Dateien sind keine Kopien der Quellen, sondern aus ihnen erstellt
(Bearbeitung im Sinne von Abschnitt 3(a)(1)(B) der Lizenz):

- **Extrahiert.** Aus dem deutschsprachigen Wiktionary nur Einträge der
  Sprache Deutsch: Stichwort, Wortart, alle Flexionsformen aus den Tabellen und
  den Einträgen „Deklinierte Form“, „Konjugierte Form“ und ähnlichen, dazu die
  Markierungen (vulgär, veraltet, regional …). Bedeutungstexte sind nicht
  übernommen. Alle Formen sind klein geschrieben (Unicode NFC) und bestehen nur
  aus a–z, ä, ö, ü und ß.
- **Gefiltert.** Entfernt sind Eigennamen, Abkürzungen, die meisten Kurzwörter
  (*Reha*, *Alu*), Einträge, die nur veraltet oder mundartlich sind,
  umgangssprachliche Zusammenziehungen (*biste*), Mehrwortformen, Formen mit
  Bindestrich, Apostroph oder Großbuchstaben im Wortinneren, Schweizer und alte
  Schreibungen sowie vulgäre, derbe, beleidigende und sexuelle Wörter (siehe
  „Was nicht dazugehört“).
- **Zusammengeführt.** Die Häufigkeit jeder Form (Spalte `zipf`) stammt aus
  wordfreq. Weil wordfreq ß und ss nicht unterscheidet, ist sie im Verhältnis
  der FrequencyWords-Zählungen auf die Schreibungen verteilt (*Masse*,
  *Maße*). Das englischsprachige Wiktionary liefert nur Hinweise (Kurzwörter,
  anstößige Wörter, Namen), keine Wörter.
- **Nach Häufigkeit ausgewählt.** Zielwörter sind Formen mit einer neutralen
  Bedeutung, deren Häufigkeit über einer Schwelle liegt (Zipf 3,2 für
  Grundformen, 3,6 für gebeugte Formen), mit Regeln gegen Namen, englische
  Wörter und Ausreißer.
- **Einzeln geprüft.** In drei Durchgängen (29. und 30. September 2026) wurde
  jede Zielform einzeln geprüft. Was dabei herausgenommen, aufgenommen oder
  festgelegt wurde, steht mit Grund im Ordner `kuratierung/`.
- **Schreibung bestimmt.** Ob eine Form groß oder klein geschrieben angezeigt
  wird (`show`), folgt aus Wortart und wahrscheinlichster Lesart, wo nötig von
  Hand festgelegt (`lesart-vorrang.txt`).
- **Rätsel erzeugt.** `levels.json` und `daily.json` hat ein eigenes Programm
  aus den Listen erzeugt: Es wählt ein Leitwort, bildet aus ihm das Rad, wählt
  Zielwörter aus dem Zielwortschatz, legt das Gitter und nimmt alle übrigen
  bildbaren Formen der Akzeptanzliste als Extrawörter der Seite. Jede Seite ist
  automatisch geprüft. Ab Bogen 3 stammen die Leitwörter aus eigenen
  Themenlisten.

## Lizenz

Die Daten in diesem Repository stehen unter **Creative Commons Namensnennung –
Weitergabe unter gleichen Bedingungen 4.0 International (CC BY-SA 4.0)**:
<https://creativecommons.org/licenses/by-sa/4.0/deed.de>. Der vollständige
Lizenztext steht in [LICENSE](LICENSE) (englisch, abgerufen am
2026-10-01 von <https://creativecommons.org/licenses/by-sa/4.0/legalcode.txt>);
die deutsche Fassung: <https://creativecommons.org/licenses/by-sa/4.0/legalcode.de>.

Du darfst die Daten kopieren, verändern und weitergeben, auch kommerziell,
solange du die Urheber nennst, Änderungen kenntlich machst und deine Fassung
unter derselben oder einer kompatiblen Lizenz weitergibst.

## Weiterverwenden

Diese Zeile nennt alle Urheber und kann so übernommen werden:

```
„Lettern-Wortliste“ von Tickwork, Stand 2026-10-01, https://github.com/inesgolubapps/lettern-wortliste, lizenziert unter CC BY-SA 4.0 (https://creativecommons.org/licenses/by-sa/4.0/deed.de). Abgeleitet aus Wiktionary (Autorinnen und Autoren des deutsch- und des englischsprachigen Wiktionary, über kaikki.org/wiktextract), wordfreq (Robyn Speer) einschließlich SUBTLEX-DE (Brysbaert et al.) und FrequencyWords (Hermit Dave, Zählungen aus Untertiteln von OpenSubtitles.org), jeweils CC BY-SA 4.0.
```

Hast du die Daten verändert, schreib dazu, was du verändert hast, zum
Beispiel „gekürzt auf Wörter mit fünf Buchstaben“.

## Fehler melden

Fehlt ein Wort, ist eines falsch geschrieben oder gehört eines nicht ins
Spiel? Sag es uns:

- als Issue in diesem Repository: <https://github.com/inesgolubapps/lettern-wortliste/issues>
- in der App über „Melden“
- per E-Mail an inesgolubapps@gmail.com

Hilfreich sind das Wort und, wenn es um ein Rätsel geht, die Seitenzahl oder
das Datum des Tagesrätsels. Korrekturen kommen mit einer späteren Fassung in
die App und in dieses Repository.

## Was nicht dazugehört

- **Der Programmcode.** Der Code der App und die Werkzeuge, mit denen diese
  Dateien entstehen, sind nicht Teil dieses Repositorys und stehen nicht unter
  dieser Lizenz. Die Lizenz gilt für die Daten.
- **Die Filterliste.** Beim Bau sortiert eine eigene Liste vulgäre, derbe,
  beleidigende und sexuelle Wörter aus, gestützt auf Wiktionary, OpenThesaurus
  und LDNOOBW (siehe QUELLEN.md). Diese Liste ist nicht Teil der Daten und wird
  weder hier noch mit der App veröffentlicht; ihre Wörter stehen in keiner Datei
  dieses Repositorys. Deshalb fehlen in `kuratierung.tsv` auch die
  39 Einträge, die diese Liste betreffen.
- Name, Bilder, Klänge, Schriften und Texte der App.

## Ohne Gewähr

Die Daten sind für ein Spiel zusammengestellt, nicht als Wörterbuch oder
Rechtschreibhilfe. Sie werden so bereitgestellt, wie sie sind, ohne Gewähr für
Richtigkeit oder Vollständigkeit; Fehler und fragwürdige Einträge sind möglich.
Eine Haftung für ihre Verwendung ist ausgeschlossen, soweit das Gesetz es
zulässt (Abschnitt 5 der Lizenz).

---

## English

**Lettern word list.** The word lists and puzzle data of **Lettern**, a German
word puzzle for iPhone by Tickwork, as of 2026-10-01.

- `daten/ziel.tsv`: target vocabulary (words a puzzle may ask for);
  `daten/bonus.tsv`: every accepted word form with its spelling;
  `daten/levels.json`: the book (640 pages); `daten/daily.json`: the
  daily puzzles (420); `kuratierung/`: curation decisions with
  reasons. Field documentation: [FORMAT.md](FORMAT.md); sources, versions and
  checksums: [QUELLEN.md](QUELLEN.md) (both in German).
- Derived from the German and the English Wiktionary (via
  kaikki.org/wiktextract), wordfreq (Robyn Speer, including SUBTLEX-DE by
  Brysbaert et al.) and FrequencyWords (Hermit Dave, counts from
  OpenSubtitles), all CC BY-SA 4.0. Changes: extracted, filtered, merged,
  selected by frequency, every target form reviewed individually, puzzles
  generated with our own tools.
- Licence: CC BY-SA 4.0, full text in [LICENSE](LICENSE). Attribution line for
  reuse:

  ```
  "Lettern word list" by Tickwork, as of 2026-10-01, https://github.com/inesgolubapps/lettern-wortliste, licensed under CC BY-SA 4.0 (https://creativecommons.org/licenses/by-sa/4.0/). Derived from Wiktionary (contributors to the German and the English Wiktionary, via kaikki.org/wiktextract), wordfreq (Robyn Speer) including SUBTLEX-DE (Brysbaert et al.), and FrequencyWords (Hermit Dave, counts from OpenSubtitles.org subtitles), each CC BY-SA 4.0.
  ```

- The app's code and the build tools are not part of this repository and not
  covered by the licence. A filter list of offensive words is applied at build
  time; it is not part of the data and not published.
- Report errors as a GitHub issue, with „Melden“ in the app, or by e-mail to
  inesgolubapps@gmail.com.
- Provided as is, without warranty of any kind (Section 5 of the licence).
