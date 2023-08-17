1) Выгружаем баннеры -  General Usage, без клик тега 
2) Указываем в терминале с помощью **cd** путь до папки с архивами 
3) Распаковываем архивы (можно с помощью команды unzipall)
4) Оборачиваем `<div id="bs"></div>` в тег `<div id=Stage>...</div>`  и заменяем все слова **click** на **flick** c помощью команды: 

Для Linux (Windows + WSL): 
```find . -iname *.html -exec sed -i 's/<div id="bs"><\/div>/\n\t<div id="Stage">\n\t\t<div id="bs"><\/div>\n\t<\/div>\n\t/g' {} \;; find . -iname  *.html -exec sed -i 's/Click/Flick/gm' {} \;; find . -iname *.js -exec sed -i 's/CLICK/FLICK/gm' {} \;; find . -iname *.js -exec sed -i 's/click/flick/gm' {} \;; find . -iname *.js -exec sed -i 's/Click/Flick/gm' {} \;; grep -iR 'stage'; echo 'click: '; grep -iR 'click';```

Для MacOS: (перед использованием в первый раз необходимо установить утилиту sed с помошью команды ```brew install gnu-sed```) !
```find . -iname "*.html" -exec sed -i '' 's/<div id="bs"><\/div>/\n\t<div id="Stage">\n\t\t<div id="bs"><\/div>\n\t<\/div>\n\t/g' {} \;; find . -iname  "*.html" -exec sed -i '' 's/Click/Flick/g' {} \;; find . -iname "*.js" -exec sed -i '' 's/CLICK/FLICK/g' {} \;; find . -iname "*.js" -exec sed -i '' 's/click/flick/g' {} \;; find . -iname "*.js" -exec sed -i '' 's/Click/Flick/g' {} \;; grep -iR 'stage'; echo 'click: '; grep -iR 'click';```
