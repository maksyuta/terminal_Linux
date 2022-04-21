Termial. HW_2
1. Сделать папку dir_1
```bash
mkdir dir_1
```
 2. Зайти в папку dir_1
 ```bash
cd dir_1
```
 3. Создать папку inner_dir_1
 ```bash 
 mkdir  inner_dir_1
  ```
 4. Посмотреть где ты находишься
  ```bash 
 pwd
  ```
 5. Находясь в папке dir_1 создать пустой текстовый файл tf_1.txt
  ```bash 
touch tf_1.txt 
  ```
 6. Находясь в папке dir_1 через команду cat создать текстовый файл tf_2.txt со следующими строками:
- the first 1
- the second 2
- the third 3
 ```bash 
cat > tf_2.txt
- the first 1
- the second 2
- the third 3 

Ctr+D
  ```
 7. Зайти в папку inner_dir_1
```bash
cd inner_dir_1
```
 8. Через cat сделать текстовый файл tf_3.txt  c любыми строками
 ```bash
 cat > tf_3.txt
 qwe
 asd
 zxc

 Ctr+D
 ```
 9. Через cat добавить в текстовый файл tf_3.txt строку “the second 2”
 ```bash
 cat >> tf_3.txt
 the second 2

 Ctr+D
 ```
 10. Через cat добавить в текстовый файл tf_3.txt строку “the sec 2”
 ```bash
 cat >> tf_3.txt
 the sec 2

Ctr+D
 ```
 11. Через cat добавить в текстовый файл tf_2.txt строку “the sec 3”
 ```bash
  cat >> /d/group_28/dir_1/tf_2.txt
  the sec 3

  Ctr+D
```
 12. Через cat добавить в текстовый файл tf_3.txt строку “the SeCoNd 2”
 ```bash
 cat >> tf_3.txt
 the SeCoNd 2

 Ctr+D
 ```
 13. Через cat добавить в текстовый файл tf_2.txt строку “the seConD 2”
 ```bash
  cat >> /d/group_28/dir_1/tf_2.txt
the seConD 2

Ctr+D
```
 14. Сделать текстовый файл tf_4.txt в котором будет 15 строк.
 ```bash
 cat -b > tf_4.txt
qwe
asd
sdf
sdfsd
fs
dfgdf
ggdf
gdfgdfg
df
gdfg
df
gdf
gdsf
32432
3242

Ctr+D
```
 15. Сделать текстовый файл tF_5.txt в котором будет 13 строк.
 ```bash
 cat -b > tf_5.txt
afsdaf
sdfs
dfgfd
dfg
wer
34543
rdfghdfg
dfgd
sdfhgsdh
sdghgdh
sghfsgfssh
sdfghg
qerqweqw

Ctr+D
```
 16. Вывести список всех файлов в папке.
 ```bash
 find -maxdepth 1 -type f
 ```
 17. Выйти из папки inner_dir_1
 ```bash
 cd ..
 ```
 18. Вывести содержимое файла tf_3.txt в терминал.
 ```bash
 cat inner_dir_1/tf_3.txt
 ```
 19. Найти путь к файлу tf_4.txt
 ```bash
realpath $(find . -name tf_4.txt)
 ```
 20. Очистить файл tf_4.txt от содержимого без удаления самого файла.
 ```bash
  echo > tf_4.txt
  ```
 21. Найти путь к файлам у которых есть  “tf” в названии.
 ```bash
 realpath $(find . -name "tf*")
```
 22. Найти путь к файлам у которых есть  “tf” в названии и буквы в любом регистре.
 ```bash
 realpath $(find . -iname "tf*") 
  ```
 23. Найти строки в файлах где есть комбинация букв “sec” в текущей папке
 ```bash
 grep sec *
 ```
 24. Найти строки в файлах где есть комбинация букв “sec” в любом регистре в текущей папке
 ```bash
 grep -i sec *
 ```
 25. Найти строки в файлах где есть только комбинация букв “sec” в текущей папке
 ```bash
 grep -w sec *
 ``` 
 26. Найти строки в файлах где есть только комбинация букв “sec” в любом регистре в текущей папке
  ```bash
grep -iw sec *
 ``` 
 27. Найти строки в файлах где есть комбинация букв “second” в текущей папке
 ```bash
grep second *
 ```
 28. Найти строки в файлах где есть комбинация букв “second” в любом регистре в текущей папке
  ```bash
 grep -i second *
 ```
 29. Найти строки в файлах где есть комбинация букв “second” во всех папках ниже уровнем
 ```bash
 grep -r second */*
 ```
 30. Найти только путь и название  файла в строках которых есть комбинация букв “second” в текущей папке
 ```bash
grep -l second *
 ```
 31. Найти все строки во всех файлах где нет комбинации “second”
 ```bash
 grep -vr "second" *
 ```
 32. Найти только название и путь к файлам где нет комбинации “second”
```bash
grep -L -r second *
 ```
 33. Вывести в терминал 4 последних строк любого текстового файла
 ```bash
 tail -n 4 tf_5.txt
 ```
 34. Вывести в терминал 4 первые строки любого текстового файла.
 ```bash
 head -n 4 tf_5.txt
 ```
 35. Команда в одну строку. Создать папку и создать текстовый файл с содержиммым.
 ```bash
 mkdir tt1 | echo dsfsdfsdfsd > f_1.txt
 ```
 36. Команда в одну строку. Переместить в любую одну папку текстовые файлы у которых в содержимом есть слово “sec”
 ```bash
 grep -l -r "sec" * | xargs mv -t  ./tt1
 ```
 37. Команда в одну строку. Скопировать в любую одну папку текстовые файлы у которых в содержимом есть слово “sec”
 ```bash
 grep -l -r "sec" * | xargs cp -t  ./tt2
```
 38. Команда в одну строку. Найти все строки c “sec” во всех текстовых файлах, скопировать и вставить эти строки в один новый созданный текстовый файл.
 ```bash
 grep -w -h "sec" * > g2.txt
 ```
 39. Команда в одну строку. Удалить текстовые файлы у которых в содержимом есть слово “sec”
 ```bash
 grep -l -r "sec" * | rm *
 ```
 40. Просто вывести в терминал строку “Good job!!”
 ```bash
 echo 'Good job!!!'
 ```