## Classes

<dl>
<dt><a href="#desktop">desktop</a></dt>
<dd></dd>
<dt><a href="#tfw">tfw</a></dt>
<dd></dd>
<dt><a href="#prvek">prvek</a></dt>
<dd></dd>
<dt><del><a href="#Dyntable">Dyntable</a></del></dt>
<dd></dd>
</dl>

## Constants

<dl>
<dt><a href="#AJAX_LOADER">AJAX_LOADER</a> : <code>string</code></dt>
<dd><p>HTML to show when some content is being loaded.</p>
</dd>
</dl>

<a name="desktop"></a>
## desktop
**Kind**: global class  
<a name="new_desktop_new"></a>
### new desktop()
Triobo. This is a singleton (a single "instance" of a "class").

<a name="tfw"></a>
## tfw
**Kind**: global class  
**Todo**

- [ ] http://www.w3schools.com/js/js_reserved.asp


* [tfw](#tfw)
    * [new tfw()](#new_tfw_new)
    * [.dynamicTableClass](#tfw.dynamicTableClass)
        * [new dynamicTableClass(params)](#new_tfw.dynamicTableClass_new)
        * _instance_
            * [.tableContainer](#tfw.dynamicTableClass+tableContainer) : <code>Object</code>
            * [.url](#tfw.dynamicTableClass+url) : <code>string</code>
            * [.data](#tfw.dynamicTableClass+data) : <code>Object</code>
            * [.ascSortingSymbol](#tfw.dynamicTableClass+ascSortingSymbol) : <code>string</code>
            * [.descSortingSymbol](#tfw.dynamicTableClass+descSortingSymbol) : <code>string</code>
            * [.labelTrue](#tfw.dynamicTableClass+labelTrue) : <code>string</code>
            * [.labelFalse](#tfw.dynamicTableClass+labelFalse) : <code>string</code>
            * [.getTable()](#tfw.dynamicTableClass+getTable) ⇒ <code>Object</code>
            * [.reload()](#tfw.dynamicTableClass+reload)
            * [.reorderEnabled()](#tfw.dynamicTableClass+reorderEnabled) ⇒ <code>boolean</code>
            * [.toggleReorder()](#tfw.dynamicTableClass+toggleReorder)
            * [.orderChange(element)](#tfw.dynamicTableClass+orderChange)
            * [.paint()](#tfw.dynamicTableClass+paint)
            * [.filter(column)](#tfw.dynamicTableClass+filter)
            * [.sort(obj, dynamicTable)](#tfw.dynamicTableClass+sort)
            * [.filterSearch(column, value, [searchType])](#tfw.dynamicTableClass+filterSearch)
            * [.filterBoolean(column, searchType)](#tfw.dynamicTableClass+filterBoolean)
            * [.filterNumeric(column, compareValue, cmp)](#tfw.dynamicTableClass+filterNumeric)
            * [.filterDate(column, compareValue, cmp)](#tfw.dynamicTableClass+filterDate)
            * [.toggleColumn(column)](#tfw.dynamicTableClass+toggleColumn)
            * [.toggleColumnDialog()](#tfw.dynamicTableClass+toggleColumnDialog)
        * _inner_
            * [~rowEdit](#tfw.dynamicTableClass..rowEdit) : <code>function</code>
    * [.calendar](#tfw.calendar)
        * [new calendar(input)](#new_tfw.calendar_new)
        * _static_
            * [.months](#tfw.calendar.months) : <code>Array.&lt;String&gt;</code>
            * [.daysShort](#tfw.calendar.daysShort) : <code>Array.&lt;String&gt;</code>
            * [.placeCalendar](#tfw.calendar.placeCalendar) : <code>[placeCalendar](#tfw.calendar..placeCalendar)</code>
        * _inner_
            * [~placeCalendar](#tfw.calendar..placeCalendar) : <code>function</code>
    * [.ajaxIncludeParams](#tfw.ajaxIncludeParams) : <code>function</code>
    * [.ajaxOnErrorCode](#tfw.ajaxOnErrorCode) : <code>function</code>
    * [.ajaxOnError](#tfw.ajaxOnError) : <code>function</code>
    * [.fillElemDefs(element, params)](#tfw.fillElemDefs)
    * [.select(params)](#tfw.select) ⇒ <code>Object</code>
    * [.button(params)](#tfw.button) ⇒ <code>Object</code>
    * [.inputFieldLegend(element, params)](#tfw.inputFieldLegend) ⇒ <code>Object</code>
    * [.input(params)](#tfw.input) ⇒ <code>Object</code>
    * [.textArea(params)](#tfw.textArea) ⇒ <code>Object</code>
    * [.checkbox(params)](#tfw.checkbox) ⇒ <code>Object</code>
    * [.icon(params)](#tfw.icon) ⇒ <code>Object</code>
    * [.table(params)](#tfw.table) ⇒ <code>Object</code>
    * [.tr(params)](#tfw.tr) ⇒ <code>Object</code>
    * [.td(params)](#tfw.td) ⇒ <code>Object</code>
    * [.slider(params)](#tfw.slider) ⇒ <code>Object</code>
    * [.ajaxGet(o)](#tfw.ajaxGet) ⇒ <code>Object</code>
    * [.encodeFormValues(fields)](#tfw.encodeFormValues) ⇒ <code>string</code>
    * [.decodeJSON(json)](#tfw.decodeJSON) ⇒ <code>Object</code>
    * [.dynamicTable(params)](#tfw.dynamicTable) ⇒ <code>Object</code>

<a name="new_tfw_new"></a>
### new tfw()
Triobo framework. This is a singleton (a single "instance" of a "class").

<a name="tfw.dynamicTableClass"></a>
### tfw.dynamicTableClass
**Kind**: static class of <code>[tfw](#tfw)</code>  
**See**: AJAX_LOADER  
**Todo**

- [ ] Don't bind rowEdit to onclick of TRs, show an edit ([i]) icon after each row (if set)
- [ ] View preferences (width, order of columns)
- [ ] Allow editing of simple cells
- [ ] Implement server parameter t - name of table
- [ ] Implement server actions - load (all rows), new (add new row, return ID), write (edit 1 cell - special for order), watch (long polling), delete (row)
- [ ] Implement "child" tables (e.g. link from list of releases to list of articles in a release) - add callback(s)


* [.dynamicTableClass](#tfw.dynamicTableClass)
    * [new dynamicTableClass(params)](#new_tfw.dynamicTableClass_new)
    * _instance_
        * [.tableContainer](#tfw.dynamicTableClass+tableContainer) : <code>Object</code>
        * [.url](#tfw.dynamicTableClass+url) : <code>string</code>
        * [.data](#tfw.dynamicTableClass+data) : <code>Object</code>
        * [.ascSortingSymbol](#tfw.dynamicTableClass+ascSortingSymbol) : <code>string</code>
        * [.descSortingSymbol](#tfw.dynamicTableClass+descSortingSymbol) : <code>string</code>
        * [.labelTrue](#tfw.dynamicTableClass+labelTrue) : <code>string</code>
        * [.labelFalse](#tfw.dynamicTableClass+labelFalse) : <code>string</code>
        * [.getTable()](#tfw.dynamicTableClass+getTable) ⇒ <code>Object</code>
        * [.reload()](#tfw.dynamicTableClass+reload)
        * [.reorderEnabled()](#tfw.dynamicTableClass+reorderEnabled) ⇒ <code>boolean</code>
        * [.toggleReorder()](#tfw.dynamicTableClass+toggleReorder)
        * [.orderChange(element)](#tfw.dynamicTableClass+orderChange)
        * [.paint()](#tfw.dynamicTableClass+paint)
        * [.filter(column)](#tfw.dynamicTableClass+filter)
        * [.sort(obj, dynamicTable)](#tfw.dynamicTableClass+sort)
        * [.filterSearch(column, value, [searchType])](#tfw.dynamicTableClass+filterSearch)
        * [.filterBoolean(column, searchType)](#tfw.dynamicTableClass+filterBoolean)
        * [.filterNumeric(column, compareValue, cmp)](#tfw.dynamicTableClass+filterNumeric)
        * [.filterDate(column, compareValue, cmp)](#tfw.dynamicTableClass+filterDate)
        * [.toggleColumn(column)](#tfw.dynamicTableClass+toggleColumn)
        * [.toggleColumnDialog()](#tfw.dynamicTableClass+toggleColumnDialog)
    * _inner_
        * [~rowEdit](#tfw.dynamicTableClass..rowEdit) : <code>function</code>

<a name="new_tfw.dynamicTableClass_new"></a>
#### new dynamicTableClass(params)
Class for creating dynamic tables.


| Param | Type | Default | Description |
| --- | --- | --- | --- |
| params | <code>Object</code> |  | table parameters |
| [params.id] | <code>string</code> | <code>&quot;\&quot;dynamicTable\&quot;&quot;</code> | Table ID (name) that identifies the table (in database, HTML IDs) |
| [params.rowEdit] | <code>[rowEdit](#tfw.dynamicTableClass..rowEdit)</code> |  | Function that is fired when row editing is triggered. |

**Example**  
```js
function myRowEditFunction(order){	// ...}var table = document.body.appendChild( tfw.dynamicTable(  {   id: "table1",   rowEdit: myRowEditFunction  } ));
```
<a name="tfw.dynamicTableClass+tableContainer"></a>
#### dynamicTableClass.tableContainer : <code>Object</code>
DIV containing the table.

**Kind**: instance property of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
**Read only**: true  
<a name="tfw.dynamicTableClass+url"></a>
#### dynamicTableClass.url : <code>string</code>
URL parameters (appended to URL after the quotation mark "?") in the form "name1=value1&name2=value2". Has to be set before calling [reload()](#tfw.dynamicTableClass+reload).

**Kind**: instance property of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
**Access:** public  
<a name="tfw.dynamicTableClass+data"></a>
#### dynamicTableClass.data : <code>Object</code>
Data obtained from server. [reload()](#tfw.dynamicTableClass+reload) has to be called to fill this.

**Kind**: instance property of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
**Default**: <code>null</code>  
**Access:** public  
**Read only**: true  
**Properties**

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| cols | <code>Array.&lt;Object&gt;</code> |  | list of columns |
| cols[].name | <code>string</code> |  | name (HTML) |
| cols[].width | <code>number</code> |  | width |
| cols[].hidden | <code>boolean</code> |  | hidden |
| cols[].type | <code>string</code> | <code>null</code> | type of field, possible values: null (general), "text", "number", "checkbox", "date", "order" |
| cols[].sort | <code>boolean</code> | <code>false</code> | whether to allow sorting by this column's values |
| cols[].search | <code>number</code> | <code>0</code> | whether to allow searching, 0=disabled, 1=match from beginning, 2=match anywhere |
| cols[].filter | <code>boolean</code> | <code>false</code> | whether to allow filtering (depends on type) |
| rows | <code>Array.&lt;Object&gt;</code> |  | list of rows |
| rows[].id | <code>number</code> |  | row ID |
| rows[].cols | <code>Array.&lt;string&gt;</code> |  | contents for each column (HTML) |

<a name="tfw.dynamicTableClass+ascSortingSymbol"></a>
#### dynamicTableClass.ascSortingSymbol : <code>string</code>
Ascending sorting symbol.

**Kind**: instance constant of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
**Default**: <code>&quot;&amp;darr;&quot;</code>  
<a name="tfw.dynamicTableClass+descSortingSymbol"></a>
#### dynamicTableClass.descSortingSymbol : <code>string</code>
Descending sorting symbol.

**Kind**: instance constant of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
**Default**: <code>&quot;&amp;uarr;&quot;</code>  
<a name="tfw.dynamicTableClass+labelTrue"></a>
#### dynamicTableClass.labelTrue : <code>string</code>
Default label for true.

**Kind**: instance constant of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
**Default**: <code>&quot;Yes&quot;</code>  
<a name="tfw.dynamicTableClass+labelFalse"></a>
#### dynamicTableClass.labelFalse : <code>string</code>
Default label for false.

**Kind**: instance constant of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
**Default**: <code>&quot;No&quot;</code>  
<a name="tfw.dynamicTableClass+getTable"></a>
#### dynamicTableClass.getTable() ⇒ <code>Object</code>
Get table container (for inserting into document).

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
**Returns**: <code>Object</code> - Returns the table container (HTML element).  
<a name="tfw.dynamicTableClass+reload"></a>
#### dynamicTableClass.reload()
Reload (or load) data from server.Sends a GET request to "data.php", decodes JSON and [paints](#tfw.dynamicTableClass+paint) the table.

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
**See**

- tfw.dynamicTableClass#paint
- tfw.decodeJSON

**Todo**

- [ ] Don't repaint table, just change values.
- [ ] Don't use hardcoded base URL

<a name="tfw.dynamicTableClass+reorderEnabled"></a>
#### dynamicTableClass.reorderEnabled() ⇒ <code>boolean</code>
Test if no filters are applied and table is sorted by column of type 'order'.

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
**Returns**: <code>boolean</code> - True if reordering can be done, false otherwise.  
<a name="tfw.dynamicTableClass+toggleReorder"></a>
#### dynamicTableClass.toggleReorder()
Toggle reordering of rows via drag & drop.Reflects the value of a private variable set by onclick events fired with filters.Recommended CSS: tr.draggable{cursor:grab}, tr.draggable:active{cursor:grabbing}

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
<a name="tfw.dynamicTableClass+orderChange"></a>
#### dynamicTableClass.orderChange(element)
Reflect a change in order in the table.

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
**Todo**

- [ ] Reflect on server


| Param | Type | Description |
| --- | --- | --- |
| element | <code>Object</code> | row that was dropped (HTML element) |

<a name="tfw.dynamicTableClass+paint"></a>
#### dynamicTableClass.paint()
Refresh the content of the table using data gotten by (re)loading.Empties the table and recreates it using [data](#tfw.dynamicTableClass+data).If [rowEdit](tfw.dynamicTableClass#rowEdit) is set, it will be fired when a row is clicked.Assumes that there is only 1 order column and that data are sorted by that column.

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
**Todo**

- [ ] Enable localization
- [ ] Think about using different IDs (or a data attribute) for rows (e.g. add a prefix)
- [ ] Change drag&dropping so that it is clear where the dragged row will end

<a name="tfw.dynamicTableClass+filter"></a>
#### dynamicTableClass.filter(column)
Apply filter for values of a column.Creates a [dialog](tfw.dialog) with filter.

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  

| Param | Type | Description |
| --- | --- | --- |
| column | <code>number</code> | order number of searched column |

<a name="tfw.dynamicTableClass+sort"></a>
#### dynamicTableClass.sort(obj, dynamicTable)
Apply sorting by values (text without HTML) of a column.Text fields are sorted locale aware, with empty strings always last.

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  

| Param | Type | Description |
| --- | --- | --- |
| obj | <code>Object</code> | sorting button that triggered the event |
| dynamicTable | <code>dynamicTableClass</code> | reference to "this" |

<a name="tfw.dynamicTableClass+filterSearch"></a>
#### dynamicTableClass.filterSearch(column, value, [searchType])
Apply search filter (case insensitive).Requires .searchFilterInvalid{display:none}

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| column | <code>number</code> |  | order number of searched column |
| value | <code>string</code> |  | searched string |
| [searchType] | <code>number</code> | <code>2</code> | type of search (1 = starts with, 2 = includes) |

<a name="tfw.dynamicTableClass+filterBoolean"></a>
#### dynamicTableClass.filterBoolean(column, searchType)
Apply boolean filter.Requires .booleanFilterInvalid{display:none}

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  

| Param | Type | Description |
| --- | --- | --- |
| column | <code>number</code> | order number of searched column |
| searchType | <code>string</code> | search type ("0" = both, "1" = only true, "2" = only false) |

<a name="tfw.dynamicTableClass+filterNumeric"></a>
#### dynamicTableClass.filterNumeric(column, compareValue, cmp)
Apply numeric filter.Requires .numericFilterInvalid1, .numericFilterInvalid-1{display:none}

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  

| Param | Type | Description |
| --- | --- | --- |
| column | <code>number</code> | order number of searched column |
| compareValue | <code>string</code> | value to compare to (can be "") |
| cmp | <code>number</code> | type of comparison (1 means greater than, -1 means lower than) |

<a name="tfw.dynamicTableClass+filterDate"></a>
#### dynamicTableClass.filterDate(column, compareValue, cmp)
Apply date filter.Requires .dateFilterInvalid1, .dateFilterInvalid-1{display:none}

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  

| Param | Type | Description |
| --- | --- | --- |
| column | <code>number</code> | order number of searched column |
| compareValue | <code>string</code> | value to compare to (can be "") |
| cmp | <code>number</code> | type of comparison (1 means greater than, -1 means lower than) |

<a name="tfw.dynamicTableClass+toggleColumn"></a>
#### dynamicTableClass.toggleColumn(column)
Toggle visibility of a column. Only hides TDs in TBODY and THs.Requires .hideColumn{display:none}

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
**Todo**

- [ ] Save user preferences (to localStorage/server)


| Param | Type | Description |
| --- | --- | --- |
| column | <code>number</code> | order number of column |

<a name="tfw.dynamicTableClass+toggleColumnDialog"></a>
#### dynamicTableClass.toggleColumnDialog()
Toggle visibility of a column.Creates a [dialog](tfw.dialog) with checkboxes.

**Kind**: instance method of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  
<a name="tfw.dynamicTableClass..rowEdit"></a>
#### dynamicTableClass~rowEdit : <code>function</code>
Function that handles row editing.

**Kind**: inner typedef of <code>[dynamicTableClass](#tfw.dynamicTableClass)</code>  

| Param | Type | Description |
| --- | --- | --- |
| order | <code>number</code> | order of the row being edited |

<a name="tfw.calendar"></a>
### tfw.calendar
**Kind**: static class of <code>[tfw](#tfw)</code>  

* [.calendar](#tfw.calendar)
    * [new calendar(input)](#new_tfw.calendar_new)
    * _static_
        * [.months](#tfw.calendar.months) : <code>Array.&lt;String&gt;</code>
        * [.daysShort](#tfw.calendar.daysShort) : <code>Array.&lt;String&gt;</code>
        * [.placeCalendar](#tfw.calendar.placeCalendar) : <code>[placeCalendar](#tfw.calendar..placeCalendar)</code>
    * _inner_
        * [~placeCalendar](#tfw.calendar..placeCalendar) : <code>function</code>

<a name="new_tfw.calendar_new"></a>
#### new calendar(input)
Class for enhancing date input fields. Requires CSS styling.


| Param | Type | Description |
| --- | --- | --- |
| input | <code>Object</code> | input field to turn into calendar field (HTML element) |

**Example**  
```js
tfw.calendar.placeCalendar = function(cal, input){ input.parentNode.insertBefore(cal, input);}var input = tfw.input({value:"2016-03-07"});document.body.appendChild(input);tfw.calendar(input);
```
<a name="tfw.calendar.months"></a>
#### calendar.months : <code>Array.&lt;String&gt;</code>
List of months' names.

**Kind**: static property of <code>[calendar](#tfw.calendar)</code>  
**Default**: <code>[&quot;January&quot;,&quot;February&quot;,&quot;March&quot;,&quot;April&quot;,&quot;May&quot;,&quot;June&quot;,&quot;July&quot;,&quot;August&quot;,&quot;September&quot;,&quot;October&quot;,&quot;November&quot;,&quot;December&quot;]</code>  
<a name="tfw.calendar.daysShort"></a>
#### calendar.daysShort : <code>Array.&lt;String&gt;</code>
List of days' names' first two letters (beginning with Monday)

**Kind**: static property of <code>[calendar](#tfw.calendar)</code>  
**Default**: <code>[&quot;Mo&quot;,&quot;Tu&quot;,&quot;We&quot;,&quot;Th&quot;,&quot;Fr&quot;,&quot;Sa&quot;,&quot;Su&quot;]</code>  
<a name="tfw.calendar.placeCalendar"></a>
#### calendar.placeCalendar : <code>[placeCalendar](#tfw.calendar..placeCalendar)</code>
Function called when a calendar widget is created.

**Kind**: static property of <code>[calendar](#tfw.calendar)</code>  
**Default**: <code></code>  
<a name="tfw.calendar..placeCalendar"></a>
#### calendar~placeCalendar : <code>function</code>
Callback function that puts calendar widget for an input field into page.Most likely create an overlay that closes calendar when user clicks somewhere else.

**Kind**: inner typedef of <code>[calendar](#tfw.calendar)</code>  

| Param | Type | Description |
| --- | --- | --- |
| calendar | <code>Object</code> | calendar widget (HTML element) |
| input | <code>Object</code> | related input field (HTML element) |

<a name="tfw.ajaxIncludeParams"></a>
### tfw.ajaxIncludeParams : <code>function</code>
Generates permanent AJAX queries parameters (e.g. tokens, anti-cache)

**Kind**: static property of <code>[tfw](#tfw)</code>  
**Default**: <code>null</code>  
<a name="tfw.ajaxOnErrorCode"></a>
### tfw.ajaxOnErrorCode : <code>function</code>
Handles error generated by server (receives error code returned by server).

**Kind**: static property of <code>[tfw](#tfw)</code>  
**Default**: <code>null</code>  
<a name="tfw.ajaxOnError"></a>
### tfw.ajaxOnError : <code>function</code>
Handles HTTP errors (HTTP codes other than 200).

**Kind**: static property of <code>[tfw](#tfw)</code>  
**Default**: <code>null</code>  
**Todo**

- [ ] Implement

<a name="tfw.fillElemDefs"></a>
### tfw.fillElemDefs(element, params)
Set parameters of a HTML element.

**Kind**: static method of <code>[tfw](#tfw)</code>  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| element | <code>Object</code> |  | HTML element |
| params | <code>Object</code> |  | parameters object |
| [params.id] | <code>string</code> |  | ID |
| [params.className] | <code>string</code> |  | class |
| [params.innerHTML] | <code>string</code> |  | content (HTML) |
| [params.text] | <code>string</code> |  | content (text), works same as innerHTML |
| [params.style] | <code>string</code> |  | CSS styling |
| [params.title] | <code>string</code> |  | title (shows on hover) |
| [params.children] | <code>Array.&lt;Object&gt;</code> |  | descendant element(s) |
| [params.disabled] | <code>boolean</code> | <code>false</code> | disabled input field |
| [params.maxLength] | <code>number</code> |  | maximum input length |
| [params.evaluate] | <code>boolean</code> | <code>false</code> | evaluate (eval) field value after change (onchange), set to 1 or true |
| [params.onchange] | <code>function</code> |  | function to call when field changes value (onchange fires) |
| [params.onClick] | <code>function</code> |  | function to call when user clicks on the field (onclick fires) |
| [params.value] | <code>string</code> |  | default field value (or button text) |
| [params.placeholder] | <code>string</code> |  | text field placeholder |

<a name="tfw.select"></a>
### tfw.select(params) ⇒ <code>Object</code>
Create a select field with specified parameters.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - Created select field (HTML element).  
**See**: tfw.fillElemDefs  

| Param | Type | Description |
| --- | --- | --- |
| params | <code>Object</code> | select parameters (for more see [fillElemDefs](#tfw.fillElemDefs)) |
| [params.multiple] | <code>boolean</code> | can multiple values be selected |
| params.list | <code>string</code> &#124; <code>Array.&lt;string&gt;</code> &#124; <code>Array.&lt;Object&gt;</code> | list of options as string "label1;label2" or "label1|value1;label2|value2", as array of string labels or as object (nonspecified value defaults to numeric index, NOT label text) |
| [params.list[].id] | <code>string</code> | value (defaults to numeric index of option) |
| params.list[].t | <code>string</code> | label |

<a name="tfw.button"></a>
### tfw.button(params) ⇒ <code>Object</code>
Create a button with specified parameters.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - Created button (HTML element)  
**See**: tfw.fillElemDefs  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| params | <code>Object</code> |  | button parameters (for more see [fillElemDefs](#tfw.fillElemDefs)) |
| [params.step] | <code>number</code> |  | step between allowed numeric values |
| [params.default] | <code>boolean</code> | <code>false</code> | if true, type=submit, otherwise type=button |
| [params.action] | <code>function</code> |  | Function to fire when button is clicked (event propagation is stopped) |

<a name="tfw.inputFieldLegend"></a>
### tfw.inputFieldLegend(element, params) ⇒ <code>Object</code>
Wrap an input field with a legend and a container.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - container with legend and input field (HTML element)  

| Param | Type | Description |
| --- | --- | --- |
| element | <code>Object</code> | input field HTML element |
| params | <code>Object</code> | legend parameters |
| params.legend | <code>string</code> | legend text |
| [params.legendStyle] | <code>string</code> | legend CSS styling |
| [params.containerId] | <code>string</code> | legend container ID |
| [params.containerStyle] | <code>string</code> | legend container CSS styling |
| [params.postText] | <code>string</code> | text after input field |

<a name="tfw.input"></a>
### tfw.input(params) ⇒ <code>Object</code>
Create an input field with specified parameters.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - Created input field (HTML element)  
**See**

- tfw.fillElemDefs
- tfw.inputFieldLegend


| Param | Type | Default | Description |
| --- | --- | --- | --- |
| params | <code>Object</code> |  | input fields parameters (for more see [fillElemDefs](#tfw.fillElemDefs) and [inputFieldLegend](#tfw.inputFieldLegend)) |
| [params.type] | <code>string</code> | <code>&quot;\&quot;text\&quot;&quot;</code> | input field type |
| [params.value] | <code>string</code> |  | prefilled value |
| [params.min] | <code>number</code> |  | minimum allowed value |
| [params.max] | <code>number</code> |  | maximum allowed value |
| [params.step] | <code>number</code> |  | step between allowed numeric values |

<a name="tfw.textArea"></a>
### tfw.textArea(params) ⇒ <code>Object</code>
Create a text area with specified parameters.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - Created text area (HTML element)  
**See**

- tfw.fillElemDefs
- tfw.inputFieldLegend


| Param | Type | Description |
| --- | --- | --- |
| params | <code>Object</code> | text area parameters (for more see [fillElemDefs](#tfw.fillElemDefs) and [inputFieldLegend](#tfw.inputFieldLegend)) |
| [params.value] | <code>string</code> | prefilled value |

<a name="tfw.checkbox"></a>
### tfw.checkbox(params) ⇒ <code>Object</code>
Create a checkbox with specified parameters.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - Created checkbox (HTML element)  
**See**

- tfw.fillElemDefs
- tfw.inputFieldLegend

**Todo**

- [ ] Use "value" for real value, instead of using it for "checked"


| Param | Type | Default | Description |
| --- | --- | --- | --- |
| params | <code>Object</code> |  | checkbox parameters (for more see [fillElemDefs](#tfw.fillElemDefs) and [inputFieldLegend](#tfw.inputFieldLegend)) |
| [params.onchange] | <code>function</code> |  | function to call when field changes value (onchange fires) |
| [params.text] | <code>string</code> |  | checkbox label text |
| [params.value] | <code>string</code> | <code>0</code> | initial value (0=unchecked,1=checked) |

<a name="tfw.icon"></a>
### tfw.icon(params) ⇒ <code>Object</code>
Create an icon with specified parameters.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - Created icon (HTML element)  
**See**: tfw.fillElemDefs  

| Param | Type | Description |
| --- | --- | --- |
| params | <code>Object</code> | icon parameters (for more see [fillElemDefs](#tfw.fillElemDefs)) |
| [params.action] | <code>function</code> | function triggered when icon is clicked (basically onclick) |
| [params.index] | <code>number</code> | move background image up by this number of pixels (background-position-x) |

<a name="tfw.table"></a>
### tfw.table(params) ⇒ <code>Object</code>
Create a table with specified parameters.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - Created table (HTML element)  
**See**: tfw.fillElemDefs  

| Param | Type | Description |
| --- | --- | --- |
| params | <code>Object</code> | table parameters (for more see [fillElemDefs](#tfw.fillElemDefs), use params.children for rows) |

<a name="tfw.tr"></a>
### tfw.tr(params) ⇒ <code>Object</code>
Create a table row with specified parameters.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - Created table row (HTML element)  
**See**: tfw.fillElemDefs  

| Param | Type | Description |
| --- | --- | --- |
| params | <code>Object</code> | table row parameters (for more see [fillElemDefs](#tfw.fillElemDefs), use params.children for columns/cells) |
| [params.columns] | <code>Array</code> | list of objects, that will be passed to tfw.td and added as children |

<a name="tfw.td"></a>
### tfw.td(params) ⇒ <code>Object</code>
Create a table cell with specified parameters.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - Created table cell (HTML element)  
**See**: tfw.fillElemDefs  

| Param | Type | Description |
| --- | --- | --- |
| params | <code>Object</code> | table cell parameters (for more see [fillElemDefs](#tfw.fillElemDefs)) |
| [params.colspan] | <code>number</code> | number of columns that this cell will merge |

<a name="tfw.slider"></a>
### tfw.slider(params) ⇒ <code>Object</code>
Create a slider with specified parameters.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - Created slider (HTML element)  
**See**: tfw.fillElemDefs  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| params | <code>Object</code> |  | slider parameters (for more see [fillElemDefs](#tfw.fillElemDefs)) |
| params.id | <code>string</code> |  | ID, has to be present! |
| [params.legend] | <code>string</code> |  | legend text |
| [params.legendStyle] | <code>string</code> |  | legend CSS styling |
| [params.min] | <code>number</code> | <code>0</code> | minimum (smallest) value |
| [params.max] | <code>number</code> | <code>100</code> | maximum (largest) value |
| [params.step] | <code>number</code> |  | step between allowed values |
| [params.width] | <code>string</code> |  | width of slider (CSS, including unit) |
| [params.valueStyle] | <code>string</code> |  | value box CSS styling |
| [params.postText] | <code>string</code> |  | text after slider |

<a name="tfw.ajaxGet"></a>
### tfw.ajaxGet(o) ⇒ <code>Object</code>
Get data from server via AJAX.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - - Returns XMLHttpRequest object  
**See**

- tfw.ajaxIncludeParams
- tfw.ajaxOnErrorCode
- tfw.ajaxOnError


| Param | Type | Default | Description |
| --- | --- | --- | --- |
| o | <code>Object</code> |  | parameters object |
| o.url | <code>string</code> |  | URL of server script with data |
| o.onload | <code>function</code> |  | function to call when request has successfully completed |
| [o.autohide] | <code>number</code> | <code>0</code> | whether to show overlay after finishing (1 = yes after 500ms, 2 = yes immediately) |

<a name="tfw.encodeFormValues"></a>
### tfw.encodeFormValues(fields) ⇒ <code>string</code>
Encode all items as URL.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>string</code> - String, that can be used to call server via ajax  

| Param | Type | Description |
| --- | --- | --- |
| fields | <code>Object</code> | items to be encoded {key1:id1,key2:id2,...} |

<a name="tfw.decodeJSON"></a>
### tfw.decodeJSON(json) ⇒ <code>Object</code>
Decode JSON data, show error in case they are invalid.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - Object that was encoded in given JSON string.  

| Param | Type | Description |
| --- | --- | --- |
| json | <code>string</code> | JSON encoded data |

<a name="tfw.dynamicTable"></a>
### tfw.dynamicTable(params) ⇒ <code>Object</code>
Wrapper that creates a dynamic table and returns it's HTML node for inserting into DOM.Class instance's properties are mirrored into the HTML element.

**Kind**: static method of <code>[tfw](#tfw)</code>  
**Returns**: <code>Object</code> - table (HTML element)  
**See**: tfw.dynamicTableClass  

| Param | Type | Description |
| --- | --- | --- |
| params | <code>Object</code> | table parameters (see [dynamicTableClass](#tfw.dynamicTableClass)) |

<a name="prvek"></a>
## prvek
**Kind**: global class  

* [prvek](#prvek)
    * [new prvek()](#new_prvek_new)
    * [.seznamZatrzitek()](#prvek.seznamZatrzitek)
    * ~~[.tabulka()](#prvek.tabulka)~~
    * ~~[.radek()](#prvek.radek)~~
    * ~~[.sloupec()](#prvek.sloupec)~~
    * [.soubory()](#prvek.soubory)
    * [.barva()](#prvek.barva)
    * [.barvaSLegendou()](#prvek.barvaSLegendou)

<a name="new_prvek_new"></a>
### new prvek()
Function package for preparing HTML elements.

<a name="prvek.seznamZatrzitek"></a>
### prvek.seznamZatrzitek()
**Kind**: static method of <code>[prvek](#prvek)</code>  
**Todo**

- [ ] Move to [tfw](#tfw)

<a name="prvek.tabulka"></a>
### ~~prvek.tabulka()~~
***Deprecated***

**Kind**: static method of <code>[prvek](#prvek)</code>  
**See**: tfw.table  
<a name="prvek.radek"></a>
### ~~prvek.radek()~~
***Deprecated***

**Kind**: static method of <code>[prvek](#prvek)</code>  
**See**: tfw.tr  
<a name="prvek.sloupec"></a>
### ~~prvek.sloupec()~~
***Deprecated***

**Kind**: static method of <code>[prvek](#prvek)</code>  
**See**: tfw.td  
<a name="prvek.soubory"></a>
### prvek.soubory()
**Kind**: static method of <code>[prvek](#prvek)</code>  
**Todo**

- [ ] Remove dependencies on Triobo
- [ ] Move to [tfw](#tfw)

<a name="prvek.barva"></a>
### prvek.barva()
**Kind**: static method of <code>[prvek](#prvek)</code>  
**Todo**

- [ ] Remove dependencies on Triobo
- [ ] Move to [tfw](#tfw)

<a name="prvek.barvaSLegendou"></a>
### prvek.barvaSLegendou()
**Kind**: static method of <code>[prvek](#prvek)</code>  
**Todo**

- [ ] Remove dependencies on Triobo
- [ ] Move to [tfw](#tfw)

<a name="Dyntable"></a>
## ~~Dyntable~~
***Deprecated***

**Kind**: global class  
**See**: tfw.dynamicTable  
<a name="AJAX_LOADER"></a>
## AJAX_LOADER : <code>string</code>
HTML to show when some content is being loaded.

**Kind**: global constant  
