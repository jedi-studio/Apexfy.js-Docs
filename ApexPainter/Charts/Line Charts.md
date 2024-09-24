# Line Charts

This script utilizes the `ApexPainter` class from the `apexify.js` library to generate customizable line charts.

## Usage

1.Import the `ApexPainter` class from the `apexify.js` library:

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

3.Define options for the line chart:

```javascript
const data = {
    data: [
        [
            { label: 'January', y: 0 },
            { label: 'February', y: 23 },
            { label: 'March', y: 26 },
            { label: 'April', y: 80 },
            { label: 'May', y: 0 },
            { label: 'June', y: 90 },
            { label: 'July', y: 30 },
            { label: 'August', y: 48 },
            { label: 'Septemper', y: 67 },
            { label: 'October', y: 0 },
            { label: 'November', y: 0 },
            { label: 'December', y: 0 },
        ],
        [
            { label: 'January', y: 90 },
            { label: 'February', y: 20 },
            { label: 'March', y: 0 },
            { label: 'April', y: 0 },
            { label: 'May', y: 10 },
            { label: 'June', y: 55 },
            { label: 'July', y: 32 },
            { label: 'August', y: 72 },
            { label: 'Septemper', y: 40 },
            { label: 'October', y: 66 },
            { label: 'November', y: 89 },
            { label: 'December', y: 100 },
        ],
        [
            { label: 'January', y: 31 },
            { label: 'February', y: 23 },
            { label: 'March', y: 65 },
            { label: 'April', y: 73 },
            { label: 'May', y: 89 },
            { label: 'June', y: 91 },
            { label: 'July', y: 0 },
            { label: 'August', y: 3 },
            { label: 'Septemper', y: 19 },
            { label: 'October', y: 43 },
            { label: 'November', y: 5 },
            { label: 'December', y: 0 },
        ],
    ],
    lineConfig: {
        yLabels: ['0', '10', '20', '30', '40', '50', '60', '70', '80', '90', '100'],
        fillArea: [
            { color: 'rgba(255, 0, 0, 0.1)' },
            { color: 'rgba(275, 0, 0, 0.1)' },
            { color: 'rgba(225, 0, 0, 0.1)' },
        ],
        lineColor: ['blue', 'red', 'green'],
        plot: {
            enable: true,
            color: ['red', 'blue', 'orange'],
            size: 6
        },
        lineTension: [0.8, 0.3, 0.6],
        grid: {
            type: 'both',
            color: '#ccc',
            width: 1
        },
        keys: {
            'blue': 'Keyword 1',
            'red': 'Keyword 2',
            'green': 'Keyword 3'
        },
        canvas: {
            bgColor: 'black',
            fontColor: 'white',
            fontSize: 16,
            width: 800,
            height: 600,
            image: 'image url or path if you don\'t want a background color',
        }
    }
};
```

!!!info Note
The `canvas.image` option can be either an Image URL or a local Image path.
!!!

4.Generate the line chart:

```javascript
const chartBuffer = await painter.createChart(data, { chartType: 'line', chartNumber: 1 });
console.log(chartBuffer); // Returns a buffer image.
```

### Line Chart Parameters:

| Name          | Type      | Required | Description                                       |
| ------------- | --------- | -------- | ------------------------------------------------- |
| `yLabels`     | `Array`   | True     | Specifies the labels for the Y-axis.              |
| `fillArea`    | `Array`   | True     | Specifies the fill area configuration.            |
| `lineColor`   | `Array`   | True     | Specifies the color for each line.                |
| `plot`        | `Object`  | True     | Specifies the plot configuration.                 |
| `lineTension` | `Array`   | True     | Specifies the line tension for each line.         |
| `grid`        | `Object`  | True     | Specifies the grid configuration.                 |
| `keys`        | `Object`  | True     | Specifies the keys for different data categories. |
| `canvas`      | `Object`  | True     | Specifies the canvas configuration.               |

### Line Chart Data Parameters:

| Name      | Type      | Required | Description                             |
| --------- | --------- | -------- | --------------------------------------- |
| `data`    | `Array`   | True     | Specifies the data for the line chart. |
