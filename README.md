# <docbook>ЕСПД</docbook>

Данный проект предназначен для оформления документации
по стандарту ЕСПД в формате DocBook 5.

## Лицензия

Все материалы распространяются на условиях
лицензии [Creative Commons BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/deed.ru)

Полный текст лиценции находится в файле COPYING.

## Что это такое?

Проект <docbook>ЕСПД</docbook> создан для форматирования документов
в формате DocBook по стандарту ЕСПД. Помимо стилей форматирования
содержит шаблоны наиболее распространенных документов.

В репозитории лежат XSL стили DocBook на основе стандартных стилей
XSL-FO для создания PDF документов. Помимо требований стандарта ЕСПД,
предлагаемый набор стилей старается следовать общим правилам русского
оформления документов.

## Как это использовать?

Стилевые файлы соответствуют стандарту XSL и модифируют стандартный
набор XSL-FO. Генерировать документы можно распространенными XSLT и FO
процессорами. У нас используются xsltproc и Apache FO.

Репозиторий расположен на [BitBucket](https://bitbucket.org/Lab50/espd-docbook5),
склонируйте с помощью Git:
    git clone git@bitbucket.org:Lab50/espd-docbook5.git

Подключить стиль можно с помощью директивы *xml-stylesheet* непосредственно
в вашем документе:

    <?xml version="1.0" encoding="utf-8"?>
    <?xml-model … ?>
    <?xml-stylesheet type="text/xsl" href="~/espd-docbook5/espd/espd.xsl"?>
    <book>
     …
    </book>

Или непосредственно в командной строке процессора.

    xsltproc ~/espd-docbook5/espd/espd.xsl mybook.xml

или Apache FOP:

    fop -xml mybook.xml -xsl ~/espd-docbook5/espd/espd.xsl -pdf mybook.pdf

### Стилевые параметры

Стиль <docbook>ЕСПД</docbook> содержит ряд параметров с помощью
хоторых можно влиять на выходное оформление.

 *  *espd.decimal*
    Децимальный номер документа.

 *  *espd.text-indent*
    Абзацный отступ. Помимо абзацев используется для выравнивания
    многих элементов (перечислений, названий разделов).
