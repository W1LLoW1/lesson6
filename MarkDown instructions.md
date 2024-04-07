# Инструкция по работе с Git

## Основные команды
### Начало работы

Для начала работы с Git необходимо создать на устройстве папку, в которой в дальнейшем будет создан __*репозиторий*__.

В командной строке используем команду для перехода в необходимую папку
```sh
cd /folder_name
```

После чего вводим команду, чтобы инициализировать ее и у нас создался репозиторий
```sh
git init
```

Определить это мы можем, посмотрев скрытые папки и заметить, что у нас была создана папка __*.git*__, в которой и будет храниться конфигурация и весь процесс нашей работы с репозиторием.

## Работа с коммитами

Чтобы добавить файл к индексации, дабы в последствие создать __*коммит*__, необходимо прописать команду
```sh
git add filename
```

После чего нам необходимо сохранить изменения, создав наш __*коммит*__, прописав команду с ключом M **(Message)** и описанием
```sh
git commit -m "Text"
```

Также мы можем, после проделанного этапа, проверить __*лог*__ нашей ветки, прописав команды, в которых мы увидим уникальное значения каждого __*коммита*__, которое можем использовать для переключения между версиями файла
```sh
git log
git log --oneline #Позволяет сократить вывод журнала до одного значения на строку
```

Чтобы откатиться, а затем вернуться к нужной версии файла, необходимо прописать команду
```sh
git checkout 4fds #Можно вписать 4-6 символов уникального значения для выполнения команды
git checkout master #Где master - название нашей основной ветки, в которой находятся последние изменения
```


## Работа с ветками

Также, чтобы не забивать основную ветку, можно тестировать все необходимое в отдельной ветке, для чего мы используем команду
```sh
git branch branch_name
```

После чего будет создана отдельная ветка, на которую мы можем переключиться командой
```sh
git checkout branch_name
```

И продолжить работу в нашем *черновике*

Чтобы просмотреть, в какой на данный момент ветке мы находимся, воспользуемся командой
```sh
git branch
```

И в конце, чтобы перенести новые данные в основную ветку, нужно перейти на нее и влить все из нашей второстепенной ветки командами:
```sh
git checkout master #Где master - название основной ветки
git merge branch_name #После чего произойдет слияние веток
```

## Работа с логами

Во время использования Git мы также сталкиваемся с ситуациями, когда нам необходимо посмотреть __*историю*__ действий с нашим файлом

Для этого воспользуемся командой
```sh
git log <hash> #Для просмотра обычной, полной истории изменений
```

Но также есть и некоторые __*ключи*__, которые позволят облегчить процесс
```sh
git log --oneline #Выводит весь лог, где каждое значение будет умещено в одну строку
git log --graph #Указывает нам на изменения в части ветки, где мы сможем увидеть, в какой момент произошло отклонение от основной ветки и обратно
```

# Работа с удаленными репозиториями

Во время работы с Git мы также сталкиваемся с ситуациями, когда нам нужно выгрузить\загрузить свои работы на удаленный сервер, в нашем случае __*GitHub*__, чтобы другие люди могли видеть изменения в файлах и продолжать работу, делать правки и т.д.

Для начала, нам необходимо быть зарегистрироваными на веб-ресурсе и создать свой новый репозиторий, чтобы начать в нем работу, или загрузить на него уже существующие работы. 

Нам понадобятся следующие команды:
```sh
git remote add origin <url> # Команда для добавления удаленного репозитория
git branch -M main # Команда для смены основной ветки
git push -u origin main # Команда для загрузки своего репозитория на удаленный сервер (GitHub)
```

После чего Вы будете работать в своем удаленном репозитории, изменения в который можно вносить, как и через веб-интерфейс, так и локально, для этого нужно воспользоваться следующими командами, в зависимости от ситуации:
```sh
git pull # Для выгрузки актуальных изменений с удаленного сервера
git push -u origin main # Для загрузки актуальных изменений на удаленный сервер в ветку main
```

# Работа с MarkDown

## Основные команды

Используя язык разметки MarkDown, мы можем представить красивый и удобный вывод информации, выполняя несложные команды

### Работа с текстом

Для того, чтобы выделить текст *курсивом*, достаточно обрамить его звездочками (*) или нижним подчеркиванием (_)

Чтобы сделать **полужирный** текст, необходимо обрамить его двумя звездочками (**) или двойным нижним подчеркиванием (__)

Чтобы __*объединить*__ оба условия, совмещаем, обрамляя текст двумя нижними подчеркиваниями и звездочкой (__*)

## Работа со списками

Чтобы __*выделить*__ ненумерованный список, используем звездочку (*)
* Список 1
* Список 2

Нумерованный список выделяется цифрой (1.text)
1. Список 1
2. Список 2

Чтобы вставить изображение в текст, нужно написать ![text] (filename), пример:
![Hi! This is Python](python.png)

## Заключение

По итогу можем заметить, что выше был представлен список **основных** команд для старта работы с __*Git*__, выполнение сохранения работы для удобного восстановления или возврата к любой точке, при ответственном подходе и грамотному, осмысленному комментированию каждого созданного __*коммита*__