# Легенда карты

* "@" -- обозначение аватара.
* "1-8" -- обозначение груза с его стоимостью.
* "a-h" -- места куда нужно сложить грузы.
* "█" -- обозначение стены
* " " -- (пробел) пустая клетка

# Условие окончания игры

Условие окончания игры - сложить груз с нужной стоимостью в соответствующую ему ячейку 

1 -> a; 2 -> b; 3 -> c; ... 8 -> h

# Подсчет действий

За одно действие считается шаг в любую сторону(ходить можно только по вертикали или горизонтали) или действие с грузом - поднять /опустить. 

Нельзя за один ход сделать шаг в сторону и провести операцию с грузом.

----

Система знает состояние всей карты и местоположение объектов с самого начала.

Сканирование карты и определение пути не является действием.

# Взаимодействие с грузом

Аватар может взаимодействовать с грузом находящимся в соседней ячейке по вертикали / горизонтали. <br>
Нельзя поднимать груз под собой или складывать его под себя.

Груз можно складывать на любую пустую клетку в лабиринте. <br>
Место для складывания груза также считаются пустой клеткой. 

Два груза не могут лежать на одной клетке.

Аватар может нести за раз только один груз.

Аватар может свободно проходить мимо груза даже если несет груз.

Переносить грузы можно в любом порядке, в любой момент можно поставить груз на пустую клетку и подобрать его или пойти за другим грузом.

# Входные данные и управление

На вход программе указывается путь к текстовому файлу, в котором лежит карта (map1.txt).

Можно вначале просканировать карту и спланировать оптимальный маршрут, а уже после запускать аватара.

Перемещением аватара занимается алогоритм, а не пользователь.

# Вывод программы

Можно написать консольное или оконное приложение - на свое усмотрение.

Визуализацию происходящего процесса поиска путей делать или перемещения аватара в лабиринте делать не обязательно.

При оценке основное внимание будет уделяться эффективности (количество действий аватара) и скорости работы алгоритма.

По окончанию работы требуется вывести для просмотра параметры из раздела "Итоговая оценка".

# Итоговая оценка 

Два независимых параметра.

1) Подсчет количества действий которое совершил аватар.

2) Время работы программы (запуск System.Diagnostics.Stopwatch перед стартом работы программы и остановка в конце.)

# Карта

![map1.txt](map1.txt)

