# Perl
p
## pragmas

`use warnings;`
`use strict`    - error on using undeclared vars


## vars
`$varname = value` - without strict
`my $varname = value` - with strict


## scalars

## strings
" - replace vars to values
' - vars names as text

q<non alphabetic symbol><non alphabetic symbol>
q<non alphabetic symbol>

### functions
int length(str)
int index(str)
str reverse(str)

str substr(str, start)
str substr(str, start, end)
str substr(str, start, end, replace_text)

str lc(str)  // lowercase
str uc(str)  // uppercase

## lists and arrays

```perl
my @arr =(item0, item1, item2, item3, item4, item5);
@arr[0];                # item0
@arr[0, 1, 2];          # (item0, item1, item2)
@arr[-2..-1];           # (item4, item5)
my $count = scalar @arr # length
my $last = $#arr        # length - 1
```
> [!WARNING]
> Perl automatically flattens nested lists
> (2, 3, (4, 5)) == (2, 3, 4, 5)


> [!TIP]
> Ranges: `(1..100)`, `(a..z)`

### functions

str[] qw(string)  // split by space
push and pop    - stack
unshift and pop - stack
sort(@arr)      - return new, not affect to original
sort(cmp, @arr) - use cmp func

## files

open(filehandler, mode, filename)
close(filehandler)

### reading
```perl
open(FH, "<", "input.txt");
my header = <FH>  # read one line
while (<FH>) {
    print $_;  # special variable that setted in while condition 
}
close(FH);
```

> [!TIP]
> <> operator allow read from files passed trough cli args or from stdin if not provided

### writing
```perl
open(FH, ">", "input.txt");
print FH "xdd", '\n';
close(FH);
```

### modes
- `<`  read
- `>`  write
- '>>' append


> [!TIP]
> `shift @ARGV` - give next cli argument


### file operators

| op  | meaning |
| --- | ------- |
| -r  | is readable   |
| -w  | is writable   |
| -x  | is executable |
| -e  | is exist      |
| -z  | is empty      |
| -s  | file size     |
| -f  | is plain file |
| -d  | is dir        |
| -l  | is link |
| -p  | is pipe |
| -S  | is socket |


> [!TIP]
> few ops `if ( -e -f -r $filename )` if file exist ans readable


## Hash

```perl
my %countries = qw(England English 
    France French 
    Spain Spanish 
    China Chinese 
    Germany German);
# or
my %countries =  ( England => 'English',
    France => 'French', 
    Spain => 'Spanish', 
    China => 'Chinese', 
    Germany => 'German');

%countries{'England'};  # English
%countries{'Italy'} = 'Italian';  # English
delete %countries{'Italy'};

for(keys %countries){
	print("Official Language of $_ is $countries{$_}\n");
}

exists %countries{'Germany'}
```


## control flow

### if

```perl
if (cond1) {
    ...
} elsif (cond2) {
    ...
} else {
    ...
}
```

### while


### unless 
unless - !if


### given 
switch case
```perl
use feature "switch";

given(expr){
    when(expr1){ statement;}
    when(expr1){ statement;}
    when(expr1){ statement;}
    …
    default { statement; }
}

given(expr){
    statement when expr1;
    statement when expr1;
    statement when expr1;
    …
    default { statement; }
}

print do {
    given ($input) {
      "The input has numbers\n"  when /\d/;
       "The input has letters\n"  when /[a-zA-Z]/;
       default { "The input has neither number nor letter\n"; }
   }
}
```


### for

```perl
my @a = (1..9);
for(@a){
	print("$_","\n");
}

foreach(@a){
	print("$_","\n");
}

for my $i (@a){
	print("$i","\n");
}
```
