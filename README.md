# Developer Utilities

A Miva module with a set of helper functions to make development easier.

* [`XML_Stringify(data var, parent_tag)`](#xml_stringify)
* [`XML_Output(data var, parent_tag)`](#xml_output)
* [`XML_Element_Name_Is_Valid(tag_name var)`](#xml_element_name_is_valid)
* [`JSON_Stringify(data var)`](#json_stringify)
* [`JSON_Output(data var)`](#json_output)
* [`JSON_Value_Is_Numeric(value)`](#json_value_is_numeric)

## Functions

### `XML_Stringify`

Pass a miva data structure & text for a parent tag to wrap it in, and it will return the XML string

**Parameters:** `data var, parent_tag`
**Return Value** `string`

```xml
<mvt:do file="g.Module_Root $ g.Module_Path $ 'util/sgs_developer_utilities.mvc'" name="l.settings:xml" value="XML_Stringify(l.settings:basket, 'basket')" />
&mvt:xml;
```

### `XML_Output`

Same as `XML_Stringify` but it will output directly to the page

**Parameters:** `data var, parent_tag`
**Return Value** `null`

```xml
<mvt:do file="g.Module_Root $ g.Module_Path $ 'util/sgs_developer_utilities.mvc'" name="l.null" value="XML_Output(l.settings:basket, 'basket')" />
```

### `XML_Element_Name_Is_Valid`

Will check whether or not the tag name is valid for use in an XML element.

**Parameters:** `tag_name var`
**Return Value** `boolean` / `1` or `0`

```xml
<mvt:do file="g.Module_Root $ g.Module_Path $ 'util/sgs_developer_utilities.mvc'" name="l.null" value="XML_Element_Name_Is_Valid('foobar')" />
```


### `JSON_Stringify`

Pass a miva data structure, and it will return a JSON string (Based on Miva's `JSON_Output` function in `json.mv`)

**Parameters:** `data var, parent_tag`
**Return Value** `string`

```xml
<mvt:do file="g.Module_Root $ g.Module_Path $ 'util/sgs_developer_utilities.mvc'" name="l.settings:json" value="JSON_Stringify(l.settings:basket)" />
&mvt:json;
```


### `JSON_Output`

Same as `JSON_Stringify` but it will output the JSON directly to the page.

**Parameters:** `data var, parent_tag`
**Return Value** `null`

```xml
<mvt:do file="g.Module_Root $ g.Module_Path $ 'util/sgs_developer_utilities.mvc'" name="l.null" value="JSON_Output(l.settings:basket)" />
```

### `JSON_Value_Is_Numeric`

Checks whether or not a value adheres to the JSON number specification. isdigit() doesn't evaluate to true for floating point numbers, so this function can be used to help check for floats or other numeric values.

[See demo on snippets.miva.com for some examples & test cases.](https://ssoule.mivamerchantdev.com/store/json-value-validation.html)

**Parameters:** `value`
**Return Value** `boolean`, `1` or `0`

```xml
<mvt:do file="g.Module_Root $ g.Module_Path $ 'util/sgs_developer_utilities.mvc'" name="l.null" value="JSON_Value_Is_Numeric(3.14)" />
```

## Change Log

- 1.1.2 (2017-05-17)
	- Added `JSON_Value_Is_Numeric` function
	- `JSON_Stringify` updated to stop outputting Floats as a String using `JSON_Value_Is_Numeric` function.
	- Switched `len()` MivaScript function to `len_var()` to improve performance for larger strings.
- 1.1.1
	- First release with the following functions:
		- `XML_Stringify`
		- `XML_Output`
		- `XML_Element_Name_Is_Valid`
		- `JSON_Stringify`
		- `JSON_Output`