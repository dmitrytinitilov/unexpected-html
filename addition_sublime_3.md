# Дополнение по Sublime 3 для верстальщика

**Горячие клавиши**

*Ctrl + `* - открывает консоль

*Ctrl + /* - выделяет блок комментариями

*Ctrl + L* - выделяет строку

*Ctrl + D* - выделяет слово

*Ctrl + Space* - включает автодополнение

*«CMD+ALT+Left/Right Arrow»* и *«CTRL+Pagedown/Pageup»* - переключение между вкладками

*Alt + F3* - выделяет все слова, совпадающие с заданным

**Запуск нескольких панелей**

ALT-Shift-2  -  две панели
ALT-Shift-3  -  три панели и т.д.

**Выравнивание**

Edit -> Line -> Reindent

Alt +E+L+R


Либо можно настроить свое сочетание клавиш

```json
[
    {
        "keys": ["ctrl+shift+r"],
        "command": "reindent",
        "args": {
            "single_line": false
            }
        }
     
]
```

**Хорошие цветовые схемы**

Aristocat

Solarized(Dark)


**Настройка Autosave при потере фокуса**

http://lucybain.com/resources/setting-up-sublime-autosave/


**Установка Package Control**

Заходим на https://packagecontrol.io/  

Ctrl + `
И копируем "магический" код

**Добавляем плагины**

*Color Highlighter* для выделения цвета

*Color Picker* - Цветовое колесо. Для его вызова нажимаем Ctrl + Shift + C

*SidebarEnhacements*

*AllAutocomplete* - автодополнение кода

*Emmet*

Обзор плагина от Sorax
https://www.youtube.com/watch?v=mGPZ8P7xDLE

Хорошая статья по синтаксису
https://habrahabr.ru/post/175747/

Шпаргалка по Emmet
http://docs.emmet.io/cheat-sheet/

*JSLint*

*SublimeLinter*
https://habrahabr.ru/post/262137/

*Color Picker*
Ctrl + Shift + C

**Полезные ссылки**

*Еще о плагинах*
https://habrahabr.ru/post/235901/

*О редакторе*
http://habrahabr.ru/post/244681/

*Создаем свою тему*
http://habrahabr.ru/post/258053/

**Все подряд**

*Для верстки*
http://aalexeev239.github.io/sublime-presentation/#Cover
https://habrahabr.ru/post/154667/
https://toster.ru/q/101569

*Для Full Stack Developer'a*
http://www.sitepoint.com/10-essential-sublime-text-plugins-full-stack-developer/
https://habrahabr.ru/post/154667/


*Несколько панелей*
http://www.macdrifter.com/2012/07/sublime-text-working-with-multiple-panes.html


*Добавить в контекстное меню*
http://ipestov.com/12-most-helpful-shortcuts-for-sublime-text/


*JS-разработка + Авдополнение + Markdown*
https://habrahabr.ru/post/235901/


https://habrahabr.ru/post/244681/


http://www.unix-lab.org/posts/sublime-text/

*Еще плагины*
http://sitear.ru/material/17-luchshih-plaginov-dlya-sublime-text-2



*Автообновление сайта при редактировании*
http://stackoverflow.com/questions/12823873/does-the-sublime-text-2-editor-support-real-time-html-css-preview

**Создание Build System для HTML и JavaScript**

http://www.c-sharpcorner.com/UploadFile/370e35/how-to-configure-sublime-text-to-open-html-file-in-chrome-on/

Открываем

Tools -> Build System -> New Build System

Прописываем

```
{
	"cmd": ["C:/Program Files/Google/Chrome/Application/chrome.exe","-u", "$file"]
}
```

Ctrl+B - для запуска Build system

**Видео:**

Видео-уроки по Sublime
https://www.youtube.com/watch?v=Wa7RIw19kUM

Про плагины
https://www.youtube.com/watch?v=NrYzJz1P4fE

Установка Package Control
https://www.youtube.com/watch?v=zVLJfrIwEP8


