Key
===============

####Copy RSA to folder and modify permission:

```
chmod 700 ~/.ssh
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
chmod 644 ~/.ssh/authorized_keys
chmod 644 ~/.ssh/known_hosts
```

####Install HomeBrew:
`ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"`
and install ssh-add: `brew install ssh-copy-id`


Image optim
===============

####imgo
Устанавливаем homebrew и выполняем следующие команды в терминале:
```
brew install exiftool imagemagick optipng libjpeg gifsicle

formulas='pngout.rb  defluff.rb cryopng.rb imgo.rb'
for package in $formulas
do
brew install "https://raw.github.com/imgo/imgo-tools/master/Formula/"$package
done
```

####svgo 
Для установки требует наличия npm от Node.js (при установки с сайта npm идет в комплекте, при установки из homebrew нужно устанавливать отдельно)
```[sudo] npm install -g svgo```

Install program
===============

1. NvAlt
2. Dropbox
3. TextExpander
4. iTerm2
5. Sublime Text 3
6. PopClip
7. BetterTouchTool

Display
===============
Copy profile **"CustomMBA.icc"** to `/Library/ColorSync/Profiles/Displays/`
