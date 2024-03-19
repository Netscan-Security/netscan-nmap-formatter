<p align="center">
  <img width="100" src="https://imgur.com/3cw4DQr.png" alt="NetScan Security Logo" />
  <h2 align="center">NetScan NMAP-Formatter</h2>
  <p align="center">Precision Scans, Real-time Defense</p>
</p>

## Examples

HTML:
![nmap-example-html](https://user-images.githubusercontent.com/2762286/166215713-02ab3e43-5e89-4f4a-b9f1-64651f2939e1.png)
Graphviz:
![nmap-example-graphviz](docs/images/example-dot.png)

A tool that allows you to convert NMAP XML output to html/csv/json/markdown/dot/sqlite.

## Installation

It's possible to install it using `go install` command

```
go install github.com/vdjagilev/nmap-formatter/v2@latest
```

All other options can be found on [Installation Wiki page](https://github.com/vdjagilev/nmap-formatter/wiki/Installation).

## Usage

```bash
nmap-formatter [html|csv|md|json|dot|sqlite] [path-to-nmap.xml] [flags]
```

Alternatively, you can read the file from `stdin` and parse it

```bash
cat some.xml | nmap-formatter json
```

Convert XML output to nicer HTML

```bash
nmap-formatter html [path-to-nmap.xml] > some-file.html
```

or Markdown

```bash
nmap-formatter md [path-to-nmap.xml] > some-markdown.md
```

or JSON

```bash
nmap-formatter json [path-to-nmap.xml]
# This approach is also possible
cat nmap.xml | nmap-formatter json
```

or Graphviz (dot)

```bash
cat example.xml | nmap-formatter dot | dot -Tsvg > test.svg
# open test.svg with browser
```

or SQLite

```bash
cat example.xml | nmap-formatter sqlite --sqlite-dsn nmap.sqlite
# open nmap.sqlite with any database tool
```

More examples can be found on [Usage Wiki page](https://github.com/vdjagilev/nmap-formatter/wiki/Usage)

### Flags

* `-f, --file [filename]` outputs the result to the file (by default output goes to STDOUT)
* `--help` display help message
* `--version` display version (also can be used: `./nmap-formatter version`)

It's also possible to change various output options. More examples on [Usage Wiki Page - Flags](https://github.com/vdjagilev/nmap-formatter/wiki/Usage#flags-and-output-options).

Screenshots of various formats available [here](https://github.com/vdjagilev/nmap-formatter/wiki/Examples)

## Use as a library

Examples on how to use this project as a library in golang: [Use as a library Wiki page](https://github.com/vdjagilev/nmap-formatter/wiki/Use-as-a-library)
