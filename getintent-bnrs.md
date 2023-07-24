1) Выгружаем баннеры -  General Usage, без клик тега 
2) Указываем в терминале с помощью cd путь до папки с архивами 
3) Распаковываем архивы (можно с помощью команды unzipall)
4) Оборачиваем `<div id="bs"></div>` в тег <div Stage>...</div> c помощью команды: 

```find . -iname *.html -exec sed -i 's/<div id="bs"><\/div>/\n\t<div id="Stage">\n\t\t<div id="bs"><\/div>\n\t<\/div>\n\t/g' {} \;```


5) Меняем во всех html-файлах слова, включающие в себя слово "Click" c помощью: 

```find . -iname  *.html -exec sed -i 's/Click/Flick/gm' {} \;```


6) Меняем во всех js-файлах слова, включающие в себя слово "Click" с разным регистром букв (CLICK, click, Click) с помощью: 

```find . -iname *.js -exec sed -i 's/CLICK/FLICK/gm' {} \;```

```find . -iname *.js -exec sed -i 's/click/flick/gm' {} \;```

```find . -iname *.js -exec sed -i 's/Click/Flick/gm' {} \;```
