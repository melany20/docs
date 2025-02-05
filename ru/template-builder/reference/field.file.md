# field.file

{% include [deprecate](../../_includes/deprecate.md) %}

Компонент позволяет исполнителю загружать файлы. В интерфейсе отображается кнопкой загрузки.

Вы можете перечислить в свойстве `accept` нужные типы файлов, которые будут предложены исполнителю при загрузке. По умолчанию разрешено загрузить только один файл, но можно позволить загружать несколько в свойстве `multiple`.

Если исполнитель заходит с мобильного устройства, то удобнее будет использовать [field.media-file](field.media-file.md) — он адаптирован под мобильные устройства и упрощает загрузку фото и видео.

В режиме проверки задания загруженные изображения появятся автоматически. Изображения можно просматривать, поворачивать и переключаться между ними.

[![](../_images/buttons/view-example.svg)](https://clck.ru/S667r)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "field.file" | Задает тип компонента. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Данные, значения которых будут обработаны или изменены. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `accept` | _array_ | Список типов файлов, которые будут предложены исполнителю при загрузке. По умолчанию можно загружать любые файлы.

Указывайте типы в формате [MIME Type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types). Например, вы можете предложить загрузку картинок через добавление типов `image/jpeg` и `image/png`. ||
|| `accept[]` | _string_ | Тип файлов в формате [MIME Type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types). ||
|| `hint` | _string_ | Текст подсказки. ||
|| `multiple` | _boolean_ | Определяет, разрешено ли загружать несколько файлов:

- `false` (по умолчанию) — запрещено;
- `true` — разрешено. ||
  || `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
  |#
