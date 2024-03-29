# Algorithms

## Рекомендации по изучению

[https://habr.com/ru/post/518372/](https://habr.com/ru/post/518372/)

1\.

 [codewars.com](https://codewars.com)\
[app.codesignal.com](https://app.codesignal.com)\
[leetcode.com](https://leetcode.com)\
\
Теория\
[aliev.me/runestone](http://aliev.me/runestone/)\
\
Книга по Питону\
[pythonworld.ru/uploads/pythonworldru.pdf](https://pythonworld.ru/uploads/pythonworldru.pdf)\
\
Виртуальная среда питона для теста\
[repl.it/languages/python3](https://repl.it/languages/python3)\
\
Уже больше года прохожу разные алгоритмы, встретил задачу — решил на листочке — отточил — прошел тесты\
\
Гугл — лучший помощник. Тесты — лучший ревьювер. Чужие решения — лучший мотиватор.\
\
Добавьте еще пару пет-проектов и будет круто

2\.

Есть замечательный курс от ИТМО на открытом образовании. Там куратор Максим Буздалов (если не ошибаюсь). Вот там курс именно на алгоритмы — сортировки, кучу, деревья, строки. И задачи реально на эти темы. (Во многом совпадают с курсом по алгоритмам в самом ИТМО) В общем советую. А leetcode для всех открыт.

Оставлю ссылку openedu.ru/course/ITMOUniversity/PADS Единственный момент, в 2017 году, когда я проходил, графов не было. Может сейчас добавили.

Графы были добавлены как отдельный курс. Но там автор другой, но тоже от ИТМО.

А, значит ничего не поменялось. Я начал было проходить, но он мне не понравился

3\.

 В целом, я считаю, что алгоритмы можно подтянуть самостоятельно.\
Оставлю пару ссылок\
[codeforces.com/edu/courses](https://codeforces.com/edu/courses)\
[algoprog.ru](http://algoprog.ru) (платный: 2 тысячи рублей/месяц)\
[stepik.org/course/217/syllabus](https://stepik.org/course/217/syllabus)\
[stepik.org/course/1547/syllabus](https://stepik.org/course/1547/syllabus)\
[stepik.org/course/53634/syllabus](https://stepik.org/course/53634/syllabus)\
[stepik.org/course/64454/syllabus](https://stepik.org/course/64454/syllabus)\
[www.coursera.org/specializations/data-structures-algorithms](https://www.coursera.org/specializations/data-structures-algorithms) (платный, англ язык, более advanced)\
[openedu.ru/course/ITMOUniversity/PADS](https://openedu.ru/course/ITMOUniversity/PADS/)

4\. 

В ИТМО много сильных алгоритмистов, не зря ребята много раз становились чемпионами мира по программированию. Рискну предположить, что материалы там скорее ориентированы на «продвинутого» пользователя, который уже понимает, как устроены алгоритмические задачи. Если курс от ИТМО не кажется вам слишком сложным — могу его только порекомендовать. Ещё на ютубе есть классные лекции по алгоритмам от Павла Маврина, тоже очень рекомендую.

5\.

 Ещё [Записи лекций](https://vk.com/mavrinlectures) Павла Маврина советую, он сейчас для кодфорсез делает курс по алгоритмам на английском. Или сделал :)

6\.

{% embed url="https://habr.com/ru/company/skillfactory/blog/539058/" %}



## Ссылки

Loop Invariants: [https://www.cs.scranton.edu//\~mccloske/courses/cmps144/invariants_lec.html](https://www.cs.scranton.edu/\~mccloske/courses/cmps144/invariants_lec.html)

Comparison-based Lower Bounds for Sorting (анализ возможного нижнего уровня сложности алгоритмов сортировки): [http://www.cs.cmu.edu/\~avrim/451f11/lectures/lect0913.pdf](http://www.cs.cmu.edu/\~avrim/451f11/lectures/lect0913.pdf)

e-maxx algo (сайт с реализацией алгоритмов): [https://e-maxx.ru/algo/](https://e-maxx.ru/algo/)

Competitive Programmer’s Handbook Antti Laaksonen: [https://cses.fi/book/book.pdf](https://cses.fi/book/book.pdf)

Problem Solving with Algorithms and Data Structures: [http://aliev.me/runestone/](http://aliev.me/runestone/)

## 3 стратегии построения алгоритма

### 1. Bottleneck Unnesesserywork Duplicatework

Удалить бутылочные горлышки, избегать ненужно работы, избегать дублирующейся работы

### 2. Spase/Time tradeoff

Либо вы используете больше пространтва, либо больше времени

### 3. DYI

Попробовать решить задачу в уме - пройти по шагам по вашим действиям - это может подсказать алгоритм, которым нужно решать задачу. Часто алгоритм, который вы придумываете или которым вам кажется, что нужно действовать, совсем не такой, каким вы будете решать задачу самостоятельно.

## 7 шагов для нахождения алгоритма

1. Внимательно прослушать проблему
2. Придумать хороший пример для задачи, в котором бы проявлялись разные стороны поведения проблемы, а не только краевые случаи и который был бы достаточно большим
3. Придумать брут-форс алгоритм (но не кодируйте его), который решит проблему примитивным или наивным способом
4. Придумайте, как вы можете оптимизировать брут-форс алгоритм
5. Продумайте полностью код вашего алгоритма, до того как начнёте его писать - что конкретно вы будете писать?
6. Написание кода на доске (тут есть правила специфичные для написания кода на доске, но не только)
7. Тест - идите по коду линия за линией и думайте - она действительно делает то что должна и делает это правильно?

Аналитика: Обращайте внимание на странные или недостаточно понятные места - и проверьте их дважды. Спрашивайте себя - где может быть ошибка?

Тест Кейсы: Начинайте с маленьких, Затем покройте краевые случаи, если останется время возьмите несколько больших тест-кейсов.

Советы: тестируйте ваш код, а не корректность алгоритма. Когда вы находите баг поймите его настоящую причину, а не пытайтесь сразу же пофиксить.

## Шаблоны используемые при решении задач

{% embed url="https://tproger.ru/translations/14-templates-to-answer-interview-questions/" %}

