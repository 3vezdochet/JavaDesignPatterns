<h1 align="center">
   Decorator
</h1>
<h3 align="center">
   Декоратор
</h3>

**Декоратор** — это структурный паттерн проектирования, который позволяет динамически менять функциональность объектов,
оборачивая их в полезные «обёртки».

Паттерн декоратор является лучшим примером когда использование композиции превосходит наследование.

Примеры, когда можно использовать паттерн декоратор:

1. Когда вы хотите добавить, улучшить или, возможно, удалить поведение или состояние объекта.
2. Когда вам нужно изменять обязанности объектам на лету, незаметно для кода, который их использует.
3. Когда нельзя расширить обязанности объекта с помощью наследования.
4. Когда вы просто хотите изменить функциональность одного конкретного объекта класса, а остальные оставить без
   изменений

<h3 align="center">
   Реализация
</h3>

1. Убедитесь, что в вашей задаче есть один основной компонент и несколько опциональных дополнений или надстроек над ним.
2. Создайте интерфейс компонента, который описывал бы все общие методы как для основного компонента, так и для его
   дополнений.
3. Создайте класс конкретного компонента и поместите в него основную бизнес-логику
4. Создайте базовый класс декораторов. Он должен иметь поле для хранения ссылки на вложенный объект-компонент. Все
   методы базового декоратора должны делегировать действие вложенному объекту.
5. И конкретный компонент, и базовый декоратор должны следовать одному и тому же интерфейсу компонента.
6. Теперь создайте классы конкретных декораторов, наследуя их от базового декоратора. Конкретный декоратор должен
   выполнять свою добавочную функциональность, а затем   (или перед этим) вызывать эту же операцию обёрнутого объекта.
7. Клиент берёт на себя ответственность за конфигурацию и порядок обёртывания объектов.

<h3 align="center">
   Decorator UML-диаграмма
</h3>

![diagram.png](diagram.png)

<h3>Плюсы</h3>

- Большая гибкость, чем у наследования.
- Позволяет добавлять обязанности на лету.
- Можно добавлять несколько новых обязанностей сразу.
- Позволяет иметь несколько мелких объектов вместо одного объекта на все случаи жизни.
- Паттерн проектирования декоратор чаще всего используется для следования принципу единой ответственности (single
  responsibility из SOLID), поскольку мы не нагружаем исходный класс дополнительными обязанностями, а разделяем их на
  классы-декораторы.

<h3>Минусы</h3>

- Трудно конфигурировать многократно обёрнутые объекты.
- Обилие крошечных классов.

<h3 align="center">
   Примеры
</h3>

- Все библиотеки ввода-вывода **IO** и **NIO** в **Java** это яркий пример удачного использования декоратора.
- [JavaRush: Паттерн проектирования декоратор с примерами.](https://javarush.com/groups/posts/3833-pattern-proektirovanija-dekorator-s-primerami)
- [Добавления и урезания функционала на примере пиццы](code)

<h3 align="center">
   Источники
</h3>

- Design Patterns with
  Java: [Decorator](books/Olaf%20Musch%20EN.pdf)
- Введение в паттерны
  проектирования: [Декоратор](books/Alexander%20Shvets%20RU.pdf)