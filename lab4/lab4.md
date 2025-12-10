# Лабораторная работа № 4

## Задание 1-2: Знакомство со справочной системой
```cmd
help Get-Command              # Полная справка по команде Get-Command
Get-Command                   # Список всех доступных команд в PowerShell
```
![Disk Partitioning](img/1.png)

## Задание 3-4: Работа с сервисами и процессами
```cmd
Get-Service                   # Список всех сервисов на компьютере
Get-Process                   # Список всех запущенных процессов
```
![Disk Partitioning](img/2.png)
![Disk Partitioning](img/3.png)

## Задание 5: Фильтрация процессов
```cmd
Get-Process explorer          # Информация о процессе explorer
Get-Process w*                # Все процессы, начинающиеся на "w"
```
![Disk Partitioning](img/4.png)
![Disk Partitioning](img/5.png)

## Задание 6: Форматирование вывода
```cmd
Get-Process i* | Format-List    # Вывод в формате списка
Get-Process i* | Format-Wide    # Широкий формат
Get-Process i* | Format-Custom  # Пользовательский формат
help format*                    # Справка по командам форматирования
```
![Disk Partitioning](img/6.png)
![Disk Partitioning](img/7.png)
![Disk Partitioning](img/8.png)
![Disk Partitioning](img/9.png)

## Задание 7: Изучение свойств объектов
```cmd
Get-Process | Get-Member      # Показать все свойства и методы объектов Process
```
![Disk Partitioning](img/10.png)

## Задание 8: Фильтрация и сортировка
```cmd
# Фильтрация процессов с handlecount > 400
Get-Process | Where-Object {$_.handlecount -gt 400}

# Сортировка отфильтрованных процессов по Handles
Get-Process | Where-Object {$_.handlecount -gt 400} | Sort-Object Handles
```
![Disk Partitioning](img/11.png)
![Disk Partitioning](img/12.png)

## Задание 9: Сортировка по памяти и выбор топ-5
```cmd
Get-Process | Sort-Object -Property WS -Descending | Select-Object -First 5
```
![Disk Partitioning](img/13.png)

## Задание 10: Управление процессами
```cmd
# Запуск Notepad (Блокнот)
notepad

# Остановка процесса Notepad
Get-Process notepad | Stop-Process

# Запуск Notepad снова
notepad

# Тестовый режим (что если)
Get-Process notepad | Stop-Process -WhatIf

# Режим подтверждения
Get-Process notepad | Stop-Process -Confirm
```
![Disk Partitioning](img/14.png)
![Disk Partitioning](img/15.png)

## Задания 11-18: Работа с файловой системой
```cmd
# 11. Создание каталога
New-Item TextFiles -ItemType Directory

# 12. Создание файлов
New-Item psdemo.txt -ItemType File
New-Item 1.txt -ItemType File
New-Item 2.txt -ItemType File

# 13. Копирование файлов
Copy-Item -Path '.\*.txt' -Destination '.\TextFiles'

# 14. Переход в каталог
Set-Location TextFiles

# 15. Переименование файла
Rename-Item psdemo.txt psdemo.bak

# 16. Перемещение файла на уровень выше
Move-Item psdemo.bak ..\

# 17. Возврат на уровень выше
Set-Location ..

# 18. Удаление каталога с содержимым
Remove-Item TextFiles -Recurse
```
![Disk Partitioning](img/16.png)
![Disk Partitioning](img/17.png)
![Disk Partitioning](img/18.png)
![Disk Partitioning](img/19.png)
