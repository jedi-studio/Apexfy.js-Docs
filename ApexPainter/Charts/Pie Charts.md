# Pie Charts

This script utilizes the `ApexPainter` class from the `apexify.js` library to generate customizable pie charts.

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

3.Define options for the pie chart:

```javascript
const data = {
  data: [
    { label: 'Category A', color: '#ff5733', value: 30, key: 'A' },
    { label: 'Category B', color: '#33ff57', value: 20, key: 'B' },
    { label: 'Category C', color: '#5733ff', value: 25, key: 'C' },
    { label: 'Category D', color: '#ffff33', value: 15, key: 'D' },
    { label: 'Category E', color: '#33ffff', value: 10, key: 'E' }
  ],
  pieConfig: {
    pieData: {
        x: -150,
        y: 0,
        boxes: {
            colors: 'blue',
            labelColor: 'black',
            fontSize: 13,
            labelDistance: 60,
            width: 30,
            height: 40
        },
        radius: 100,
    },
    stroke: {
      color: 'white',
      size: 2
    },
    title: {
      text: 'Pie Chart',
      color: 'black',
      fontSize: 24,
      x: -20,
      y: -170
    },
    keyBox: {
      bgcolor: '#ffffff',
      width: 300,
      height: 300,
      radius: 20,
      x: 800,
      y: 50,
      content: {
        keyTitle: {
            text: `Keys`,
            fonstSize: 20,
            x: 20,
            y: 30,
        },
        keys: {
            x: 20,
            y: 30,
            fontSize: 14,
        }
      }
    },
    canvas: {
      width: 1200,
      height: 400,
      bgcolor: 'gray'
    }
  }
};
```

4.Generate the pie chart:

```javascript
const chartBuffer = await painter.createChart(data, { chartType: 'pie', chartNumber: 1 });
console.log(chartBuffer); // Returns a buffer image.
```

### Pie Chart Parameters:

| Name      | Type      | Required | Description                                     |
| --------- | --------- | -------- | ----------------------------------------------- |
| `pieData` | `Object`  | True     | Specifies the data for the pie chart.           |
| `stroke`  | `Object`  | True     | Specifies the stroke configuration.             |
| `title`   | `Object`  | True     | Specifies the title configuration.              |
| `keyBox`  | `Object`  | True     | Specifies the key box configuration.            |
| `canvas`  | `Object`  | True     | Specifies the canvas configuration.             |

### Pie Chart Data Parameters:

| Name      | Type      | Required | Description                             |
| --------- | --------- | -------- | --------------------------------------- |
| `data`    | `Array`   | True     | Specifies the data for the pie chart.   |
