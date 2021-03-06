imgo help
======================

#### Поддерживаемые форматы:
png,jpeg, jpg, gif

#### Использование:
- `imgo .` если запустить программу c точкой, в качестве парметра, то она рекурсивно будет искать все файлы (*.png, *.gif, - *.jpg, *.jpeg) в текущей директории и всех поддиректориях, лежащих ниже, и попытается сжать их
- `imgo file.png` в качестве атрибута поддерживается имя сжимаемого файла
- `imgo file.png file2.gif` вместо одного файла можно указать несколько, через пробел

#### Об уровнях сжатия:

Уровни сжатия imgo можно условно разделить на 3 степени (это справедливо для формата PNG):

- `imgo file.png` базовый уровень сжатия (используется по умолчанию), работает относительно быстро, применяет "безопасные" преобразования, рекомендуется использовать на файлах, которые будут открываться c помощью IE6;
- `imgo -b file.png` продвинутый уровень сжатия (вызывается параметром -b или -brute), применяется весь набор преобразований, опасен же тем, что некоторые файлы (с прозрачностью) могут некорректно отображаться в IE6;
- `imgo -m -b file.png` достигается за счет многократного сжатия файла (вызывается параметром -m или -multipass). Замечено, что при дополнительном проходе можно сжать файл сильнее, обычно счет идет на байты и доли процента. 

#### Расширенное использование

- `imgo -h`, `imgo --help` - вывести справку
- `imgo -b`, `imgo --brute` - перейти в режим продвинутого сжатия, опасен для IE6, сжимает лучше, но раза в 2-3 медленнее
- `imgo -png` - при рекурсивном обходе папки и ее поддиректорий обрабатывать только *.png файлы
- `imgo -jpg` - при рекурсивном обходе папки и ее поддиректорий обрабатывать только *.jpg и *.jpeg файлы
- `imgo -e`, `imgo --emulate` - включение режима эмуляции, исходные файлы перезаписаны не будут, будет выведена только информация о том, насколько можно сжать файл\файлы
- `imgo -m`, `imgo --multipass` - если файл удалось сжать, он будет обработан повторно, до тех пор, пока эффективность сжатия не будет равна 0
- `imgo -q`, `imgo --quiet` - скрытый режим, никакой информации выведено не будет
- `imgo -V`, `imgo --version` - выведет на экран версию скрипта
- `imgo -d`, `imgo --diff` - после сжатия выводит на экран информацию (различия) между оригинальным файлом и сжатым (экспериментальная функция)
- `imgo -v`, `imgo --log` - выводит на экран дополнительную информацию, применяется в отладочных целях
