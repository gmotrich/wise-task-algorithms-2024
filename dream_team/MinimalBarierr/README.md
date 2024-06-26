Проверка на то, являеются ли отмеченные вершины минимальным барьером графа

Основные понятия:
* odd(G) — число нечетных компонент связности в графе G, где нечетная компонента (англ. odd component) — это компонента связности, содержащая нечетное число вершин.
* Дефицитом (англ. deficit) графа G мы будем называть величину: def(G)=|V|−2α(G), где α(G) — размер максимального паросочетания в G
, а V(G) — множество вершин графа G.
* Множество S⊂V(G), для которого odd(G−S)−|S|=def(G), называется барьером (англ. barrier).

* Минимальным по включению барьером (англ.minimal barrier) называется барьер, который перестанет быть барьером при исключении из него любой вершины.

Методы:
* Сначала идёт проверка графа на двудольность в методе isBipartide (пытаемся раскрасить вершины в два цвета так, чтобы смежные вершины были разных цветов. Если на каком-то шаге не получается это сделать - возвращаем false)

* Поиск максимального паросочетания - метод findMaxMatchingSize - с помощью вспомогательного метода dfs(обхода в глубину) по алгоритму Куна
* Метод odd вычисляет количество нечётных компонент для переданного в него набора вершин (Не для всего графа!!!)
* В основном методе execute вычисляется дефицит и количество нечётных компонент в подграфе из невыделенных вершин. Проверяется, что выделенные красные вершины действительно являеются барьером.
* Создаём массив для вершин. Далее в для всех вершин в барьере: присваиваем массиву значения всех вершин не в барьере + текущая вершина из барьера. Пересчитываем для них odd, если odd стало на 1 меньше своего начального значения - значит множество без этой вершины тоже барьер, т.е. заданный барььер не является минимальным.

Примечание:
* Вершины барьера должны быть отмечены красным.