# pass-passphrase

A [pass](https://www.passwordstore.org/) extension for generating
passphrases.

## Usage

```
Usage:
    pass passphrase generate [--clip,-c] [--in-place,-i | --force,-f] pass-name [number of words]
        Generate an series of words for a passphrase. The number of words will be default to 4.
        The words will come from /usr/share/dict/words, and will all be lower case
        Optionally put it on the clipboard and clear board after 45 seconds.
        Optionally replace only the first line of an existing file with a new passphrase.

```

## Example

Generate a passphrase:

```
$ pass passphrase generate passphrase-secret
[master c036259] Add generated password for passphrase-secret.
 1 file changed, 0 insertions(+), 0 deletions(-)
  create mode 100644 passphrase-secret.gpg
  The generated password for passphrase-secret is:
  heitiki ungored dwarfy beennut

$ pass show passphrase-secret
heitiki ungored dwarfy beennut
```

Generate a phrase of different length

```
$ pass passphrase generate passphrase-secret 8
[master 6c2a58a] Add generated password for passphrase-secret.
 1 file changed, 0 insertions(+), 0 deletions(-)
  create mode 100644 passphrase-secret.gpg
  The generated password for pin-secret is:
  bream unmoved smally colmar kieye verglas discus banning
```

Generate a passphrase and copy to clipboard
```
$ pass passphrase generate -c passphrase-secret
[master cd84da1] Add generated password for passphrase-secret.
 1 file changed, 0 insertions(+), 0 deletions(-)
  create mode 100644 passphrase-secret.gpg
  Copied passphrase-secret to clipboard. Will clear in 45 seconds.

```

You can also use an environment variable `PASSWORD_STORE_PASSPHRASE_DICTIONARY` to change from the default dictionary of `/usr/share/dict/words`

All the other options supported by base `pass` is also supported, such as `--force`, `--inline`, and `--qrcode`.

## Installation

````
- Enable password-store extensions by setting ``PASSWORD_STORE_ENABLE_EXTENSIONS=true``
- Clone this repo and create a symlink (or just download the raw file) to `passphrase.bash` in `~/password-store/.extensions`
```

## Requirements

- `pass` 1.7.0 or later for extenstion support
- `qrencode` for generating QR code images

## License

```
Copyright (C) 2017 Hugh Davenport

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
```
