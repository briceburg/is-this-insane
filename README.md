# site concept


## Example

in this case, we have a directory containing directories and want to express
contents as JSON (or yaml or whatever else cop supports)

### Context

* shell

```sh
$ mkdir -p ints/{0..9}
$ ls ints/
0  1  2  3  4  5  6  7  8  9
```

### Input:

* shell
  * cop utility - https://github.com/jasmith590/COP

```sh
$ mkdir -p ints/{0..9}
$ echo "INTEGERS=( $(cd ints ; echo *) )" | cop --stdin-type=shell --json
```

### Output

* json

```json
{
  "INTEGERS": [
    "0",
    "1",
    "2",
    "3",
    "4",
    "5",
    "6",
    "7",
    "8",
    "9"
  ]
}
```

### More

#### execution

* shell

curl this at _your risk_

```
curl https://is-this-insane/@id@.sh | sh
```

#### discuss

* WTF why not use ...
* you sute echo ints/*  is portable and outputs a single line to be used for array definition?
