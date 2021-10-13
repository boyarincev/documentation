# Quartz.NET

[Жизненный цикл джобов](https://www.quartz-scheduler.net/documentation/quartz-3.x/tutorial/more-about-jobs.html)

Интеграция с IOC контейнером - джобы не реализуют интерфейс IDisposable, соответственно нет простой возможности освобождать зависимости, нужно делать это через события - [пример](https://stackoverflow.com/questions/18791033/what-is-the-proper-way-to-call-dispose-in-a-quartz-net-ijob-that-is-idisposab).
