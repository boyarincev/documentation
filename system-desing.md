# System Desing

>  Пожалуй, это тип собеседования, для которого нет «царской дороги». Надо заметить, что до этого у меня был нулевой опыт в проектировании распределённых систем. Информации по подготовке к system design собеседованию в разы меньше, чем к алгоритмическому. Всё усугубляется тем, что люди, которые публикуют разборы таких задач, часто сами не обладают релевантным опытом. Тем не менее, воодушевлённая паттернами для алгоритмического собеседования, я начала искать что-то похожее и нашла[ платный курс](https://www.educative.io/courses/grokking-the-system-design-interview), который казался простым и эффективным… до первого собеседования, где я поняла, что он очень поверхностный. Там не обсуждалось ни reverse proxy, ни content delivery network, про которые хотели услышать мои интервьюеры. Хватило его только на «троечку». Это, с одной стороны, помогло — позволило получить оффер, при условии, что все остальные части были пройдены хорошо. А с другой — срезало уровень предлагаемой должности, так как этот этап важен для оценки «сениорности» кандидата. Ну и так как все сессии очного этапа суммируются, то лучше не терять здесь баллов — их может просто не хватить для положительного результата.\
> \
> Во время дальнейшей подготовки я наконец-то нашла отличный[ бесплатный ресурс](https://github.com/donnemartin/system-design-primer). Он тоже довольно краткий — читается за несколько часов, но к каждой части есть ссылки для углубления в материал. Это отличная стратегия вне зависимости от количества времени, которое есть в наличии: можно начать с краткого обзора, а потом изучить подробнее.\
> \
> Об этой подборке с гитхаба я узнала из письма с материалами для подготовки, которые мне прислал рекрутер. Это ценный источник, о котором не следует забывать. Некоторые из высылаемых ресурсов могут оказаться лучше подборок из статей вроде этой.

Цитата из статьи

{% embed url="https://habr.com/ru/post/499394/" %}



{% embed url="https://github.com/donnemartin/system-design-primer" %}

{% embed url="https://habr.com/ru/post/516604/" %}

```
Latency Comparison Numbers (~2012)
----------------------------------
L1 cache reference                           0.5 ns
Branch mispredict                            5   ns
L2 cache reference                           7   ns                      14x L1 cache
Mutex lock/unlock                           25   ns
Main memory reference                      100   ns                      20x L2 cache, 200x L1 cache
Compress 1K bytes with Zippy             3,000   ns        3 us
Send 1K bytes over 1 Gbps network       10,000   ns       10 us
Read 4K randomly from SSD*             150,000   ns      150 us          ~1GB/sec SSD
Read 1 MB sequentially from memory     250,000   ns      250 us
Round trip within same datacenter      500,000   ns      500 us
Read 1 MB sequentially from SSD*     1,000,000   ns    1,000 us    1 ms  ~1GB/sec SSD, 4X memory
Disk seek                           10,000,000   ns   10,000 us   10 ms  20x datacenter roundtrip
Read 1 MB sequentially from disk    20,000,000   ns   20,000 us   20 ms  80x memory, 20X SSD
Send packet CA->Netherlands->CA    150,000,000   ns  150,000 us  150 ms

Notes
-----
1 ns = 10^-9 seconds
1 us = 10^-6 seconds = 1,000 ns
1 ms = 10^-3 seconds = 1,000 us = 1,000,000 ns

Credit
------
By Jeff Dean:               http://research.google.com/people/jeff/
Originally by Peter Norvig: http://norvig.com/21-days.html#answers

Contributions
-------------
'Humanized' comparison:  https://gist.github.com/hellerbarde/2843375
Visual comparison chart: http://i.imgur.com/k0t1e.png
```

Источник: [https://gist.github.com/jboner/2841832](https://gist.github.com/jboner/2841832)

{% embed url="https://habr.com/ru/company/gms/blog/516718/" %}

