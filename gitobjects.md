# Объекты git

Всю информацию git представляет в виде *объектов*.

Объекты — это то, в чём git хранит содержимое. Они хранятся в `.git/objects`, директории, которая иногда называется *объектной базой данных*.

Объекты представлены как: *блобы (blobs)*, *деревья(tree)*, *коммиты*.

***Blob*** (binary large object) – большой бинарный объект. Для каждого файла в репозитории формируется blob-файл, который содержит его имя и сжатое содержимое. Blob-файл формируется при добавлении файла в индекс.

Посмотреть информацию о проиндексированных файлах:
```
git ls-files
```
Получить git хэш проиндексированного файла:
```
git ls-files -s <имя файла>
```

***Tree*** (дерево) – показывает связи между файлами в репозитории. Деревья формируются для каждой директории репозитория (в том числе для корневой) во время коммита и показывают, какие файлы (или поддиректории) лежат в данной директории. Таким образом, объект дерева состоит из имен blob-объектов для файлов, которые лежат в данной директории, и других деревьев для всех поддиректорий.

***Объект коммита*** – содержит в себе имя автора коммита, время коммита и объект дерева корневой директории проекта.

```mermaid
flowchart LR
    node2[89ac1 commit <br> 92ce3 tree <br> author <br> commiter] -->
    node3[92ce3 tree <br> 5d914 blob 'filename' <br> 811e7 blob 'filename' <br> cba0c blob 'filename']:::class2 --> node4[5d914 blob]:::class1  
    node3[92ce3 tree <br> 5d914 blob 'filename' <br> 811e7 blob 'filename' <br> cba0c blob 'filename']:::class2 --> node5[811e7 blob]:::class1
    node3[92ce3 tree <br> 5d914 blob 'filename' <br> 811e7 blob 'filename' <br> cba0c blob 'filename']:::class2 --> node6[cba0c blob]:::class1
    classDef class1 fill:#FF8C00,stroke:#333,stroke-width:2px
    classDef class2 fill:#7CFC00,stroke:#333,stroke-width:2px
    classDef class3 fill:#3f3,stroke:#333,stroke-width:2px
```

Посмотреть тип и содержимое объекта можно при помощи команд:
```
git cat-file -t <hash>
git cat-file -p <hash>
```

[<<к содержанию<<](./readme.md) | [<назад](./cancel.md) | [вперед>](./branch.md)