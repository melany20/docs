# Исполнители

{% include [deprecate](../../_includes/deprecate.md) %}

{% include [troubleshooting-key-combination](../_includes/troubleshooting/troubleshooting/id-troubleshooting/key-combination.md) %}

## Данные об исполнителях {#user-info}

{% cut "Как посмотреть информацию об исполнителях" %}

Информация об исполнителях, которые участвовали в ваших заданиях, доступна на странице  [Исполнители]({{ users }}). Чтобы посмотреть информацию об исполнителе, выберите его идентификатор. Заказчику доступны следующие данные профиля исполнителя: страна и город, возраст, образование, знание языков. Во вкладке **Метаинформация** можно узнать версию браузера и операционной системы, тип User-agent, регион, определённый по IP, и другие параметры исполнителя. Чтобы отобрать исполнителей для [пула](../../glossary.md#pool) по данным профиля, устройству, геопозиции и другим параметрам, используйте [фильтры](../concepts/filters.md).

{% endcut %}

{% cut "Проверяется ли информация, указанная исполнителем в профиле?" %}

Исполнители сами указывают информацию в профиле при регистрации. Мы не требуем документов, удостоверяющих личность, при регистрации в Толоке. Если профиль кажется нам подозрительным, мы просим его владельца уточнить данные.

{% endcut %}

{% cut "Знают ли исполнители свой идентификатор?" %}

Нет, идентификатор исполнителя доступен только заказчику.

{% endcut %}

{% cut "Почему в настройках пула можно отфильтровать исполнителей по полу, хотя в профиле информации о поле нет?" %}

Заказчику недоступна полная информация о конкретных исполнителях. Например, он не видит их дату рождения, пол, фамилию и имя. При этом в настройках пула заказчику доступны фильтры по дате рождения и полу. Они позволяют отобрать группу исполнителей, не получая информации о каждом в отдельности. Это уменьшает риск деанонимизации исполнителей.

{% endcut %}

{% cut "Обучение прошли более 500 исполнителей, но в тренировочном навыке отображается только 30" %}

В пуле отображается общее число исполнителей, которые выполнили там хотя бы одну страницу заданий. Тренировочный навык может со временем теряться из-за настройки повторного прохождения. Она позволяет заново выполнить тренировку по истечении указанного срока, если исполнитель так и не приступил к заданиям в привязанных пулах или сделал слишком большой перерыв в выполнении заданий (например, из-за [блокировки](../../glossary.md#banning-tolokers)). Поэтому в тренировочном навыке отображаются те исполнители, которые либо недавно завершили обучение, либо регулярно выполняют ваше задание и не дают навыку исчезнуть.

[Другой вопрос](support.md#help)

{% endcut %}

## Бонусы {#bonuses}

{% cut "Как поощрить исполнителей в дополнение к базовой стоимости задания" %}

Вы можете повысить базовую стоимость задания для исполнителей с более высоким навыком. Для этого настройте [Динамическое ценообразование](../concepts/dynamic-pricing.md). Если вы хотите повысить мотивацию исполнителей за качественное выполнение заданий, независимо от их навыка, используйте бонусы. Опишите в инструкции задания, сколько бонусов и в каких случаях получат исполнители.

{% endcut %}

{% cut "Как посмотреть статистику по выплаченным бонусам" %}

Чтобы посмотреть расходы на выплату бонусов, перейдите в ваш  [профиль]({{ profile }}) и откройте вкладку **Затраты**.

[Другой вопрос](support.md#help)

{% endcut %}

## Читеры {#cheaters}

{% cut "Можно ли отключать задания для исполнителей, которые выполняют его некачественно?" %}

Можно закрывать доступ исполнителей к пулу по слишком [быстрым ответам](../concepts/quick-answers.md), по регулярному несовпадению с [мнением большинства](../concepts/mvote.md) или если исполнитель делает много ошибок в [контрольных заданиях](../concepts/goldenset.md). Задания, выполненные такими исполнителями, можно [выдать другим исполнителям](../concepts/restore-task-overlap.md).

{% endcut %}

{% cut "Можно ли попросить исполнителя переделать задание, если он допустил в нем ошибки?" %}

Нет, после отправки задания исполнитель уже не может внести в него изменения. Неверно [выполненные задания](../../glossary.md#completed-tasks) можно добавить в новый пул.

{% endcut %}

{% cut "Могу ли я самостоятельно исправить что-то в выполненном задании?" %}

Нет, в самом задании ничего исправить нельзя. Но это можно сделать вручную при обработке файла с результатами.

{% endcut %}

{% cut "Недобросовестный исполнитель отправляет задание с незаполненными полями ответа. Будет ли он заблокирован до того, как будут известны ответы других исполнителей?" %}

Исполнитель не будет заблокирован, пока не будет известно [мнение большинства](../concepts/mvote.md). Поэтому мы рекомендуем проводить [обучение](../concepts/train.md) или экзамен для новых исполнителей. Тогда для выполнения заданий можно будет отобрать тех, кто успешно прошел обучение.

{% endcut %}

{% cut "Оплачиваются ли ответы недобросовестных исполнителей, заблокированных за неверные ответы?" %}

Если исполнителю уже начислена оплата за задания, отменить ее не получится.

{% endcut %}

{% cut "Исполнители успешно проходят обучение, но отвечают с низкой точностью в основном задании" %}

Обучение помогает исполнителям изучить инструкцию задания и потренироваться в его выполнении. По результатам обучения заказчик может отобрать исполнителей, которые справились достаточно хорошо, в основной пул. Однако, успешное прохождение обучающего пула не гарантирует, что исполнитель в дальнейшем будет качественно выполнять задания. Исполнители, которые прошли обучение с высоким уровнем точности, не соответствующим их ответам в основном задании, могли обменяться друг с другом правильными ответами.

Помимо обучения, в основных пулах нужно настроить [правила контроля качества.](../concepts/control.md) Это позволит контролировать качество работы исполнителя на протяжении выполнения им задания. Если задание предполагает ответы в свободной форме или отправку файлов с данными, используйте [отложенную приемку](../concepts/offline-accept.md), чтобы выплачивать вознаграждение после проверки.

{% endcut %}

{% cut "В результаты попали ответы исполнителей, которых я заблокировал" %}

В результатах отображаются ответы всех исполнителей, в том числе и заблокированных. Чтобы исключить их ответы из результатов, выберите опцию **Не учитывать ответы заблокированных исполнителей**. Убраны будут ответы тех исполнителей, кто заблокирован на момент выгрузки результатов, а не на момент разметки пула.

{% endcut %}

{% cut "Как заблокировать исполнителя и отклонить все его ответы?" %}

Автоматически отклонить ответы заблокированного исполнителя нельзя.

{% include [quality-control-tasks-after-too-fast-ban-delete-answers](../_includes/troubleshooting/pool-setup/id-quality-control/tasks-after-too-fast-ban-delete-answers.md) %}

{% endcut %}

{% cut "На проекте есть исполнитель, которому я доверяю, но он был заблокирован системой" %}

К сожалению, такой исполнитель нарушил требования пользовательского соглашения и больше не сможет выполнять задания. Вы можете найти новых исполнителей или настроить [фильтры](../concepts/filters.md) так, чтобы они лучше соответствовали проекту.

{% endcut %}

{% cut "Написать в службу поддержки" %}

<iframe width="100%" frameborder="0" src="https://forms.yandex.com/surveys/10035353.388b5c1d02f16762f4a79b515beaa9740148362a/?lang=ru&iframe=1&service=toloka-ai"></iframe>

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}