```
█████████████████████████████████████████████████████████████
█ █           █ █                 █   █     █   █       █   █
█ █ █ ███████ █ █ █████████ █████ █ █ █ ███ ███ █ ███ █ █ █ █
█ █ █     █ █ █ █ █       █ █   █   █ █   █   █   █   █   █ █
█ █████ █ █ █ █ █ █ █████ █ █ █ █████ ███ ███ █████ ███████ █
█     █6█ █ █ █   █   █ █ █ █ █     █ █   █ █   █   █   █   █
█████ ███ █ █ ███████ █ █ █ █ █████ █ █ ███ ███ █ ███ █ █ ███
█     █   █ █   █     █   █ █     █     █         █   █ █ █ █
█ █████ ███ ███ █ █████ ███ ███████████ █████████████ █ █ █ █
█       █ █     █ █   █ █             █ █           █ █4█ █ █
█████████ █ █████ █ █ █ █ ███████████ ███ █████████ █ ███ █ █
█   █     █       █ █3█ █ █     █   █     █       █ █   █   █
█ █ █ █████████████ ███ █ █ ███ ███ ███████ █████ █ ███ ███ █
█ █   █       █   █     █   █ █ █   █   █   █     █   █     █
█ █████ █ █████ █ █ █████████ █ █ █ █ ███ ███ ███ ███ █ █████
█   █   █       █ █   █     █     █ █     █   █ █   █ █ █   █
█ █ █ ███████████ ███ █ ███ ███████ █ █████ ███ ███ █ █ █ ███
█ █ █         █ █ █   █ █ █   █     █   █   █       █ █ █   █
███ █████████ █ █ █ ███ █ ███ █ ███████ █ ███████████ █ ███ █
█   █       █   █   █   █   █ █     █   █   █         █   █ █
█ █ █ ███ █ ███ ███████ █ █ █ █████ ███████ █ ███████████ █ █
█ █ █ █   █   █         █ █   █   █       █ █ █         █   █
█ ███ █ █████████████████ ███████ ████  @     █ ███████ ███ █
█ █   █                 █ █     █             █ █         █ █
█ █ ███████████████ ███ █ █ ███ ███ ██abcdefgh█ █████ █████ █
█   █         █ █   █   █ █ █ █   █ ███████████     █   █   █
█ ███ ███████ █ █ █████ █ █ █ ███ █ █ █ █ ███ █ ███ █████ ███
█     █   █   █ █     █ █ █ █   █ █   █   █   █   █     █   █
███████ ███ ███ █████ █ █ █ █ █ █ █████ ███ █████████ █ ███ █
█   █     █   █ █     █ █ █ █ █   █   █   █         █ █   █ █
█ ███ ███ ███ █ █ █████ █ █ ███ ███ █ █ ███████████ ███ █ █ █
█   █ █ █   █ █ █     █5█ █   █     █ █ █     █     █   █ █ █
█ █ █ █ █ █ █ █ █████ ███ █ █ ███████ █ █ ███ █ █████ █████ █
█ █     █ █ █     █ █ █   █ █ █   █   █ █ █     █     █   █ █
█ ███████ ███████ █ █ █ █████ █ ███ ███ █ ███████████ █ █ █ █
█ █     █ █     █   █   █     █   █   █ █ █   █     █   █   █
█ █ ███ █ █ █ █████ ███████ ███ █ ███ █ █ █ █ █ ███ █ ███████
█ █   █ █   █     █         █   █     █ █   █     █ █ █   █ █
█████ █ █████████ ███████████ █████████████████ ███ █ █ █ █ █
█     █           █         █ █ █       █     █ █   █   █   █
█ ███████████████ ███████ █ █ █ █ █ ███ █ ███ █ █ █████████ █
█   █           █     █  1█ █ █ █ █ █2    █   █ █   █     █ █
█ █ ███ █████ █ █████ █ ███ █ █ █ █ ███████ ███████ █ █████ █
█ █   █     █ █   █   █   █ █ █ █ █   █     █       █ █     █
█ ███ ███████ █ ███ ███ █ █ █ █ █ ███ █ ███████ █████ █ █████
█   █   █     █ █   █   █ █ █ █ █ █   █         █     █ █   █
███████ █ ███████ ███████ ███ █ █ █ █████████████ █████ █ ███
█     █ █   █   █         █   █   █       █     █   █   █   █
█ ███ █ █ █ █ █ █████████ █ █████████████ █ ███ █ █ █ █████ █
█   █   █ █   █           █ █           █ █ █ █ █ █ █     █ █
███ █████████ █████ ███████ █ █████████ █ █ █ █ ███ █████ █ █
█   █   █   █ █   █     █   █ █ █       █     █   █     █ █ █
█ ███ █ █ █ ███ █ █ █████ ███ █ █ ███████████████ █ ███ █ █ █
█ █   █ █ █   █ █ █ █     █   █   █     █         █ █   █   █
█ █ ███ █ ███ █ █ █ █ █████ █ █ ███ ███ █ █████████ █ █████ █
█ █   █ █   █   █ █ █ █   █7█ █   █   █   █   █     █     █ █
█ ███ █ ███ █████ █ █ █ █ ███ ███ ███ █████ █ █ ███████ █ █ █
█   █ █  8█ █   █ █ █   █     █   █   █   █ █   █ █     █ █ █
█ ███ █ ███ █ █ █ █████████████ ███ ███ █ █ █████ █ ███████ █
█     █       █ █                   █   █         █         █
█████████████████████████████████████████████████████████████

```
