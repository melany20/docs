# condition.equals

{% include [deprecate](../../_includes/deprecate.md) %}

Проверяет, равно ли исходное значение указанному. При совпадении вернет `true`, иначе — `false`.

При подстановке значений можно ссылаться на данные `data.*` или на другой элемент с помощью `$ref`. Также можно использовать [хелперы](helpers.md) и [условия](conditions.md), чтобы получить значение.

[![](../_images/buttons/view-example.svg)](https://clck.ru/QMmPE)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "condition.equals" | Задает тип компонента. ||
|| `data` | _any_ | Исходное значение. Если не задано, то используется значение, возвращаемое родительским компонентом (в котором находится `condition.equals`).

Как передать значение:

- указать само значение, например число 42 или строку;
- [получить значение из данных](../operations/work-with-data.md);
- сослаться на другой элемент с помощью `$ref`;
- использовать [хелперы](helpers.md) и [условия](conditions.md), чтобы получить значение. ||
  || `hint` | _string_ | Сообщение об ошибке валидации, которое увидит исполнитель ||
  || `to`<span style="color: red">\*</span> | _any_ | Значение, c которым сравнивается исходное.

Как передать значение:

- указать само значение, например число 42 или строку;
- [получить значение из данных](../operations/work-with-data.md);
- сослаться на другой элемент с помощью `$ref`;
- использовать [хелперы](helpers.md) и [условия](conditions.md), чтобы получить значение. ||
  |#
