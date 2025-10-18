# Text

## Output redirect
`<` - redirect input
`>` - redirect output

**fd descriptors**
- stdin  - 0
- stdout - 1
- stderr - 2

> [!NOTE]
> redirect stdout and stderr `&> output.txt`

> [!NOTE]
> redirect to /dev/null `<command> 2>%1 /dev/null`

---

## cut
```sh
cur -d "delim" -f <num of fields, comma sep>
```

---

## paste
concat files by lines of passed files

file1 file2 file3
one   three one three
two   two   two two
three one   three one

```sh
paste -d "delim" file1 file2 > file3
```

## head, tail
```sh
head -n <number>
tail -n <number>
```


## grep
```sh
grep

Pattern selection and interpretation:
  -E, --extended-regexp     PATTERNS are extended regular expressions
  -F, --fixed-strings       PATTERNS are strings
  -G, --basic-regexp        PATTERNS are basic regular expressions
  -P, --perl-regexp         PATTERNS are Perl regular expressions
  -e, --regexp=PATTERNS     use PATTERNS for matching
  -f, --file=FILE           take PATTERNS from FILE
  -i, --ignore-case         ignore case distinctions in patterns and data
  -w, --word-regexp         match only whole words
  -x, --line-regexp         match only whole lines
  -z, --null-data           a data line ends in 0 byte, not newline

Output control:
  -n, --line-number         print line number with output lines
      --line-buffered       flush output on every line
  -H, --with-filename       print file name with output lines
  -h, --no-filename         suppress the file name prefix on output
      --label=LABEL         use LABEL as the standard input file name prefix
  -o, --only-matching       show only nonempty parts of lines that match
  -r, --recursive           like --directories=recurse
  -R, --dereference-recursive  likewise, but follow all symlinks
  -c, --count               print only a count of selected lines per FILE

Context control:
  -B, --before-context=NUM  print NUM lines of leading context
  -A, --after-context=NUM   print NUM lines of trailing context
  -C, --context=NUM         print NUM lines of output context
```

> [!TIP]
> Find something `grep -rn <pattern>`

