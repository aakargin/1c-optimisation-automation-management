# Функционально-технические требования к подсистеме «Управление оптимизацией и автоматизацией учета»

## 1. Общие требования

1.1. В подсистеме должны быть реализованы следующие объекты:
- макет процесса;
- запущенный процесс;
- задача;
- настройка запуска процессов;
- панель руководителя;
- выполненные точки процесса (регистр сведений).

1.2. Требования к объектам подсистемы раскрыты в совокупности требований к функциональностям подсистемы.

1.3. В подсистеме должны быть реализованы следующие функциональности:
- создание маршрута процесса;
- внесение изменений в маршрут процесса;
- создание задания на автоматизацию;
- создание задания на оптимизацию;
- согласование и утверждение маршрута процесса;
- запуск утвержденного процесса;
- выполнение задач и переход процесса на следующий этап;
- создание задания на актуализацию;
- агрегирование сводной информации по статусу выполнения утвержденных процессов в панели руководителя.

## 2. Создание маршрута процесса

2.1. Функционал создания маршрута процесса должен быть реализован в объекте **макет процесса**.

2.2. Создание маршрута процесса должно осуществляться с помощью чат-бота.

2.2.1. Схема взаимодействия бота с пользователем должна задаваться в формате, позволяющим удобно и быстро ее редактировать.

2.2.2. Необходимо разработать универсальную схему взаимодействия (опросник) для создания маршрутов учетных процессов.

2.3. При создании маршрута процесса должны определяться следующие свойства процессов, которые будут запускаться по этому маршруту:
- тип периода к которому относится процесс (максимальное значение типа - тип периода, соответствующий отчетному периоду организации) (период заполняется при запуске процесса);
- типы аналитик, по которым идентифицируется запущенный процесс (аналитики заполняются при запуске процесса);
- группа и подгруппа процессов, к которой относиться процесс;
- признак запускаемого / незапускаемого процесса (незапускаемые процессы могут создаваться в том числе для реализации схемы взаимодействия чат-бота).

2.4. Информация о всех точках и соединительных линиях (элементах, связывающих выходы и входы точек) маршрута должны храниться в табличной части объекта **макет процесса**.

2.4.1. В табличной части для каждой точки маршрута должна хранится информация о оставшемся количестве точек до конца процесса (не считая текущую точку), расчитываемое по маршруту с наименьшим количеством точек (это значение должно передаваться в запускаемую **задачу**).

2.5. Должен быть реализован функционал визуализации маршрута процесса в виде графической схемы (по возможности, не задействуя ресурсы сервера).

2.6. Должен быть реализован механизм автоматического формирования заданий на автоматизацию и оптимизацию в процессе создания маршрута процесса.

2.7. Должен быть реализован механизм автоматического создания объектов **настройка запуска процессов** для автоматизации запуска утвержденных процессов.

## 3. Внесение изменений в маршрут процесса

3.1. Функционал внесения изменений в маршрут процесса с помощью чат-бота должен быть доступен до утверждения **макета процесса**.

3.2. Чат-бот должен обеспечивать возможность:
- добавлять точку маршрута в указанном месте маршрута процесса;
- удалять заданные точки маршрута;
- удалять все точки маршрута после заданной точки маршрута.

3.3. Чат-бот должен автоматически определять какие вопросы из схемы взаимодействия необходимо заново адресовать пользователю в связи с внесением изменений в маршрут процесса (в том числе требовать подтверждение корректности маршрута от точки внесения изменений до точки завершения маршрута).

## 4. Создание задания на автоматизацию

## 5. Создание задания на оптимизацию

## 6. Согласование и утверждение маршрута процесса

## 7. Запуск утвержденного процесса

## 8. Выполнение задач и переход процесса на следующий этап

## 9. Создание задания на актуализацию

## 10. Агрегирование сводной информации по статусу выполнения утвержденных процессов в панели руководителя

10.1. Сводная информация по статусу выполнения утвержденных процессов должна выводится в **панель руководителя**.

10.2. Сводная информация должна формироваться по заданному отчетному периоду.

10.3. Сводная информация должна содержать следующую инфографику:
- количество выполненных **задач** из общего количества **задач** за период;

`количество выполненных задач = количество записей в регистре о выполненнии задач в периоде`

`общее количество задач за период = количество записей в регистре о выполненнии задач в периоде + количество текущих задач на выполнении по процессам, относящимся к текущему периоду + информация о количестве оставшихся задач в процессе из каждой задачи на выполнении по процессам, относящимся к текущему периоду`

- разница между количеством невыполненных заданий на автоматизацию по состоянию на конец периода и на начало периода из количества невыполненных заданий на автоматизацию по состоянию на конец периода с указанием количества выполненных заданий на автоматизацию в периоде;
- разница между количеством невыполненных заданий на оптимизацию по состоянию на конец периода и на начало периода из количества невыполненных заданий на оптимизацию по состоянию на конец периода с указанием количество выполненных заданий на оптимизацию в периоде.

10.4. Сводная информация должна отображатся в следующих представлениях:
- информация по всему подразделению и правее по каждой группе процессов;
- информация по группе процессов и правее по каждой подгруппе процессов.

10.5. **Панель руководителя** должна выводится как на тонкий клиент пользователя так и на страницу веб-сервиса.
