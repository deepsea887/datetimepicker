# Amaze UI Datetime Picker
---

该项目来自 [bootstrap-datetimepicker](https://github.com/smalot/bootstrap-datetimepicker)，只修改了 `CSS` 文件，使用需要结合原有的 `class` 和 Amaze UI 混合使用。

## 案例

时间选择器插件参数 `format` ：设置时间格式

```html
<input type="text" value="2015-02-15 21:05" id="datetimepicker" class="am-form-field">
```
```javascript
$('#datetimepicker').datetimepicker({
  format: 'yyyy-mm-dd hh:ii'
});
```

也可以通过 `data-date-format` 来设置时间格式

```html
<input type="text" value="2015-02-14 21:05" id="datetimepicker" data-date-format="yyyy-mm-dd hh:ii">
```
```javascript
$('#datetimepicker').datetimepicker();
```

结合 Amaze Ui 组件

结合 Amaze UI Class `.am-input-group` 来实现组件样式，其中 Class `.date`、`.add-on`、`.icon-th` 都在原 JS 中有引用，使用时务必写上。

```html
<div class="am-input-group date" id="datetimepicker" data-date="12-02-2012" data-date-format="dd-mm-yyyy">
  <input size="16" type="text" value="2015-02-14 14:45" class="am-form-field" readonly>
  <span class="am-input-group-label add-on"><i class="icon-th am-icon-calendar"></i></span>
</div>
```
```javascript
$('#datetimepicker').datetimepicker();
```

内联调用形式：

```html
<div id="datetimepicker"></div>
```
```javascript
$('#datetimepicker').datetimepicker();
```

## 使用

```javascript
$('.datetimepicker').datetimepicker()
```

## 依赖和编译

克隆项目后，安装好

```bash
$ lessc less/amazeui.datetimepicker.less datetimepicker.css
```

## 参数

All options that take a "Date" can handle a `Date` object; a String formatted according to the given `format`; or a timedelta relative to today, eg '-1d', '+6m +1y', etc, where valid units are 'd' (day), 'w' (week), 'm' (month), and 'y' (year).

需要按照 ISO-8601 日期和时间的表示方法，设置你的时间格式 `format` :

* yyyy-mm-dd
* yyyy-mm-dd hh:ii
* yyyy-mm-ddThh:ii
* yyyy-mm-dd hh:ii:ss
* yyyy-mm-ddThh:ii:ssZ

### format

String.  Default: 'mm/dd/yyyy'

The date format, combination of p, P, h, hh, i, ii, s, ss, d, dd, m, mm, M, MM, yy, yyyy.

* p : meridian in lower case ('am' or 'pm') - according to locale file
* P : meridian in upper case ('AM' or 'PM') - according to locale file
* s : seconds without leading zeros
* ss : seconds, 2 digits with leading zeros
* i : minutes without leading zeros
* ii : minutes, 2 digits with leading zeros
* h : hour without leading zeros - 24-hour format
* hh : hour, 2 digits with leading zeros - 24-hour format
* H : hour without leading zeros - 12-hour format
* HH : hour, 2 digits with leading zeros - 12-hour format
* d : day of the month without leading zeros
* dd : day of the month, 2 digits with leading zeros
* m : numeric representation of month without leading zeros
* mm : numeric representation of the month, 2 digits with leading zeros
* M : short textual representation of a month, three letters
* MM : full textual representation of a month, such as January or March
* yy : two digit representation of a year
* yyyy : full numeric representation of a year, 4 digits

### weekStart

设置开始星期几的选择：接受整数 `0 - 6`，默认为 `0`，0 (Sunday) 到 6 (Saturday)。  

### startDate

设置时间开始参数：接受 `Date` 类型值，开始时间前面的日期将被设置为 `disabled`。

### endDate

设置结束时间参数：接受 `Date` 类型值，结束时间后面的日期将被设置为 `disabled`。

### daysOfWeekDisabled

禁用星期的列数：接受 `String` 或 `Array` 类型参数

- 默认值为 `'', []` 
- 示例：设置周六和周日禁用: `daysOfWeekDisabled: '0,6'` 或者 `daysOfWeekDisabled: [0,6]`。

### autoclose

设置时间后自动关闭时间选择器面板，参数类型：`Boolean` 默认值为：`false` 不关闭。

### startView

视图模式，通过参数 `startView` 设置日历初始视图模式，可以接受 `Number` | `String` 类型：

- `0` 或者 `hour`: 显示分
- `1` 或者 `days`: 显示小时
- `2` 或者 `month`: 显示天（默认）
- `3` 或者 `year`: 显示月
- `4` 或者 `decade`: 显示年

### minView

最小视图模式，可以接受 `Number` | `String` 类型：

- `0` 或者 `hour`: 显示分（默认）
- `1` 或者 `days`: 显示小时
- `2` 或者 `month`: 显示天
- `3` 或者 `year`: 显示月
- `4` 或者 `decade`: 显示年

### maxView

最大视图模式，可以接受 `Number` | `String` 类型：

- `0` 或者 `hour`: 显示分
- `1` 或者 `days`: 显示小时
- `2` 或者 `month`: 显示天
- `3` 或者 `year`: 显示月
- `4` 或者 `decade`: 显示年（默认）

### todayBtn

是否显示按钮 Today ，点击 Today 会跳转到今日的时间，默认为 `false`

### todayHighlight

是否高亮当日的日期，默认为 `false`。

### keyboardNavigation

是否允许键盘选择时间，默认为 `true`。

### language

String.  Default: 'en'

The two-letter code of the language to use for month and day names.  These will also be used as the input's value (and subsequently sent to the server in the case of form submissions).  Currently ships with English ('en'), German ('de'), Brazilian ('br'), and Spanish ('es') translations, but others can be added (see I18N below).  If an unknown language code is given, English will be used.

### forceParse

Boolean.  Default: true

Whether or not to force parsing of the input value when the picker is closed.  That is, when an invalid date is left in the input field by the user, the picker will forcibly parse that value, and set the input's value to the new, valid date, conforming to the given `format`.

### minuteStep

设置分钟视图时间间隔数，默认为 `5`。


### pickerReferer : deprecated

String.  Default: 'default'

The referer element to place the picker for the component implementation. If you want to place the picker just under the input field, just specify <code>input</code>.

### pickerPosition 

设置选择器的定位方式，接受 `String` 类型：

- `'bottom-right'` (默认)
- `'bottom-left'`
- `'top-right'`
- `'top-left'`

### viewSelect

时间更新设置，默认为选择分面板时更新时间，可以接受 `Number` | `String` 类型：

- `0` 或者 `hour`: 显示分（默认）
- `1` 或者 `days`: 显示小时
- `2` 或者 `month`: 显示天
- `3` 或者 `year`: 显示月
- `4` 或者 `decade`: 显示年

### showMeridian

是否显示 AM 和 PM 分隔小时面板。默认值为 `false`。

### initialDate

设置时间选择器初始化的时间值，默认情况下是现在，你可以指定其他时间，`initialDate` 接受 `Date` | `String`， 默认值为: `new Date()`。

### onRender

渲染日历时调用的函数，比如 `.disabled` 设置禁用日期。

```javascript
var nowTemp = new Date();
var now = new Date(nowTemp.getFullYear(), nowTemp.getMonth(), nowTemp.getDate(), 0, 0, 0, 0);
$('#date-end')
  .datetimepicker({
    onRender: function(date) {
      return date.valueOf() < now.valueOf() ? 'disabled' : '';
    }
  });
```

组件结合

```html
<div class="am-input-group date form_datetime-1">
  <input size="16" type="text" value="2015-02-14 14:45" class="am-form-field" readonly>
  <span class="am-input-group-label add-on"><i class="icon-th am-icon-calendar"></i></span>
</div>
```

带有删除的组件结合

```html
<div class="am-input-group date form_datetime-3" data-date="2015-02-14 14:45">
  <input size="16" type="text" value="" class="am-form-field" readonly>    
  <span class="add-on am-input-group-label"><i class="icon-remove am-icon-close"></i></span>
  <span class="add-on am-input-group-label"><i class="icon-th am-icon-calendar"></i></span>
</div>
```

## 方法

### .datetimepicker(options)

初始化一个时间选择器

### remove

删除

```javascript
$('#datetimepicker').datetimepicker('remove');
```

### show

显示

```javascript
$('#datetimepicker').datetimepicker('show');
```

### hide

隐藏

```javascript
$('#datetimepicker').datetimepicker('hide');
```

### update

Arguments:

* currentDate (Date).

更新指定的时间。

```javascript
$('#datetimepicker').datetimepicker('update', new Date());
```

如果更新时间为现在时间，则不需要传值。

```javascript
$('#datetimepicker').datetimepicker('update');
```

### setStartDate

设置开始时间，小于开始时间的则不能选中并设置 `disabled`，`setStartDate` 接受：`String` 值。

```javascript
$('#datetimepicker').datetimepicker('setStartDate', '2015-01-01');
```

如果忽略该值，将不启用该选项。

```javascript
$('#datetimepicker').datetimepicker('setStartDate');
$('#datetimepicker').datetimepicker('setStartDate', null);
```

### setEndDate

设置结束时间，大于结束时间的则不能选中并设置 `disabled` ，`setEndDate` 接受：`String` 值。

```javascript
$('#datetimepicker').datetimepicker('setEndDate', '2014-12-31');
```

如果忽略该值，选项无效。

```javascript
$('#datetimepicker').datetimepicker('setEndDate');
$('#datetimepicker').datetimepicker('setEndDate', null);
```

### setDaysOfWeekDisabled

禁用星期的列数：`setDaysOfWeekDisabled` 接受 `String` 或 `Array` 类型参数。

```javascript

// 周日和周六将被禁用
$('#datetimepicker').datetimepicker('setDaysOfWeekDisabled', [0,6]);

```

如果忽略该值，选项无效。

```javascript
$('#datetimepicker').datetimepicker('setDaysOfWeekDisabled');
$('#datetimepicker').datetimepicker('setDaysOfWeekDisabled', null);
```

## 事件

### show

时间选择器显示时触发。

```javascript
$('#date-end')
  .datetimepicker()
  .on('show', function(ev){
    console.log('datetimepciker 显示了');
  });
```

### hide

时间选择器隐藏时触发。

```javascript
$('#date-end')
  .datetimepicker()
  .on('hide', function(ev){
    console.log('datetimepciker 将隐藏');
  });
```

### changeDate

时间日期发生修改时触发，通过 `ev.date` 获取修改后的时间。

```javascript
$('#date-end')
  .datetimepicker()
  .on('changeDate', function(ev){
    if (ev.date.valueOf() < date-start-display.valueOf()){
      ....
    }
  });
```

### changeYear

年份修改时触发。

### changeMonth

月份修改时触发。

### outOfRange

Fired when you pick a date before the *startDate* or after the *endDate* or when you specify a date via the method *setDate* or *setUTCDate*..

## 键盘控制导航

### up, down, left, right arrow keys

- 上、下、左、右键控制选择日期。

- `Shift` + 上或者左向前移动一个月，`Shift` + 下或右向后移动一个月。

- `Ctrl` + 上或者左向前移动一个年，`Ctrl` + 下或右向后移动一个年。

### escape

`ESC` 键退出激活的时间选择器。

### enter

`Enter` 回车键能够选择日期。

## 鼠标滚轮导航

### 依赖

支持鼠标滚轮导航需要依赖 [jQuery Mouse Wheel Plugin](https://github.com/brandonaaron/jquery-mousewheel) 

### 配置参数

#### wheelViewModeNavigation

是否支持使用鼠标滚轮浏览不同的视图模式，`wheelViewModeNavigation` 默认为 `false`。

#### wheelViewModeNavigationInverseDirection

Boolean.  Default: false

Whether or not to reverse the direction of scrolling. Default is scroll up to the decade view.

#### wheelViewModeNavigationDelay

设置面板滚动时间间距，`wheelViewModeNavigationDelay` 默认值为 `100`。

#### About viewSelect option

The recommended value for viewSelect option is 4 when this feature is enable. That means you can easily update any the value in every view. This option value is applied in the demo page.

### Feature Demo

支持鼠标滚轮控制器的[Demo](http://lyonlai.github.io/bootstrap-datetimepicker/demo.html) 

## I18N

The plugin supports i18n for the month and weekday names and the `weekStart` option.  The default is English ('en'); other available translations are avilable in the `js/locales/` directory, simply include your desired locale after the plugin.  To add more languages, simply add a key to `$.fn.datetimepicker.dates`, before calling `.datetimepicker()`.  Example:

```javascript
$.fn.datetimepicker.dates['en'] = {
  days: ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"],
  daysShort: ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"],
  daysMin: ["Su", "Mo", "Tu", "We", "Th", "Fr", "Sa", "Su"],
  months: ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"],
  monthsShort: ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"],
  today: "Today"
};
```

You can override the default date format in the language configuration with `format` attribute.
Example:

```javascript
$.fn.datetimepicker.dates['pt-BR'] = {
  format: 'dd/mm/yyyy'
};
```

Right-to-left languages may also include `rtl: true` to make the calendar display appropriately.

If your browser (or those of your users) is displaying characters wrong, chances are the browser is loading the javascript file with a non-unicode encoding.  Simply add `charset="UTF-8"` to your `script` tag:

```html
<script type="text/javascript" src="bootstrap-datetimepicker.de.js" charset="UTF-8"></script>
```
