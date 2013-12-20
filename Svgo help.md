#### Usage:
`svgo [OPTIONS] [ARGS]`

#### Options:
  -h, --help : Help
  -v, --version : Version
  -i INPUT, --input=INPUT : Input file, "-" for STDIN
  -s STRING, --string=STRING : Input SVG data string
  -f FOLDER, --folder=FOLDER : Input folder, optimize and rewrite all *.svg files
  -o OUTPUT, --output=OUTPUT : Output file (by default the same as the input), "-" for STDOUT
  --config=CONFIG : Config file to extend or replace default
  --disable=DISABLE : Disable plugin by name
  --enable=ENABLE : Enable plugin by name
  --datauri=DATAURI : Output as Data URI string (base64, URI encoded or unencoded)
  --pretty : Make SVG pretty printed

Arguments:
  INPUT : Alias to --input
  OUTPUT : Alias to --output
with files:

$ svgo test.svg
or:

$ svgo test.svg test.min.svg
with STDIN / STDOUT:

$ cat test.svg | svgo -i - -o - > test.min.svg
with folder

$ svgo -f ../path/to/folder/with/svg/files
with strings:

$ svgo -s '<svg version="1.1">test</svg>' -o test.min.svg
or even with Data URI base64:

$ svgo -s 'data:image/svg+xml;base64,…' -o test.min.svg
with SVGZ:

from .svgz to .svg:

$ gunzip -c test.svgz | svgo -i - -o test.min.svg
from .svg to .svgz:

$ svgo test.svg -o - | gzip -cfq9 > test.svgz
