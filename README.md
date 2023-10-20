# Задание для кафедры 1С

Сенин Игорь Александрович, группа Б05-121



#### Сборка

Проект небольшой, поэтому разумно собирать его напрямую:

```bash
g++ -lstdc++fs -std=c++17 main.cpp -o a.out
```

Рекомендуемая версия g++ - от 8.0.0; при версиях ниже не сборка гарантируется.



#### Запуск

Например, можно запустить так:

```bash
./a.out test_suites/dir_1 test_suites/dir_2 31.41592
```



#### Описание

В качестве значения сходства двух строк используется длина наибольшей общей подпоследовательности; в частности, она сходится с данным примером. Подсчёт выполняется динамическим программированием; *оптимизация* - если на каком-то шаге уже понятно, что нужного значения не достичь, останавливаем подсчёт.

Может быть ситуация, когда несколько файлов в первой и второй директориях идентичны. Тогда для следующего равного файла можно не продолжать цикл и скопировать информацию первого файла.

Также уместно сначала проверять равенство хэшей, и только потом сами строки.

Интерфейс файлов представляется классом ```File```.
