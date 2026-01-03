# Bash
Если на проекте есть доступ к серверу, то тестировщик может просматривать логи или другие артефакты на нем. Для этого может пригодиться знание команд bash.

## Задание 1

##### Работа с файлами и директориями
```bash
~                                     # Открыть домашнюю директорию
pwd                                   # Определить имя папки, в которой вы находитесь
mkdir test1                           # Создать внутри этой папки каталог с именем test1
cd test1                              # Перейти в папку test1
touch file{1,2,3}.txt.                # Создать файл 1,2 и 3 внутри каталога test1
ls                                    # Проверить содержимое каталога test1 
cd                                    # Перейти в домашнюю директорию 
mkdir test2                           # Создать папку test2 внутри домашней директории
rmdir test2                           # Удалить папку test2 
cd mv ~/test1                         # Вернуться в директорию test1
rm file2.txt                          # Удалить файл 2 из папки test1 
mkdir test3                           # Создать папку в домашней директории test3
touch file{4,5}.txt                   # Добавить два файла в директорию test3
cd ..                                 # Вернуться в родительскую директорию
rmdir -rf test3                       # Удалить папку test3  
ls                                    # Проверить, что директория была удалена
mkdir test4                           # Создать папку test4 в домашней директории
mv ~/test1/file{1,3}.txt ~/test4      # Переместить файлы 1 и 3 из папки test1 в папку test4
echo line11 >> file1.txt              # Добавить в файл 1 три строки со словами line
echo line12 >> file1.txt            
echo line13 >> file1.txt
cat file1.txt                         # Посмотреть содержимое файла 1
echo line31 >> file3.txt              # Добавьте в файл 3 три строки со словами line
echo line32 >> file3.txt
echo line33 >> file3.txt
cat file1.txt file3.txt               # Просмотрите содержимое двух файлов (1 и 3) сразу
nano file1.txt + manual replacement   # Используя один из редакторов замените все строки в файле 1
nano file3.txt + manual replacement 
```
## Задание 2
##### Редактирование файлов, проверка и остановка процессов, проверка доступности веб-сайтов
```bash
mkdir test3                                   # Создать папку test 3 
cd test3                                      # Open directory test3 
echo -e "row1\nrow2\nrow3\nrow4" > file4.txt  # Добавить в папку test 3 три файла 4, 5 и 6, в каждом из которых должно быть по 4 строки row1, row2, row3, row4
echo -e "row1\nrow2\nrow3\nrow4" > file5.txt  
echo -e "row1\nrow2\nrow3\nrow4" > file6.txt 
grep "row2" file5.txt                         # Найдите строку row2 в файле 5
grep -R "row" .                               # Найдите строку row в папке test3
grep -c "row" file6.txt                       # Посчитайте сколько строк с содержимым row в файле 6
find . -name "file5.txt"                      # Найдите файл 5 внутри папки test3
find . -name "file5.txt" -delete              # Используя команду find, удалите файл 5
echo test > file4.txt                         # Используя команду echo, добавьте слово test в файл 4
sed 's/test/fail/g' file4.txt                 # Замените слово test в файле 4 на fail
echo test >> file4.txt                        # Добавьте в файл 4 слово test так, чтобы сохранилось содержимое
ps aux                                        # Просмотрите все процессы для юзеров не только в консоли, которые происходят в системе
kill 588                                      # Убейте любой неважный процесс в консоли
ping artsiomrusau.com                         # Узнайте доступность ресурса rusau.net, используя ping
ping -c 5 artsiomrusau.com                    # Отправьте 5 пакетов на сайт rusau.net  
curl https://petstore.swagger.io/v2/pet/      # Используя GET и команду curl, получите информацию о зарегистрированных питомцах с любым статусом на https://petstore.swagger.io/
findByStatus?status=registered                
curl -X POST https://petstore.swagger.io/     # Используя POST и команду curl, создайте нового пользователя на https://petstore.swagger.io/
v2/user' \ 
-H 'accept: application/json' \
-H 'Content-Type: application/json' \
-d '{
    "id": 0,
    "username": "new_user",
    "firstName": "Jack",
    "lastName": "Smith",
    "email": "smith233@example.com",
    "password": "test1234",
    "phone": "+70000000000",
    "userStatus": 1
}'
``` 
