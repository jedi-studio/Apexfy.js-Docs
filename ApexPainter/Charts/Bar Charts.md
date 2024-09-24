# Bar Charts

This script utilizes the `ApexPainter` class from the `apexify.js` library to generate customizable bar charts.

## Usage

1. Import the `ApexPainter` class from the `apexify.js` library:

+++ JS

```javascript
const { ApexPainter } = require('apexify.js'); 
```

+++ TS

```typescript
import { ApexPainter } from 'apexify.js'; 
```

+++

2.Create an instance of the `ApexPainter` class:

```javascript
const painter = new ApexPainter();
```

3.Define options for the chart:

```javascript
const data = {
    
    chartData: {
    height: 600,
    width: 800,
    widthPerc: 0.8,
    heightPerc: 0.8,
    title: {
        title: 'Test chart',
        color: 'yellow',
        size: 25,
    },
    bg: {
       image: 'https://png.pngtree.com/thumb_back/fh260/background/20211118/pngtree-financial-technology-data-graph-image_908921.jpg',
        bgColor: 'darkgray'
      }, 
    grid: {
        enable: true,
        color: 'lightgray',
        width: 3
    },
    axis: {
        color: 'black',
        size: 16,
    },
    labels: {
        color: 'black',
        fontSize: 12,
    }
  },
    xLabels: [0, 10, 20, 30, 40, 90, 110, 130, 150, 180, 190],
    yLabels: [0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100],
    data: {
        xAxis: [
            { label: 'Label 1', barColor: 'red', stroke: { color: '', width: 3 }, value: 20, position: { startsXLabel: 8, endsXLabel: 19 } },
            { label: 'Label 2', barColor: 'green', value: 30, position: { startsXLabel: 22, endsXLabel: 27 } },
            { label: 'Label 3', barColor: 'blue', value: 40, position: { startsXLabel: 43, endsXLabel: 50 } },
            { label: 'Label 4', barColor: 'yellow', value: 48, position: { startsXLabel: 78, endsXLabel: 89 } },
            { label: 'Label 5', barColor: 'yellow', value: 10, position: { startsXLabel: 105, endsXLabel: 120 } },
            { label: 'Label 6', barColor: 'yellow', value: 15, position: { startsXLabel: 123, endsXLabel: 132 } },
            { label: 'Label 7', barColor: 'yellow', value: 5, position: { startsXLabel: 139, endsXLabel: 154 } },
            { label: 'Label 8', barColor: 'yellow', value: 3, position: { startsXLabel: 163, endsXLabel: 169 } },
            { label: 'Label 9', barColor: 'yellow', value: 74, position: { startsXLabel: 170, endsXLabel: 178 } },
            { label: 'Label 10', barColor: 'yellow', value: 99, position: { startsXLabel: 178, endsXLabel: 185 } },
            { label: 'Label 11', barColor: 'green', value: 60, position: { startsXLabel: 31, endsXLabel: 35 } },
            { label: 'Label 12', barColor: 'green', value: 55, position: { startsXLabel: 36, endsXLabel: 41 } },
            { label: 'Label 13', barColor: 'green', value: 83, position: { startsXLabel: 60, endsXLabel: 76 } },

        ],
        yAxis: [0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 120],
        keys: {
            'red': 'Label 1',
            'green': 'Label 2',
            'blue': 'Label 3',
            'yellow': 'Lable 4'
        },
        keyColor: '',
        xTitle: 'X Axis Title',
        yTitle: 'Y Axis Title',
        labelStyle: {
            color: 'blue',
            size: 12
        }
    },
};
```

!!!info Note
 The `bg.image` option can be either an Image URL or Local Image.
!!!

4.Generate the chart:

```javascript
const chartBuffer = await painter.createChart(data, { chartType: 'bar', chartNumber: 1 });
console.log(chartBuffer); // Returns a buffer image.
```

### Chart Parameters:

| Name              | Type        | Required | Description                                           |
| ----------------- | ----------- | -------- | ----------------------------------------------------- |
| `height`          | `number`    | False    | Specifies the height of the chart canvas.            |
| `width`           | `number`    | False    | Specifies the width of the chart canvas.             |
| `widthPerc`       | `number`    | False    | Specifies the width percentage of the chart canvas.  |
| `heightPerc`      | `number`    | False    | Specifies the height percentage of the chart canvas. |
| `title`           | `Object`    | False    | Specifies the title configuration.                    |
| `bg`              | `Object`    | False    | Specifies the background configuration.              |
| `grid`            | `Object`    | False    | Specifies the grid configuration.                    |
| `axis`            | `Object`    | False    | Specifies the axis configuration.                    |
| `labels`          | `Object`    | False    | Specifies the label configuration.                   |
| `xLabels`         | `Array`     | True     | Specifies the labels for the X-axis.                |
| `yLabels`         | `Array`     | True     | Specifies the labels for the Y-axis.                |
| `data`            | `Object`    | True     | Specifies the data for the chart.                    |

### Chart Data Parameters:

| Name              | Type        | Required | Description                                           |
| ----------------- | ----------- | -------- | ----------------------------------------------------- |
| `xAxis`           | `Array`     | True     | Specifies the data for the X-axis.                   |
| `yAxis`           | `Array`     | True     | Specifies the data for the Y-axis.                   |
| `keys`            | `Object`    | True     | Specifies the keys for different data categories.    |
| `keyColor`        | `string`    | False    | Specifies the color for the keys.                   |
| `xTitle`          | `string`    | False    | Specifies the title for the X-axis.                  |
| `yTitle`          | `string`    | False    | Specifies the title for the Y-axis.                  |
| `labelStyle`      | `Object`    | False    | Specifies the style for the labels.                  |
