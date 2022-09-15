# dg

Download all official diaries from Garulhos/SP.

## Usage

```sh
./dg -h
USAGE:
    dg [OPTIONS]

OPTIONS:
    -y <YEAR>
          official diary year
    -m <MONTH>
          official diary month
    -w <WORD>
          search word
    -a <NUM>
          num of lines after <WORD>
    -b <NUM>
          num of lines before <WORD>
    -i
          insensitive case search
    -v
          invert search results
```

## Batch

```sh
./date.sh |
  sd '(^\d),' '0$0' |
  awk -F',' '{print $1 " " $2}' |
  xargs -n2 bash -c './dg -m $0 -y $1'
```

## Dependencies

- [fd](https://github.com/sharkdp/fd)
- [pdftotext](https://linux.die.net/man/1/pdftotext)
- [ripgrep](https://github.com/BurntSushi/ripgrep)
- [sd](https://github.com/chmln/sd)
- [wget](https://www.gnu.org/software/wget/)
- [xargs](https://man7.org/linux/man-pages/man1/xargs.1.html)
