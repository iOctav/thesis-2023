В этом проекте представлен шаблон выпускной квалификационной работы, который подойдёт как для бакалаврской, так и для магистерской.

**Важно!**

Шаблон не идеален и соответствует не всем требованиям.
Но ты можешь помочь, даже если не разбираешься в техе.
Если консультант по нормконтролю высказал замечания к работе составленной по данному шаблону, то смело можно [заводить issue](https://gitlab.com/kspt-templates/thesis/issues/new)
И вместе мы попробуем исправить шаблон или инструкцию по его заполнению.

Исправления принимаются в виде Merge request'ов в репозиторий на [Gitlab](https://gitlab.com/kspt-templates/thesis) или [Github](https://github.com/kspt-templates/thesis).

## Работа с шаблоном

Для получения из данного шаблона **pdf** файла необходимо его собрать.

**Самый простой способ (!)** собрать данный шаблон - интегрированный в gitlab CI.
Чтобы им воспользоваться, достаточно [форкнуть](https://gitlab.com/kspt-templates/thesis/forks/new) проект на gitlab'е.
После чего все вносимые изменения будут инициировать процесс сборки. Результатом сборки является артефакт - архив с готовым pdf.

Если же есть необходимость собирать шаблон локально, то необходимо установить какой-либо дистрибутив LaTeX.

### Установка texlive

**Ubuntu 16.04** и выше воспользуйтесь следующей командой:

```
sudo apt install texlive-latex-extra texlive-lang-cyrillic
```

**Archlinux** воспользуйтесь следующей командой:

```
sudo pacman -S texlive-bin texlive-core texlive-fontsextra texlive-formatsextra texlive-langcyrillic texlive-latexextra texlive-pictures texlive-science 
```

### Сборка шаблона

Для упрощения процесса сборки написан Makefile, использовать который можно с помощью команды:

```
make pdf
```

Результатом выполнения является файл **thesis.pdf**

Для удаления всех артефактов сборки можно выполнить команду:
```
make clean
```

## Заполнение шаблона

1. Заполнить титульный лист, отредактировав файл `title.tex`
1. Заполнить реферат, отредактировав файл `abstract.tex`
1. Написать введение в файле `introduction.tex`
1. Начать заполнять номенклатуру с помощью данной конструкции на следующей строке после первого появления конкретной аббревиатуры в тексте `\nomenclature{GPLv2}{GNU GENERAL PUBLIC LICENSE v2 - Универсальная общественная лицензия GNU второй версии}`
1. Начать заполнять список используемых источников, добавляя записи в файл `thesis.bib` и ссылаясь на них из текста с помощью команды `\cite{}`
1. Отредактировать главы расположенные в файлах `chapter**.tex`.
Если имеющихся файлов недостаточно, то добавить новые можно, создав их и подключив после предыдущих в файле `thesis.tex`
1. Написать заключение в файле `conclusion.tex`
1. Отредактировать согласование в реферате (файл `csse-fcs.cls`):
	1. на 182 строке
		* рисунок - `\cyrr\cyri\cyrs\cyru\cyrn\cyro\cyrk`
		* рисунка - `\cyrr\cyri\cyrs\cyru\cyrn\cyrk\cyra`
		* рисунков - `\cyrr\cyri\cyrs\cyru\cyrn\cyrk\cyro\cyrv`
	1. на 188 строке 
		* таблица - `\cyrt\cyra\cyrb\cyrl\cyri\cyrc\cyra`
		* таблицы - `\cyrt\cyra\cyrb\cyrl\cyri\cyrc\cyr\char251`
		* таблиц - `\cyrt\cyra\cyrb\cyrl\cyri\cyrc`
	1. на 194 строке 
		* листинг - `\cyrl\cyri\cyrs\cyrt\cyri\cyrn\cyrg`
		* листинга - `\cyrl\cyri\cyrs\cyrt\cyri\cyrn\cyrg\cyra`
		* листингов - `\cyrl\cyri\cyrs\cyrt\cyri\cyrn\cyrg\cyro\cyrv`
	1. на 206 строке 
		* приложение - `\cyrp\cyrr\cyri\cyrl\cyro\cyrzh\cyre\cyrn\cyri\cyre`
		* приложения - `\cyrp\cyrr\cyri\cyrl\cyro\cyrzh\cyre\cyrn\cyri\cyrya`
		* приложений - `\cyrp\cyrr\cyri\cyrl\cyro\cyrzh\cyre\cyrn\cyri\cyrishrt`

_____

Основано на [шаблоне](https://bitbucket.org/ice_phoenix/csse-fcs-latex/) магистерской диссертации.
