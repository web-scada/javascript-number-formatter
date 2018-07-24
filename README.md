# INTRODUCTION

This standalone number formatter is intended to be short and fast. As they are the main factors for a high performance JavaScript app. Development release is as short as 75 lines including license info, blank lines and comments. And production release is as small as 849 bytes.
```javascript
alert( format( "#,##0.####", 1234567.890)); //output: 1,234,567.89
```

The jQuery formatNumber version translates a number defined in an html tag.

```html
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
<script type="text/javascript" src="jquery.format_number.js"></script>

<div class="number">1234567.890</div>

<script>
$('div.number').formatNumber( {"format":"#,##0.####"} ); //output the div: 1,234,567.89
</script>
```


# BENEFITS

* Short, fast, flexible yet standalone. Only 75 lines including MIT license info, blank lines & comments.
* Accept standard number formatting like ```#,##0.00``` or with negation ```-000.####```.
* Accept any country format like ```# ##0,00, #,###.##, #'###.##``` or any type of non-numbering symbol.
* Accept any numbers of digit grouping. ```#,##,#0.000``` or ```#,###0.##``` are all valid.
* Accept any redundant/fool-proof formatting. ```##,###,##.#``` or ```0#,#00#.###0#``` are all OK.
* Auto number rounding.
* Simple interface, just supply mask & value like this: ```format( "0.0000", 3.141592)```
* Safe to minimize with Google Compiler in Advanced mode.

# LIMITATION

* No prefix or suffix is allowed except leading negation symbol. So ```$#,##0.00``` or``` #,###.##USD``` will not yield expected outcome. Use ```'$'+format('#,##0.00', 123.45)``` or ```format('#,##0.00', 456.789) + 'USD'```
* No scientific/engineering formatting.
* Not for date or phone formation.
* No color control.

# NOTE

When there's only one symbol is supplied, system will always treat the single symbol as Decimal. For instance, ```format( '#,###', 1234567.890)``` will output 1234567,890. To force a single symbol as Separator, add a trailing dot to the end like this: ```format( '#,###.', 1234567.890)``` which will then output 1,234,567.

# INFO
You may see some [examples in this demo/sample page](http://www.integraxor.com/developer/codes/js-formatter/format-sample.htm). This code was originally developed in Ecava IGX WEB [SCADA](http://www.integraxor.com/), if you know what's SCADA then you may be interested to [download a copy](http://www.integraxor.com/download-igx.html) to see this peace of code performs in real life application.


