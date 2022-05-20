# wordle-solver

A simple Wordle solver.

## Method

`wordle-solver` sources five letter words from `/usr/share/dict/words` (or
another specified file containing one word per line) and attempts to solve a
[Wordle](https://www.nytimes.com/games/wordle/index.html) puzzle.

The user must give feedback indicating whether each letter guessed does not
appear in the word, does appear, but at a different location, or appears at
the guessed location. Alternatively an answer can be supplied to solve
automatically. It's also possible to solve the daily or an arbitrary Wordle
from the *New York Times* website.

The algorithm is not terribly clever or optimal. On the first guess it will
randomly choose words with unique common consonants and up to two common
unique vowels (a, e, o). On the second guess all consonants and up to two of
any vowel are allowed, but all letters must still be unique. After that,
random words are chosen from the remaining possible words.

The solver plays in *hard mode* where any previously guessed letters in the
word must be used in subsequent guesses in the correct position if known.

## Usage

```
usage: wordle-solver [-h] [-a word] [-d] [-n number] [-p] [-s] [-t] [-v] [-w fname] [guess ...]

Solve a Wordle puzzle.

positional arguments:
  guess                 seed the solver with up to 6 guesses

optional arguments:
  -h, --help            show this help message and exit
  -a word, --answer word
                        auto-solve using supplied five letter word
  -d, --debug           show debug information
  -n number, --number number
                        auto-solve specified Wordle
  -p, --practice        do not update statistics
  -s, --statistics      print statistics
  -t, --today           auto-solve today's Wordle
  -v, --version         show program's version number and exit
  -w fname, --words fname
                        file containing list of words to guess from
```

## Example output

![Solution to Wordle 0](wordle-solver.png?raw=true)

## Copyright

wordle-solver 1.0

Copyright (c) 2022  David Purton

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
