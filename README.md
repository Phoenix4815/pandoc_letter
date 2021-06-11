# Pandoc Template for DIN5008 type letters

![Pull requests welcome!](https://img.shields.io/badge/-Pull%20requests%20welcome!-informational)
![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/Phoenix4815/pandoc_letter?sort=semver)
[![License: AGPL v3](https://img.shields.io/badge/license-AGPL%20v3-blue.svg)](http://www.gnu.org/licenses/agpl-3.0)

This repository provides a simple Pandoc LaTeX template for German DIN5008A and DIN5008B conform letters.
Internally, this template is based on the default Pandoc LaTeX template as well as the `scrletter` KOMA class.

## Example

Also see `examples/` folder.

```markdown
---
address:
    - An Max Mustermann
    - Fake Street 123
    - 12345 Berlin
    - Deutschland
backaddress:
    - Erika Mustermann
    - Musterhaus 2
    - 99999 Musterstadt
fromaddress:
    - Musterhaus 2
    - 99999 Musterstadt
fromname: Erika Musterfrau
fromemail: example@example.de
opening: Sehr geehrte Damen und Herrren,
closing: Mit freundlichen Grüßen,
encl: Wichtige Dokumente
---

Dies ist ein Testbrief!
*blub*

> Dies ist
> Ein Zitat
 
Test test
```

> ![Screenshot example letter](examples/example.png)

## Installation

Clone the repository and move the `din5008.latex` file into the Pandoc template folder.

### Windows

The template folder can be found in `%USERPROFILE%\AppData\Roaming\pandoc\templates\`.
Place the `din5008.latex` there.

### Linux

```bash
git clone https://github.com/Phoenix4815/pandoc_letter.git /tmp/din5008/
mkdir -p "$HOME/.pandoc/templates/"
cp /tmp/din5008/din5008.latex "$HOME/.pandoc/templates/"
```

### MacOS

The template folder can be found in `/Users/USERNAME/.pandoc/templates/`.
Place the `din5008.latex` there.

## Usage

Create a markdown type letter.
See the `examples/` folder for an example letter.
Compile using

```bash
pandoc --template din5008 YOUR_LETTER.md -o YOUR_LETTER_OUTPUT.pdf
```

Most options of the default Pandoc LaTeX template should be supported.
The following additional variables may be set:

| Key            | Description                                                                                                                                               | Default Value  |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|----------------|
| `letteroption` | The `scrletter` letter type                                                                                                                               | `DIN5008B`     |
| `address`      | Recipient adress                                                                                                                                          | __required__   |
| `fromaddress`  | Your address                                                                                                                                              | __required__   |
| `specialmail`  | The first three lines in the letter's window according to the [DIN standard](https://de.wikipedia.org/wiki/DIN_5008). Used to e.g. denote "Einschreiben". | _empty_        |
| `backaddress`  | Back address in the letter's window                                                                                                                       | _empty_        |
| `fromphone`    | Your phone number                                                                                                                                         | _empty_        |
| `fromfax`      | Your fax number                                                                                                                                           | _empty_        |
| `fromemail`    | Your email adress                                                                                                                                         | _empty_        |
| `yourref`      | "Ihr Zeichen"                                                                                                                                             | `-`            |
| `yourmail`     | "Ihr Schreiben vom"                                                                                                                                       | `-`            |
| `myref`        | "Unser Zeichen"                                                                                                                                           | `-`            |
| `date`         | Date of letter                                                                                                                                            | _current date_ |
| `opening`      | The letter's opening                                                                                                                                      | __required__   |
| `closing`      | The letter's closing                                                                                                                                      | __required__   |
| `ps`           | Post scriptum                                                                                                                                             | _empty_        |
| `cc`           | CC                                                                                                                                                        | _empty_        |
