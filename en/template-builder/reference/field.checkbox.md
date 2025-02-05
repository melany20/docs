# field.checkbox

A checkbox.

If you need to add a group of checkboxes, use [field.checkbox-group](field.checkbox-group.md).

[![image](../_images/buttons/view-example.svg)](https://clck.ru/asSNc)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.checkbox" | Set component type ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `disabled` | _boolean_ | Property that disables the component. If `true`, the component will not be unavailable. ||
|| `hint` | _string_ | Hint text. ||
|| `preserveFalse` | _boolean_ | Property that specifies whether to return `false` values in the results. By default, if the component returns `false`, this result will not be added to the output. To add `false` to the results, specify `"preserveFalse": true`. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#
