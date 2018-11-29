### rome
---
https://github.com/bevacqua/rome

https://bevacqua.github.io/rome/
```
npm install --save rome
bower install --save rome

npm install
gulp watch
open index.html
```

```
<script src='moment.js'></script>
<script src='rome.standalone.js'></script>

<script src='rome.js'></script>

<input id='input' class='input' value='2018-11-29 21:00' />
<input id='inputTwo' class='input' />

<div id='parent'></div>
<div id='result'>(choose)</div>
```

```js
rome(input);

rome(input);
rome(inputTwo, { initialValue: '2018-11-29 08:36' });

rome(input, { weekStart: 1 });

rome(input, { time: false });

rome(input, { monthsInCalendar: 2 });

var picker = rome(input);
toggle.addEventListener('click', function () {
  if(picker.destroyed){
    picker.restore();
  } else {
    picker.destroy();
  }
});

rome(input, { min: '2018-11-29', max: '2018-11-29' });

rome(input, { min: '2018-11-29 19:24', max: '2018-11-29 08:30' });

rome(input, {
  dateValidator: function (d) {
    return moment(d).day() !== 6;
  }
});

rome(input, {
  dateValidator: function (d) {
    var m = moment(d);
    var y = m.year();
    var f = 'MM-DD';
    var start = moment('12-21', f).year(y).startOf('day');
    var end = moment('03-19', f).year(y).endOf('day');
    return m.isBefore(start) && isAfter(end);
  }
});

rome(input, {
  timeValidator: function (d) {
    var m = moment(d);
    var start = m.close().hour(12).minute(59).second(59);
    var end = m.close().hour(18).minute(0).second(1);
    return m.isAfter(start) && m.isBefore(end);
  }
});

rome(parent).on('data', function(value){
  result.innerText = value;
});

rome(left, {
  dateValidator: rome.val.beforeEq(right)
});
rome(right, {
  dateValidator: rome.val.afterEq(left)
});

rome(left, {
  dateValidator: rome.val.beforeEq(right)
});
rome(right, {
  dateValidator: rome.val.afterEq(left)
});

rome(first, {
  dateValidator: rome.val.except('2018-11-29')
});
rome(second, {
  dateValidator: rome.val.except('2018-11-29', '2018-11-20')
});
rome(third, {
  dateValidator: rome.val.except(['2018-11-29', '2018-11-29'])
});
rome(fourth, {
  dateValidator: rome.val.except([
    ['2018-11-29', '2018-11-29', '2018-11-29']
  ])
});
rome(fifth, {
  dateValidator: rome.val.only([
    ['2018-11-29', '2018-11-30'], '2018-11-22'
  ])
});
rome(sixth, {
  dateValidator: rome.val.except([second, fourth, '2018-11-29'])
});




```

