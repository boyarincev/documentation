# Job Interviews

## Резюме

Резюме глазами интервьюера

{% embed url="https://habr.com/ru/company/tinkoff/blog/474894/" %}

## Темы в которых нужно разбираться Backend девелоперу

{% embed url="https://roadmap.sh/backend" %}



## Статьи о проведении собеседований

Собеседуем кандидата на должность Senior Software Developer

{% embed url="https://habr.com/ru/post/469403/" %}

Тестовые задания на собеседовании разработчика — есть ли в них смысл?

{% embed url="https://habr.com/ru/post/469099/" %}

Senior Engineer в поисках работы. О задачах на технических собеседованиях и теоретических вопросах

{% embed url="https://habr.com/ru/post/442442/" %}

Senior Engineer в поисках работы. Как я прошел 20 собеседований с HR и что я об этом думаю

{% embed url="https://habr.com/ru/post/430222/" %}

Senior Engineer в поисках работы. Как я прошел 15 технических собеседований и что я об этом думаю

{% embed url="https://habr.com/ru/post/434864/" %}

## Сервисы для онлайн-кодинга на собеседовании

[coderpad.io ](https://coderpad.io/)- Две онлайн-комнаты в месяц бесплатно (закрываются через 4 дня, можно успеть провести несколько собеседований)

[repl.it](https://repl.it/) - Тут без ограничений на количество сессий в месяц, но на бесплатном тарифе всего 2 онлайн пользователя

## Подготовка к собеседованиям .NET

Информация о том, что спрашивают на собеседованиях в Москве на сеньора.

{% embed url="https://habr.com/ru/post/500430/" %}

&#x20;Список далеко не полон, однако, я постарался собрать наиболее частотные вопросы. Так как я позиционируюсь как «бэк-энд», то и вопросы были соответствующие.

* Для затравки идут ссылочные и значимые типы, где размещаются, отличия, преимущества, недостатки. И всегда ли классы в куче? Всегда ли структуры на стеке?
* Наследование и полиморфизм в задачках, когда что-то от чего-то унаследовано с нарушением здравого смысла (за такое в продакшене руки отрывают) и нужно догадаться, что сделает программа.
* Дают код, в котором происходит Boxing и unboxing, и надо сказать, что будет в результате. За такой код тоже руки надо отрывать, и в реальной жизни он не встречается, но ответить надо.
* SOLID, KISS, DRY, YAGNI своими словами.
* GC. Куда же без него, родимого. Начинают с общих принципов работы, которые, однако, надо знать в деталях. Маркировка, сжатие. Поколения. Очередь финализации.\
  После теоретических вопросов переходят к описанию двух-трех проблем и спрашивают, как с ними бороться на практике. От общих вопросов, типа что будет при большом количестве создаваемых объектов и до специфических проблем при работе с большими объектами.
* IoC/DI
* WCF, REST API
* async/await
* Микросервисы — обзорно. Наиболее часто спрашивали аутентификацию/авторизацию.
* Порассуждать на тему индексов и транзакций в SQL Server и написать простенький запрос на SQL. Если позиция предполагает серьезные знание SQL, то спрашивают про оптимизацию запросов, выявлению узких мест, в частности, работу с планом запроса
* Потоки и синхронизация. Monitor, Mutex, Semaphore, AutoResetEvent, ReaderWriterLock. Неплохо еще знать Slim версии объектов. Конечно же Interlocked и volatile. Причем ответы на вопросы о потоках и объектах синхронизации очень, ну просто очень весомы. По ним определяют степень «синьористости». Кроме теоретических вопросов обычно просят сделать набросок решения какой-нибудь несложной задачи. Например, сделать, чтобы первый поток выводил на консоль «ping», а второй — «pong», и делали бы они это строго по очереди.

\
Для подготовки к интервью неплохо бы полистать Рихтера «CLR via C#» (да, да, он все еще актуален) и написать тестовую задачку, типа реализации «поставщик/потребитель» на Monitor, а потом то же самое на AutoResetEvent. Это покроет 80% вопросов.

## Подготовка к собеседованиям в крупные компании

### Подготовился за два месяца

{% embed url="https://habr.com/ru/post/682358/" %}

### История как девушка готовилась к собеседованиям в FAANG

{% embed url="https://habr.com/ru/post/499394/" %}

Рассказывает как готовилась к алгоритмическому этапу, поведенческому и собеседованию по System Design

### Другая девушка в FAANG

{% embed url="https://habr.com/ru/post/569522/" %}

**Roadmap задач**

Я старалась решать по 2-4 задачи в будний день из разных разделов, это примерно 4 часа в день до/после работы. Например, одна на строки, другая на графы. Разделам, где я проседала больше, выделяла отдельное время - в частности, на динамическое программирование. Полностью вся суббота и часть воскресенья уходили на подготовку. Будьте к этому готовы, подготовка съест очень много вашего личного времени. На текущий момент у меня 352 задачи:![](https://habrastorage.org/r/w1560/getpro/habr/upload\_files/ca9/536/c90/ca9536c908f265c13958cbaff66c974d.png)

В таком режиме важен таймлайн - не можете решить задачу за 1-3 часа, смотрим хинты, непонятно как решать даже с хинтами, смотрим и разбираем решение. И да, купите премиум! Оно того стоит: у вас будут доступны фильтры задач по компании, решения, закрытые популярные задачи, тестовые подборки для собеседований. Параллельно я просматривала задачи из [Cracking The Coding Interview](https://www.amazon.com/Cracking-Coding-Interview-Programming-Questions/dp/0984782850) c точки зрения подхода решения. Есть еще неплохая подборка с паттернами для решения задач [Patterns for Coding Questions](https://www.educative.io/courses/grokking-the-coding-interview). Так прошло 4.5 месяца, нужно было начинать готовится в System Design.\
\
Какие топики обязательно надо покрыть (по-моему мнению):

1. [DP](https://leetcode.com/tag/dynamic-programming/): одномерный ([Coin Change](https://leetcode.com/problems/coin-change/), [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)), двумерный ([Unique Paths](https://leetcode.com/problems/unique-paths/), [Dungeon Game](https://leetcode.com/problems/dungeon-game/)), трехмерный ([Cherry Pickup](https://leetcode.com/problems/cherry-pickup/), [Cherry Pickup II](https://leetcode.com/problems/cherry-pickup-ii/));
2. Графы: [DFS](https://leetcode.com/tag/depth-first-search/) и [BFS](https://leetcode.com/tag/breadth-first-search/) надо прям так, чтобы если вас разбудят среди ночи, вы их напишите. Алгоритм Дейкстры, как находит шарнирные точки, мосты, циклы. Рассмотреть задачи на BFS + Binary Search ([Swim in Rinsing Water](https://leetcode.com/problems/swim-in-rising-water/));
3. [Heap/Priority Queue](https://leetcode.com/tag/heap-priority-queue/);
4. Матрицы: обходить змейкой, по диагонали, звездочкой и как угодно;
5. Задачи [бинарного поиска](https://leetcode.com/tag/binary-search/);
6. RMQ: Fenwick tree, [Segment tree](https://leetcode.com/articles/a-recursive-approach-to-segment-trees-range-sum-queries-lazy-propagation/) (есть хорошее объяснение на канале у [Tushar Roy](https://www.youtube.com/channel/UCZLJf\_R2sWyUtXSKiKlyvAw));
7. Задачи на [sliding window](https://leetcode.com/tag/sliding-window/), [prefix sums](https://leetcode.com/tag/prefix-sum/), [stack](https://leetcode.com/tag/stack/), [recursion](https://leetcode.com/tag/recursion/) (вот тут надо уметь в [Master Theorem](https://www.youtube.com/watch?v=OynWkEj0S-s))

**System Design**

До этого я читала [GoF](https://www.amazon.com/Design-Patterns-Object-Oriented-Addison-Wesley-Professional-ebook/dp/B000SEIBB8) (у меня даже какой-то курсач в универе по паттернам был), [книгу](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420) Фаулера (подписана на его [блог](https://martinfowler.com/) и слежу за статейками там). Я очень волновалась именно за системный дизайн, потому что опыта проектирования highload систем у меня не было, но именно эта секция в Google прошла у меня лучше всего. Я знаю базовые вещи: про OSI, балансеры, LRU/LFU cache, ACID и т. д. Но нужно уметь четко выделять точки отказа в системе, как лучше шардировать данные, проектирование read heavy vs write heavy приложений и уметь донести свою мысль интервьюеру, что очень важно. В итоге, я прошла курс [Grokking the System Design](https://www.educative.io/courses/grokking-the-system-design-interview) - хайли рекоменд, прочитала [Alex Xu, System Design Interview](https://www.amazon.com/System-Design-Interview-insiders-Second/dp/B08CMF2CQF) и половину книги [Designing Data-Intensive Applications](https://www.amazon.com/Designing-Data-Intensive-Applications-Reliable-Maintainable/dp/1449373321/ref=pd\_lpo\_14\_img\_0/136-6629283-9009906?\_encoding=UTF8\&pd\_rd\_i=1449373321\&pd\_rd\_r=3c536e21-9782-455c-9308-2ac6b6916af1\&pd\_rd\_w=QEXB6\&pd\_rd\_wg=hkXtD\&pf\_rd\_p=fb1e266d-b690-4b4f-b71c-bd35e5395976\&pf\_rd\_r=4Q9DVDPMPNDQM602R2DK\&psc=1\&refRID=4Q9DVDPMPNDQM602R2DK) (она очень интересная и стоящая, но мне не пригодилась). Есть еще более углубленный курс на educative - [Grokking the Advanced System Design](https://www.educative.io/courses/grokking-adv-system-design-intvw).![](https://habrastorage.org/r/w1560/getpro/habr/upload\_files/c78/88c/cd0/c7888ccd03e1c3711409c7400b481912.jpeg)

Если у вас опыт только, как фронтенд разработчика, и вы не умеете в reverse proxy и зеркалирование в nginx, начать советую с этого. Напишите маленькое приложение на бекенде, настройте балансер, потрогайте ACL (можно даже через битовые маски реализовать, чтобы и битовые операции вспомнить).

**Behavioral**

Моей ошибкой было то, что я особо к нему не готовилась, а стоило. Я бы предложила взять [Leadership Principles](https://www.amazon.jobs/en/principles) Амазон и расписать в доке конкретные ситуации с примерами и быть готовым красиво выкатить ответ, когда вас спросит про ownership, пример вашего achievement, disagreement с менеджером и пару десятков часто задаваемых вопросов. Тут не буду советовать того, чего не смотрела/читала. Советую обратить внимание на [док](https://docs.google.com/document/d/1UIMSw6KkL6z7t\_ATpKUdQWe5xPxCYXGjVWNY3BbLBx8) сообщества подготовки в FAANG. Есть еще неплохой список топиков на [leetcode](https://leetcode.com/explore/interview/card/leapai/).

**Mock-собеседования**

Ребята из [канала подготовки в FAANG](https://t.me/FaangInterview) в телеге проводят mock-собеседования (только на английском). Cтоит сходить, когда у вас есть хотя бы 100 задач leetcode. Вам подберут других ребят по схожему количеству задач, очень помогает научиться правильно проговаривать ход своих мыслей и объяснять ход решения другому человеку. Это не тоже самое, что mock interview test на leetcode. Группа очень полезна, в [доке сообщества](https://docs.google.com/document/d/1UIMSw6KkL6z7t\_ATpKUdQWe5xPxCYXGjVWNY3BbLBx8) куча информации по подготовке - советую ее прочитать и начать оттуда. Рефералов можно тоже поискать в группе или на LinkedIn/Blind, но у вас должно быть прорешено определенное количество задач. И пожалуйста, если будете присоединяться в группу - прочитайте сначала закрепленные сообщения, правила и начните с доки, вы найдете там ответы на большую часть ваших вопросов, не стоит сразу писать в чат, а с чего же стоит начать и что делать.

**Подготовка резюме**

Очень важно подготовить резюме и уместить все ваши достижения на максимум 2 страницы, а лучше 1.5, никто не будет читать ваши 15 страниц жизни, начиная с первого приложения "Hello World!".\
\
Резюме нужно оформить в формате goals and achievements, а не списком технологий. Почитать можно [тут](http://larrr.com/primer-horoshego-rezyume/), шаблон взять [отсюда](https://www.careercup.com/resume). Еще хорошие шаблоны [тут](https://github.com/darhonbek/resume\_templates). В телеге [в этом канале](https://t.me/resume\_review) можно попросить ребят поревьюить ваше резюме.\
\
И тут сейчас будет мой факап, у нас проблемы Хьюстон!Я опечаталась в своем email при первой подаче через реферала, ситуация смешная и одновременно страшная. Вывод: всегда внимательно проверяйте контакты (раз 5) и дайте кому-то почитать перед отправкой.

#### Ссылки и материалы

1. [Группа](https://t.me/FaangInterview) по подготовке в FAANG и [док сообщества](https://docs.google.com/document/d/1UIMSw6KkL6z7t\_ATpKUdQWe5xPxCYXGjVWNY3BbLBx8)
2. [Группа](https://t.me/resume\_review) по ревью резюме
3. Блог [Ларисы Агарковой](http://larrr.com/) и ее хороший [гайд по подготовке](http://larrr.com/wp-content/uploads/2016/10/InterviewPreparationGuide.pdf), можно еще [интервью](https://www.youtube.com/watch?v=i\_jIzbSI9MQ) посмотреть
4. Ютуб-канал [Tuchar Roy](https://www.youtube.com/channel/UCZLJf\_R2sWyUtXSKiKlyvAw)
5. Курс по [System Design](https://www.educative.io/courses/grokking-the-system-design-interview)
6. Курс по [Advanced System Design](https://www.educative.io/courses/grokking-adv-system-design-intvw)
7. Курс [Patterns for Coding Questions](https://www.educative.io/courses/grokking-the-coding-interview)
8. Книга [Alex Xu, System Design Interview](https://www.amazon.com/System-Design-Interview-insiders-Second/dp/B08CMF2CQF)
9. Книга [Designing Data-Intensive Applications](https://www.amazon.com/Designing-Data-Intensive-Applications-Reliable-Maintainable/dp/1449373321/ref=pd\_lpo\_14\_img\_0/136-6629283-9009906?\_encoding=UTF8\&pd\_rd\_i=1449373321\&pd\_rd\_r=3c536e21-9782-455c-9308-2ac6b6916af1\&pd\_rd\_w=QEXB6\&pd\_rd\_wg=hkXtD\&pf\_rd\_p=fb1e266d-b690-4b4f-b71c-bd35e5395976\&pf\_rd\_r=4Q9DVDPMPNDQM602R2DK\&psc=1\&refRID=4Q9DVDPMPNDQM602R2DK)
10. Книга [Cracking The Coding Interview](https://www.amazon.com/Cracking-Coding-Interview-Programming-Questions/dp/0984782850)

## Неструктурированная информация

4 толковых канала на Youtube про технические собеседования

{% embed url="https://habr.com/ru/post/454264/" %}

[Подготовка к собеседованиям в кремниевой долине](https://habrahabr.ru/company/edison/blog/344018/)

[Как подготовиться к собеседованию в Google и не пройти его. Дважды](https://habr.com/ru/post/419945/)

> Алгоритмические задачи
>
> Это наверное был самый интересный пункт подготовки. Можно, конечно, сесть и тупо решать задачи. Для этого есть много разных сайтов. Я в основном использовал три: Hackerrank, CodeChef и LeetCode. На CodeChef задачи разбиты по сложности, но не по темам. На Hackerrank и по сложности, и по темам.

\-Подскажите, пожалуйста, на каких по сложности задачах с hackerrank лучше тренироваться (имеется в виду practice, не соревнования на время)? Medium или Hard уже? На самих интервью какой приблизительно сложности алгоритмические задачи были?

\-Если смотреть Hackerrank, то интервью ближе к Medium, может между Medium и Hard. Если смотреть Leetcode, то Medium и Hard. Leetcode в принципе полегче

[Список сервисов задачников](https://habr.com/ru/company/hexlet/blog/434786/)

Ещё один сервис: [https://www.lintcode.com/problem/](https://www.lintcode.com/problem/)

Подготовка к собеседованию в яндекс на Javascript: [https://habr.com/ru/post/470337/](https://habr.com/ru/post/470337/)

> Если кому интересно, как подготовиться к собесу в Яндекс (и не только) на JS разработчика и попасть на младшего разработчика, то вот примерный список:
>
> Что читать:
>
> learn.javascript.ru
>
> developer.mozilla.org
>
> maxpfrontend.ru/vebinary/voprosy-dlya-sobesedovaniya-javascript-razrabotchika
>
> Что знать:
>
> Event loop, очередность вывода setTimeout, promise
>
> Async/await
>
> call, bind, apply
>
> замыкания и область видимости
>
> hoisting
>
> ES6
>
> Передача по ссылке и по значению
>
> Генераторы и итераторы
>
> Как работает spread/rest
>
> Армия функций, различия let, const, var
>
> Все это с примерами в коде, чтобы было понимание.

{% embed url="https://habr.com/ru/post/563188/" %}

{% embed url="https://habr.com/ru/post/564852/" %}



## Вопросы на собеседовании со стороны собеседуемого

Правильные вопросы на собеседовании: [https://habr.com/ru/post/468923/](https://habr.com/ru/post/468923/)
