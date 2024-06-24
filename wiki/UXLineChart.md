## Описание
Класс позволяет отрисовывать графики на координатной плоскости.
## Использование
```php
$x = new UXNumberAxis();
$y = new UXNumberAxis();
$chart = new UXLineChart($x, $y);
$chart->title = "График косинусов и синусов";
$x->label = 'X';
$y->label = 'Y';
```
Мы создали график и передали ему в конструктор две оси.
Затем задали название для графика и осей.
```php
$sin = new UXXYChartSeries();
$sin->name = 'Синус';
$cos = new UXXYChartSeries();
$cos->name = 'Косинус';
```
Далее мы создали два контейнера для точек нашего графика и дали им имена.
Класс **UXXYChartSeries** содержит в себе данные о расположении точек.
```php
for($i = 0; $i < 20; $i++){
  $sin->chartData->add(new UXXYChartData($i, sin($i)));
  $cos->chartData->add(new UXXYChartData($i, cos($i)));
}
```
Наконец мы задали данные для нашего графика используя **UXXYChartData**.
Данный класс принимает на вход два аргумента. Во всех графиках кроме UXPieChart,UXBarChart и UXStackedBarChart на вход передаются два числа.
```php
$chart->series->addAll([$sin, $cos]);
```
Здесь мы добавили "наборы точек" в график, используя свойство **series**.
## Заключение
Вот, что мы имеем на выходе:

![UXLineChart](https://github.com/jphp-group/jphp-charts-ext/raw/master/examples/images/line_chart.png)
## Пример
https://github.com/jphp-group/jphp-charts-ext/blob/master/examples/src/charts/UXLineChartExample.php