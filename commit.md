# Коммит изменений

### Создание

Коммит сохраняет снимок состояния индекса. Все файлы, созданные или изменённые, для которых не выполнено ```git add``` после редактирования — не войдут в коммит. Они останутся изменёнными только диске.

Коммит создается командой:
```
git commit -m "комментарии"
```
Если опустить метку -m откроется редактор, в котором можно изменить комментарий и сохранить файл.

Другие полезные опции команды ```git commit```:
* ```--amend``` — **перезаписать предыдущий коммит**,
* ```-a, --all``` — закоммитеть все изменения в файлах,
* ```--author [author]``` — подменить автора коммита,
* ```--date [date]``` — подменить дату коммита.

После создания коммита отобразится информация: на какую ветку выполнен коммит (например, ```master```), какая контрольная сумма ```SHA-1``` у этого коммита (```463dc4f```), сколько файлов было изменено, а также статистику по добавленным/удалённым строкам в этом коммите.

### Просмотр истории

Просмотр истории коммитов осуществляется командой:
```
git log
```
По умолчанию (без аргументов) ```git log``` перечисляет коммиты с их ```SHA-1``` контрольными суммами, именем и электронной почтой автора, датой создания и сообщением коммита в обратном к хронологическому порядке — последние коммиты находятся вверху.
Есть много вариантов выбора, какие элементы отображаются в логе. Например, удобным можеть быть такой формат:
```
git log --pretty=format:"%h %ad | %s%d [%an]" --graph --date=short
```
где:
* ```--pretty="..."``` — определяет формат вывода,
* ```%h``` — укороченный хэш коммита,
* ```%d``` — дополнения коммита (*«головы»* веток или теги),
* ```%ad``` — дата коммита,
* ```%s``` — комментарий,
* ```%an``` — имя автора,
* ```--graph``` — отображает дерево коммитов в виде ASCII-графика,
* ```--date=short``` — сохраняет формат даты коротким.

Чтобы не вводить каждый раз такую команду используют алиасы.
> *Алиасы* в git это пользовательские сокращенные команды, которые позволяют выполнять стандартные команды git, но использовать при этом выбранные нами сокращения.

Добавьте следующее в файл .gitconfig:
```
git config --global alias.hist "log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short"
```
Теперь команда `git hist` позволит избежать ввода очень длинной команды `log`.

[<<к содержанию<<](./readme.md) | [<назад](./gitindex.md) | [вперед>](./cancel.md)