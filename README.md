# AT
flowchart TD
    %% Define external entities
    OT_SPECIALIST[Специалист по охране труда]
    OT_HEAD[Начальник отдела охраны труда]
    HR_DEPT[[Отдел кадров]]
    DB[(База данных<br/>LPS)]

    %% Define the main system
    LPS[[Labor Protection System<br/>LPS]]

    %% Data flows to/from the system
    OT_SPECIALIST -- "Данные об обучении<br/>Запрос на отчет / протокол" --> LPS
    LPS -- "Сформированный протокол<br/>Готовый отчет / напоминание" --> OT_SPECIALIST

    OT_HEAD -- "Запрос на сводную статистику<br/>Подписанный протокол" --> LPS
    LPS -- "Сводный отчет по предприятию" --> OT_HEAD

    HR_DEPT -- "Данные о сотрудниках<br/>прием, увольнение, переводы" --> LPS
    LPS -- "Уведомление о необходимости<br/>обучить нового сотрудника" --> HR_DEPT

    LPS -- "Запрос на запись / обновление" --> DB
    DB -- "Результат запроса<br/>данные" --> LPS
