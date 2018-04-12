# Balls & boxes

В тази задача ще трябва да имплементирате класове за топки и кутии. Основните класове са:
*   `org.elsys.part1.Ball` -- класът за топка, която се характеризира с обем и цвят.
*   `org.elsys.part1.BallContainer` -- контейнер за топки, който предоставя различни методи за достъп, добавяне, премахване на топки и други.
*   `org.elsys.part1.Box` -- вид контейнер за топки, който обаче има максимален обем.

## Задачи

### 1. `Ball`, `BallContainer` и `Box`

Имплементирайте коректно методите в трите класа. За да сте сигурни, че методите са имплементирани коректно, трябва да изпълните JUnit тестовете, които се намират в папката `test`.

#### 1.1 `Ball`

`Ball` трябва да има два конструктора. Топки, които са създадени с конструктора само с един параметър, трябва да бъдат бели на цвят.
Дефинирайте в класа полета за обем (`volume`) от тип `double` и за цвят (`color`) от тип `org.elsys.part1.Color`.
Дефинирайте методи за достъп до полетата на класа (getVolume, setVolume, getColor, setColor).

#### 1.2 `BallContainer`

За имплементацията на `BallContainer` може да използвате колекция от стандартната библиотека по ваш избор. За всеки метод в кода е добавено описание какво трябва да върши (посредством Java Doc). Обърнете внимание на метода `getVolume()` и помислете как най-ефективно бихте могли да го реализирате.

#### 1.3 `Box`

`Box` е вид `BallContainer` с максимален капацитет (т.е. вторият е родител на първия). Трябва да се имплементира, така че добавянето на по-голям обем топки от максималния капицитет да е невъзможно. Когато добавянето на топка е невъзможно, методът за добавяне трябва да хвърля изключението `BallContainerException`.

`Box` дефинира и един допълнителен метод. Това е `getBallsFromSmallest()` и той трябва да връща `java.util.Iterator`, чрез който да могат да се итерират всички топки, започвайки от най-малката. За сортиране използвайте имплементираното в стандартната библиотека, а не имплементирайте свое.

### 2. main метод

Дефинирайте main метод в класа **org.elsys.main.MainClass**.
Той трябва да прави следното:
  * прочита линия от стандартния вход, която ще съдържа числа, разделени със спейс (напр: `"12 3 300 1"`)
  * за всяко число в низа създава топка; ако числото се дели на 2 топката трябва да е бяла, ако не - черна
  * добавя топките в инстанция на `Box` с фиксиран размер 100
  * след това итерира топките чрез метода `getBallsFromSmallest` и ги добавя в инстанция на `BallContainer`
  * проверява дали броят на топките в двата контейнера е един и същ и ако е, изписва "success" на стандартния изход

### 3. `UniqueBallContainer`

Този клас трябва да имат същите свойства като `BallContainer` с разликата, че може да съдържа само една топка от определен цвят и обем.

Класът в момента е празен и не наследява никакви други класове. Ваша задача е да прецените кой друг клас (от тези дефинирани в първата част или някой нов ваш клас) би наследил, какви методи би дефинирал и предефинирал, така че да няма повтаряне на един и същ код на повече от едно място.

Друга специфична част е, че трябва да решите дали този клас да ползва същата като `BallContainer` и `Box` колекция, или някаква друга, която е по-подходяща.

За тази част няма включени JUnit тестове и трябва да имплементирате сами такива за методите `add` и `getVolume`.