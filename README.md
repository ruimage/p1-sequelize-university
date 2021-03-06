# Схема курса университета

## Введение
Мы собираемся разработать схему базы данных, которая будет поддерживать приложение для подачи заявок на университетский курс. Представьте себе приложение, в котором студенты могут просматривать предложения по курсу университета. Каждый из курсов университета указан: английский 101, английский 201, математика 101 и т. д. Студенты просматривают список и зачисляются на курсы. Конкретные требования представлены в releases.


## Releases
### Release 0: Основная схема
Начните с разработки схемы базы данных на основе требований, перечисленных ниже. Используйте [дизайнер схем](https://www.dbdesigner.net/), чтобы визуально представить схему.

- Студент может записаться на многие курсы.
- На курсе может быть много учащихся.
- Студент получает финальную оценку на каждом курсе, куда он был зачислен (как следует подумайте о том, в какой таблице находятся эти данные).
- Курс преподается одним преподавателем.
- Преподаватель может вести несколько курсов.

### Release 1: Обновленные требования
Требования к нашей схеме изменились. Наша база данных должна поддерживать некоторые дополнительные функции. Измените дизайн схемы в соответствии с требованиями, перечисленными ниже.

- Отдел предлагает много курсов.
- Курс предлагается одним отделом.
- Курс имеет множество секций (например, английский 101, секция 1, английский 101, секция 2 и т. д.).
- Секция предлагается либо в понедельник / среду / пятницу, либо во вторник / четверг.
- В секции есть время начала и время окончания.
- Учащийся может начать посещать курс только после его зачисления в определенную секцию курса.
- Студент получает финальную оценку на секции, куда он был зачислен
- Секция преподаётся одним преподавателем.
- Преподаватель может преподавать в нескольких секциях.


### Release 2: Классы перекрестных списков
Иногда курсы перечислены перекрестно в нескольких департаментах. Например, один и тот же курс комбинаторики может совместно предлагаться отделами математики и информатики. Обновите схему для поддержки кросс-листинга:

- Отдел предлагает много курсов.
- Курс может предлагаться многими отделами.

По завершении сделайте скриншот экрана с финальным дизайном схемы и зафиксируйте его.

### Release 3: Вынужденные ограничения
Поскольку учащиеся зачисляются в секции курса, то в связи с этим может возникнуть парочка проблем. Что делать, если студент поступает в две секции одного курса? Или что делать, если студент записывается в две секции, время которых накладывается одно на другое? Или, если уж на то пошло, что делать, если преподавателю поручено вести занятия в двух секциях, время которых накладывается одно на другое?

Как мы можем сделать вывод о том, что данные ученика или учителя нарушают одно из этих ограничений? Даже если сама база данных не имеет встроенных ограничений,  то мы все равно можем сделать вывод о наличии нарушения и затем написать код в JavaScipt, чтобы гарантировать то, что это нарушение не дойдет до нашей базы данных. Другими словами, наше приложение JavaScipt не будет ничего записывать в базу данных, если  нарушение будет иметь место.

Как мы можем обеспечить соблюдение этих ограничений? Обсудите в парах, как это возможно сделать. Каковы потенциальные затраты на поддержку кода JavaScipt для подтверждения наших данных? Напишите объяснение в файле `constraints.md`.

*Примечание:* Мы не будем отражать эти ограничения в нашей схеме.

## Заключение
При разработке схемы базы данных мы позволяем потребностям приложения управлять дизайном схемы. Нам нужно иметь возможность взглянуть на потребности приложения и понять, как поддерживать эти потребности в базе данных.

Одной из важнейших проблем является сопоставление данных в разных таблицах друг с другом. Например, связывая студентов с их курсами через секции, в которых они записываются. Мы должны уметь смотреть на приложение, выводить типы отношений между объектами и знать, как моделировать их в наших схемах.

[дизайнер схем #1](https://www.dbdesigner.net/)
[дизайнер схем #2](https://app.quickdatabasediagrams.com/#/)
