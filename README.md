# Audit

[![Build status](https://ci.appveyor.com/api/projects/status/66po2pqg20s38kmi/branch/master?svg=true)](https://ci.appveyor.com/project/AnatolyKulakov/audit)

Аудит всей деятельности сообществ, представленный в дружелюбной к роботам форме.

## Назначение

Данный репозиторий - это самый полный архив всех встреч, спикеров, докладов, слайдов, видеозаписей и прочих артефактов активности [DotNetRu](http://dotnet.ru). Его основная цель - быть единым источником данных для всех последующих представлений ([сайтов](http://dotnet.ru/), [энциклопедий](https://github.com/DotNetRu/BrandBook/wiki), [приложений](https://github.com/DotNetRu/App), [видеотек](https://www.youtube.com/DotNetRu), [статистике](https://github.com/DotNetRu/BrandBook/wiki/LikedVideos) и т.д.).

## Формат

Аудит хранится в виде xml файлов с чрезвычайно простой и интуитивно понятной структурой.

### Логическая структура

DotNetRu состоит из [Сообществ](db/communities). Каждое сообщество регулярно собирает [Встречи](db/meetups). Встречи проходят на какой-то [Площадке](db/venues) при поддержке наших [Друзей](db/friends). На встречах [Докладчики](db/speakers) читают [Доклады](db/talks).

### Формальная структура

- [Xml Schema](schemas)
- [PowerShell](https://github.com/kulakovt/Boombr/blob/master/src/Model.ps1)

## Настройка редактора

Данный репозиторий чуствителен к окончаниям строк в XML файлах. Они должны быть в формате Windows (`CRLF`). Если вы редактируете файлы вручную, настройте ваш редактор на использование этого окончания.

В фициальной документации по [настройке git-клиента](https://git-scm.com/book/ru/v1/%D0%9D%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-Git-%D0%9A%D0%BE%D0%BD%D1%84%D0%B8%D0%B3%D1%83%D1%80%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-Git#%D0%A4%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B8-%D0%BF%D1%80%D0%BE%D0%B1%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B8%D0%BC%D0%B2%D0%BE%D0%BB%D1%8B) рекомендуется возложить на плечи системы контроля версий функцию переписывания окончания строк в хранимых файлах. Более того, эта наглость включена по умолчанию. Что является немыслемой глупостью и может привести к проблемам при наличии проверок содержимого. Например в случае с данным репозиторием. Поэтому при работе с Audit'ом рекомендуется выключить модификазию исходных хранимых файлов, а ещё лучше - для всей системы:

`git config --global core.autocrlf false`

:warning: Изменять содержимое файлов это задача редакторов (IDE) и прочих специализированных инструментов. Система контроля версий не должна ни при каких условиях портить то что ей велели хранить.
