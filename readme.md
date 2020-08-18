
## Installing

`npm install d3-timeline-chart --save`

## Example

```javascript
'use strict';
const element = document.getElementById('chart');
const data = [{
    label: 'Name',
    data: [{
        type: TimelineChart.TYPE.POINT,
        at: new Date([2015, 1, 11])
    }, {
        type: TimelineChart.TYPE.POINT,
        at: new Date([2015, 1, 15])
    }, {
        type: TimelineChart.TYPE.POINT,
        at: new Date([2015, 3, 10])
    }, {
        label: 'I\'m a label',
        type: TimelineChart.TYPE.INTERVAL,
        from: new Date([2015, 2, 1]),
        to: new Date([2015, 3, 1])
    }, {
        type: TimelineChart.TYPE.POINT,
        at: new Date([2015, 6, 1])
    }, {
        type: TimelineChart.TYPE.POINT,
        at: new Date([2015, 7, 1]),
        customClass: 'custom-class'
    }]
}];

const timeline = new TimelineChart(element, data, {
    tip: function(d) {
        return d.at || `${d.from}<br>${d.to}`;
    }
});
```

## Config

Available config parameters

### intervalMinWidth (8)
This allows you to define a minimum width for an interval element. Sometimes, when you zoom out too much you might still want to be able to visualize the interval. It defaults to 8.

### tip (undefined)
A function that receives as parameter a data point and returns an HTML text to be displayed as a tooltip

