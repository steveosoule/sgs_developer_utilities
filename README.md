# Developer Utilities

A Miva module with a set of helper functions to make development easier.

* [`XML_Stringify(data var, parent_tag)`](#xml_stringify)
* [`XML_Output(data var, parent_tag)`](#xml_output)
* [`XML_Element_Name_Is_Valid(tag_name var)`](#xml_element_name_is_valid)
* [`JSON_Stringify(data var)`](#json_stringify)
* [`JSON_Output(data var)`](#json_output)

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