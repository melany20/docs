# plugin.field.image-annotation.hotkeys

{% include [deprecate](../../_includes/deprecate.md) %}

Позволяет задавать горячие клавиши для компонента [field.image-annotation](field.image-annotation.md).

Можно задать горячие клавиши для выбора типов областей, выбора режимов разметки и подтверждения или отмены создания области. Добавить их можно на стрелки вверх и вниз (`up`,`down`), цифры и латинские буквы.

[![](../_images/buttons/view-example.svg)](https://clck.ru/TSC6f)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "plugin.field.image-annotation.hotkeys" | Задает тип компонента. ||
|| `cancel` | _string_ | Горячая клавиша для отмены создания области. ||
|| `confirm` | _string_ | Горячая клавиша для подтверждения создания области. ||
|| `labels` | _array_ | Горячие клавиши для выбора типов областей. Добавляются на кнопки в порядке их отображения, если вы добавили возможность выделить несколько типов областей. ||
|| `labels[]` | _string_ | Горячая клавиша. ||
|| `modes` | _object_ | Горячие клавиши для выбора режимов разметки. ||
|| `modes.point` | _string_ | Горячая клавиша для режима разметки точками. ||
|| `modes.polygon` | _string_ | Горячая клавиша для режима разметки многоугольниками. ||
|| `modes.rectangle` | _string_ | Горячая клавиша для режима разметки прямоугольниками. ||
|| `modes.select` | _string_ | Горячая клавиша для режима выбора фигур и точек. ||
|#
