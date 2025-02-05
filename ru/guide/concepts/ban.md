# Блокировка

{% include [deprecate](../../_includes/deprecate.md) %}

Исполнитель может быть заблокирован двумя способами:

1. [Заказчиком](#ban-yourself);
1. [Платформой](#ban-platform).

## Как заблокировать исполнителя  {#ban-yourself}

Вы можете закрыть доступ исполнителю к одному или всем [проектам](../../glossary.md#project). Это позволяет вручную регулировать, какие исполнители будут выполнять задания. Например, можно выбрать всех исполнителей со значением [навыка](../../glossary.md#skill) ниже N и заблокировать им доступ к заданиям. Вы также можете разблокировать доступ.

Чтобы заблокировать доступ к заданиям для одного исполнителя:

1. Выберите исполнителя на странице [Пользователи]({{ users }}).

1. Нажмите кнопку {% if locale == "ru-ru" %}**Действия → Заблокировать**{% endif %}{% if locale == "en-com" %}**Actions → Ban**{% endif %}, заполните поля:

    #|
    ||**Поле**|**Описание**||
    ||{% if locale == "ru-ru" %}**Место блокировки**{% endif %}{% if locale == "en-com" %}**Ban type**{% endif %} | Область действия блокировки:

    - {% if locale == "ru-ru" %}**У меня**{% endif %}{% if locale == "en-com" %}**In all my projects**{% endif %} — все проекты;
    - {% if locale == "ru-ru" %}**На проекте**{% endif %}{% if locale == "en-com" %}**In the project**{% endif %} — один проект (выберите проект из списка).||
    ||{% if locale == "ru-ru" %}**Дата разблокировки**{% endif %}{% if locale == "en-com" %}**Ban expires**{% endif %} | Укажите, когда нужно снять блокировку.

    Рекомендуется блокировать доступ на время, чтобы поддерживать нужное количество исполнителей, выполняющих задания.||
    ||{% if locale == "ru-ru" %}**Причина**{% endif %}{% if locale == "en-com" %}**Reason**{% endif %} | Причина блокировки (доступна только заказчику).||
    |#

Чтобы заблокировать доступ к заданиям для некоторых исполнителей:

1. Выберите исполнителей с помощью [фильтров](../../glossary.md#filters) на странице [Пользователи]({{ users }}) или загрузите TSV-файл:

    {% if locale == "ru-ru" %}

    ```plaintext
    <id исполнителя 1>
    <id исполнителя 2>
    ...
    <id исполнителя n>
    ```

    {% endif %}{% if locale == "en-com" %}

    ```plaintext
    <performer id 1>
    <performer id 2>
    ...
    <performer id n>
    ```

    {% endif %}

1. Нажмите кнопку {% if locale == "ru-ru" %}**Заблокировать**{% endif %}{% if locale == "en-com" %}**Ban**{% endif %}, заполните поля (см. таблицу выше).

Сведения о доступе к заданиям можно просмотреть на странице исполнителя (перейдите на нее со страницы [Пользователи]({{ users }})), вкладка {% if locale == "ru-ru" %}**Блокировки**{% endif %}{% if locale == "en-com" %}**Bans**{% endif %}. Чтобы разблокировать доступ к заданиям, наведите курсор на строку блокировки и нажмите кнопку ![](../_images/location-job/task-edit/task-action-delete.svg).

{% note alert %}

Ответы заблокированных исполнителей будут учтены, если не отклонить их вручную при помощи отложенной приемки. Чтобы отправить задания этих исполнителей на повторную разметку, настройте правило [Повторное выполнение заданий после блокировки](restore-task-overlap.md).

{% endnote %}

## Блокировка на платформе {#ban-platform}

Для блокировки недобросовестных исполнителей на платформе существует специальный алгоритм — антифрод. Он проверяет поведение исполнителей и блокирует подозрительные аккаунты.

Основные причины бана:

1. Разглашение конфиденциальной информации.
1. Использование скриптов и ботов, обман платформы.
1. Некачественное выполнение заданий.
1. Использование ложных данных при регистрации.
1. Частые ошибки при вводе или пропуске капчи.
1. Использование нескольких аккаунтов.

{% note info %}

Если поведение исполнителя кажется подозрительным, [напишите в службу поддержки](../troubleshooting/support.md#cheater). Мы проведем дополнительную проверку. Если исполнитель действительно нарушает требования пользовательского соглашения — он будет заблокирован в системе и больше не сможет выполнять задания.

Вы также можете [заблокировать](#ban) такого исполнителя у себя на проекте.

{% endnote %}

## Решение проблем {#troubleshooting}

{% cut "На проекте есть исполнитель, которому я доверяю, но он был заблокирован системой" %}

К сожалению, такой исполнитель нарушил требования пользовательского соглашения и больше не сможет выполнять задания. Вы можете найти новых исполнителей или настроить [фильтры](filters.md) так, чтобы они лучше соответствовали проекту.

{% endcut %}

{% cut "Можно ли отключать задания для исполнителей, которые выполняют его некачественно?" %}

Можно закрывать доступ исполнителей к пулу по слишком [быстрым ответам](quick-answers.md), по регулярному несовпадению с [мнением большинства](mvote.md) или если исполнитель делает много ошибок в [контрольных заданиях](goldenset.md). Задания, выполненные такими исполнителями, можно [выдать другим исполнителям](restore-task-overlap.md).

{% endcut %}

{% cut "Можно ли попросить исполнителя переделать задание, если он допустил в нем ошибки?" %}

Нет, после отправки задания исполнитель уже не может внести в него изменения. Неверно [выполненные задания](../../glossary.md#completed-tasks) можно добавить в новый пул.

{% endcut %}

{% cut "Могу ли я самостоятельно исправить что-то в выполненном задании?" %}

Нет, в самом задании ничего исправить нельзя. Но это можно сделать вручную при обработке файла с результатами.

{% endcut %}

{% cut "Недобросовестный исполнитель отправляет задание с незаполненными полями ответа. Будет ли он заблокирован до того, как будут известны ответы других исполнителей?" %}

Исполнитель не будет заблокирован, пока не будет известно [мнение большинства](mvote.md). Поэтому мы рекомендуем проводить [обучение](train.md) или экзамен для новых исполнителей. Тогда для выполнения заданий можно будет отобрать тех, кто успешно прошел обучение.

{% endcut %}

{% cut "Оплачиваются ли ответы недобросовестных исполнителей, заблокированных за неверные ответы?" %}

Если исполнителю уже начислена оплата за задания, отменить ее не получится.

{% endcut %}

{% cut "Исполнители успешно проходят обучение, но отвечают с низкой точностью в основном задании" %}

Обучение помогает исполнителям изучить инструкцию задания и потренироваться в его выполнении. По результатам обучения заказчик может отобрать исполнителей, которые справились достаточно хорошо, в основной пул. Однако, успешное прохождение обучающего пула не гарантирует, что исполнитель в дальнейшем будет качественно выполнять задания. Исполнители, которые прошли обучение с высоким уровнем точности, не соответствующим их ответам в основном задании, могли обменяться друг с другом правильными ответами.

Помимо обучения, в основных пулах нужно настроить [правила контроля качества.](control.md) Это позволит контролировать качество работы исполнителя на протяжении выполнения им задания. Если задание предполагает ответы в свободной форме или отправку файлов с данными, используйте [отложенную приемку](offline-accept.md), чтобы выплачивать вознаграждение после проверки.

{% endcut %}

{% cut "В результаты попали ответы исполнителей, которых я заблокировал" %}

В результатах отображаются ответы всех исполнителей, в том числе и заблокированных. Чтобы исключить их ответы из результатов, выберите опцию **Не учитывать ответы заблокированных исполнителей**. Убраны будут ответы тех исполнителей, кто заблокирован на момент выгрузки результатов, а не на момент разметки пула.

{% endcut %}

{% cut "Как заблокировать исполнителя и отклонить все его ответы?" %}

Автоматически отклонить ответы заблокированного исполнителя нельзя.

{% include [quality-control-tasks-after-too-fast-ban-delete-answers](../_includes/troubleshooting/pool-setup/id-quality-control/tasks-after-too-fast-ban-delete-answers.md) %}

{% endcut %}

{% cut "Написать в службу поддержки" %}

<iframe width="100%" frameborder="0" src="https://forms.yandex.com/surveys/10035353.388b5c1d02f16762f4a79b515beaa9740148362a/?lang=ru&iframe=1&service=toloka-ai"></iframe>

{% endcut %}