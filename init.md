# Создание нового репозитория

***Репозиторий Git***  — это папка, в которую Git отслеживает изменения. На компьютере может быть любое количество репозиториев, каждое из которых хранится в собственной папке. Каждый репозиторий Git в системе является независимым, поэтому изменения, сохраненные в одном репозитории Git, не влияют на содержимое другого.

Git Bash используют символ ```/``` для разделения каталогов. Например, абсолютный путь для каталога Program Files, будет чаще всего выглядеть следующим образом: ```/c/Program Files/```.
Ключевые команды:
1. Отображение текущего рабочего каталога:
```
pwd
```
2. Переход в определённый каталог:
```
cd <path>
```
3. Отображает содержимое каталога:
```
ls
```
По умолчанию, ls не отображает файлы, начинающиеся с ```.```, например, ```.gitignore```. Для отображения таких файлов нужно использовать флаг ```-a```:
```
ls -a
```
4. Создание нового файла:
```
git touch имя <файла>
```

Открыть терминал сразу в нужном каталоге можно кликнув правой кнопкой мыши на каталоге и выбрав Git Bash Here:
![](https://netology-code.github.io/guides/git-terminal/images/6.png)

Чтобы создать репозиторий из существующей папки на компьютере в командной строке следует перейти в корневую папку, содержащую код, и выполнить команду:
```
git init
```
[<<к содержанию<<](./readme.md) | [<назад](./gitinstall.md) | [вперед>](./gitfiles.md)