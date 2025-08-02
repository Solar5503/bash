# Bash

Я рад поделиться некоторыми командами bash, которые я использовал для выполнения задач во время обучения по программе «Обеспечение качества».

## Навигация
- [Задание 1](#задание-1)
- [Задание 2](#задание-2)
- [Задание 3](#задание-3)
- [Задание 4](#задание-4)
- [Задание 5](#задание-5)

## Задание 1

Для начала создайте папку Faculties. Создайте 3 файла в папке Faculties через терминал: bio.txt, geo.txt, math.txt. Просмотрите содержимое папки Faculties. Удалите папку Faculties.

```bash
mkdir Faculties
cd Faculties
touch bio.txt geo.txt math.txt
ls -l
cd ..
rm -R Faculties
```

## Задание 2

Для начала создадим новую папку students с 3 файлами: new_comers.txt, current.txt, graduates.txt Потом создайте вторую папку archive. Переместите файл graduates.txt в папку archive. Скопируйте файл graduates.txt в папку students.Переименуйте файл graduates.txt из папки archive в файл old_graduates.txt. Добавьте в файл old_graduates.txt текст "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut interdum, lectus et vulputate mattis, tortor nisl congue ligula, at vestibulum diam elit sed arcu." Выведите текст из файла old_graduates.txt в отдельном процессе.

```bash
mkdir students
cd students
touch new_comers.txt current.txt graduates.txt
mkdir archive
mv students/graduates.txt archive
cp archive/graduates.txt students
mv archive/graduates.txt archive/old_graduates.txt
cd archive
echo  "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut interdum, lectus et vulputate mattis, tortor nisl congue ligula, at vestibulum diam elit sed arcu." > old_graduates.txt
less old_graduates.txt
```

## Задание 3

Создайте папку university. Внутри этой папки создайте файл students.txt, в который поместите следующую информацию. Информация о каждом студенте должна быть на новой строке:
Александра Ивановна Смирнова
Михаил Егорович Петров
МИХАИЛ Алексеевич Соколов
Мария Сергеевна СМирнова
мария Юрьевна Рожкова.
В этой же папке создайте еще 3 пустых файла с названиями faculties.txt, faculties.png, students.png. Ваша задача определить количество строк в итоговой выдаче.

```bash
mkdir university
cd university
touch students.txt
echo  "Александра Ивановна Смирнова" > students.txt
echo  "Михаил Егорович Петров" >> students.txt
echo  "МИХАИЛ Алексеевич Соколов" >> students.txt
echo  "Мария Сергеевна СМирнова" >> students.txt
echo  "мария Юрьевна Рожкова" >> students.txt
touch faculties.txt faculties.png students.png
grep Мария students.txt //кол-во строк: 1
grep -i мария students.txt //кол-во строк: 2
grep -iv мария students.txt //кол-во строк: 3
grep -c Смирнова students.txt //кол-во строк: 1
grep -icv Смирнова students.txt //кол-во строк: 3
find . -name "*.txt" //кол-во строк: 2
find . -name "students.*" //кол-во строк: 2
find . -name faculties.txt //кол-во строк: 1
```

## Задание 4

Создайте файл library.txt и поместите в него следующую информацию:
"Тени прошлого" автора Мария Васильева
"Загадка старинного маяка" автора Иван Петров.
Добавьте информацию о новой книге в этот файл: "Звёздные врата Антареса". Замените информацию в этом файле на предложение "Все книги на данный момент недоступны". Выведите содержимое этого файла в терминал.

```bash
touch library.txt
echo  '"Тени прошлого" автора Мария Васильева' > library.txt
echo  '"Загадка старинного маяка" автора Иван Петров' >> library.txt
echo  "Звёздные врата Антареса" >> library.txt
echo "Все книги на данный момент недоступны" > library.txt
cat library.txt
```

## Задание 5

Выполнить следующие команды: отправить 5 пакетов на сайт stepik.org, отправка пакетов каждые 5 сек на сайт stepik.org, отправка запроса на получение только HTML-разметки stepik.org, отправка запроса на получение полного ответа с сайта stepik.org

```bash
ping -c 5 stepik.org
ping -i 5 stepik.org
curl -L stepik.org
curl -L stepik.org --verbose
```
