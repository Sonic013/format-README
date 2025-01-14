# *Инструкция по работе с Git и удаленными репозиториями.*
## *Общее описание*
Git- это распределенная система управления версиями, позволяет работать как с локальными репозиториями, так и с удаленными. На настоящий момент является одной из самых распрастраненных систем контроля версий.

## *Начало работы*
Для начала работы необходимо посредством программы VS-code (для ОС Windows) выбрать папку для работы, а так же создать (или загрузить) файл, с которым будет вестись дальнейшая работа. После чего наобходимо ввести команду "git init" в папке с репозиторием, после чего у вас создастся скрытый файл .git .

### *Создание коммитов*
1. Добавление изменений в коммит
Для добавления изменений в коммит необходимо ввести команду "git add <имя файла>". Для добавления изменений во все файлы репозитория используется команда "git add -A"

2. Создание коммитов
Для создания коммита необходимо ввести команду "git commit". Для добавления комментария к коммиту необходимо дополнительно после введенной команды добавить <-m "текст комментария">.

3. Проверка состояния репозитория
Для того, что бы посмотреть были ли внесены какие-либо изменения в файлы, необходимо ввести команду "git status".

4. Проверка наличия отличий между версиями в пределах одной ветки
Для того, что бы увидеть, какие именно изменения были внесены в файлы после последнего коммита необходимо ввести команду "git diff". Зеленым цветом будут отоборажаться добавленные строки/файлы, красным - удаленные строки/файлы, а серым- те части, которые не претерпевали изменений.

### *Просмотр списка коммитов и переход между ними*
Для просмотра истории всех созданных коммитов необходимо ввести команду "git log". Таким образом отобразится список всех созданных коммитов с указанием автора, даты создания, а так же уникальным номером данного коммита. Для выбора отдельного коммита необходимо скопировать первые 4 цифры из уникального номера, ввести команду "git checkuot <номер коммита>".

## *Работа с ветками*
1. Создание веток и переход между ветками
Для создания ветки необходимо ввести команду "git branch <название ветки>". Для просмотра имеющихся веток необходимо ввести команду "git branch". В отображенном списке веток символом "*" будет обозначена ветка, на которой на данный момент находится пользователь. При настройке терминала "bash" так же будет присутствовать цветовое обозначение. Для перехода между разными ветками необходимо ввести команду "git checkout <название ветки>". Для создания ветки и перехода на нее необходимо ввести команду "git branch -b <название ветки>".

2. Объединение веток
Для объединения веток или добавления данных из одной ветки в другую необходимо перейти в ветку, в которую будет производиться выгрузка данных. После чего необходимо ввести команду "git merge <Название ветки, из которой будет производиться выгрузка>".

3. Удаление веток
Для удаления ветки необходимо ввести команду "git branch -d <название ветки>".

4. Конфликт веток при объединении
Если при попытке объединения веток в одной строке содержатся различные значения, возникает конфликт, который не позволяет провести автоматическое добавление данных из одной ветки в другую. В таком случае файл, версии которого объединялись, подсвечивается красным, а в окне терминала появляется сообщение о конфликте и окно перехода в меню разрешения конфликта. Пользователь в ручном режиме может сравнить, в чем разница версий, а так так же выбрать, какая из них по итогу останется при слиянии веток.

## *Работа с удаленными репозиториями*
### Что такое удаленный репозиторий
Репозиторий, хранящийся в облаке, на стороннем сервисе, специально созданном для работы с git имеет ряд преимуществ. Во-первых - это своего рода резервная копия вашего проекта, предоставляющая возможность безболезненной работы в команде. А еще в таком репозитории можно пользоваться дополнительными возможностями хостинга. К примеру -визуализацией истории или возможностью разрабатывать вашу программу непосредственно в веб-интерфейсе.

### Клонирование репозитория
Клонирование - это когда вы копируете удаленный репозиторий к себе на локальный ПК. Это то, с чего обычно начинается любой проект. При этом вы переносите себе все файлы и папки проекта, а также всю его историю с момента его создания. Чтобы склонировать проект, сперва, необходимо узнать где он расположен и скопировать ссылку на него. Например, адрес https://github.com/<пример репозитория>. Необходимо ввести команду git clone https://github.com/<пример репозитория> При клонировании в текущий каталог, там будет создана папка, в которую поместятся все проектные файлы и скрытая директория .git, с самим репозиторием, или с необходимой информацией о нем.

### Подключение к удаленному репозиторию
Чтобы связать свой локальный репозиторий с репозиторием на GitHub, необходимо ввести следующую команду в терминале: git remote add origin https://github.com/<пример репозитория>. Обратите внимание, что нужно обязательно изменить URI репозитория на свой.

### Отправка изменений на удаленный репозиторий
Команда, предназначенная для отправки изменений - push. Она принимает два параметра: имя удаленного репозитория и ветку, в которую необходимо внести изменения (master — это ветка по умолчанию для всех репозиториев). Например, git push <имя репозитория> master.

Запрос изменений с удаленного репозитория
Для загрузки изменений с удаленного репозитория необходимо ввести команду git pull <имя репозитория> master.

Как удалить локальный репозиторий
1. Для удаления локального репозитория необходимо удалить скрытую папку «.git» в корневом каталоге репозитория. Сделать это можно 3 способами:

2. Проще всего вручную удалить эту папку «.git» в корневом каталоге «Git Local Warehouse».
Также удалить, не устраивающий вас, репозиторий можно на github. Открываете нужный вам объект и переходите в пункт меню Настройки. Там, прокрутив ползунок вниз, вы попадете в зону опасности, где один из пунктов будет называться «удаление этого хранилища».
3. В локальном терминале ввести команду cd repository-path/ rm -r .git
