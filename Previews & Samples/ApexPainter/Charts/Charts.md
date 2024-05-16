# Charts Samples

## Line Chart

![Line Chart](https://media.discordapp.net/attachments/1206055041065033833/1235109324142018620/lineChart.png?ex=66332cb2&is=6631db32&hm=19b5a800f85d78b2c24c554cf759fa1a2d278fdcae9b4a68e4b888c5f740b9d9&=&format=webp&quality=lossless&width=1082&height=662)

==- Code Sample
```js
    const data = {
        data: [
            [
                { label: 'January', y: 50 },
                { label: 'February', y: 65 },
                { label: 'March', y: 70 },
                { label: 'April', y: 85 },
                { label: 'May', y: 60 },
                { label: 'June', y: 75 },
                { label: 'July', y: 90 },
                { label: 'August', y: 80 },
                { label: 'September', y: 85 },
                { label: 'October', y: 70 },
                { label: 'November', y: 55 },
                { label: 'December', y: 60 },
            ],
            [
                { label: 'January', y: 45 },
                { label: 'February', y: 60 },
                { label: 'March', y: 50 },
                { label: 'April', y: 75 },
                { label: 'May', y: 80 },
                { label: 'June', y: 65 },
                { label: 'July', y: 70 },
                { label: 'August', y: 85 },
                { label: 'September', y: 90 },
                { label: 'October', y: 80 },
                { label: 'November', y: 70 },
                { label: 'December', y: 65 },
            ],
            [
                { label: 'January', y: 55 },
                { label: 'February', y: 70 },
                { label: 'March', y: 65 },
                { label: 'April', y: 80 },
                { label: 'May', y: 85 },
                { label: 'June', y: 80 },
                { label: 'July', y: 95 },
                { label: 'August', y: 75 },
                { label: 'September', y: 80 },
                { label: 'October', y: 65 },
                { label: 'November', y: 60 },
                { label: 'December', y: 70 },
            ],
        ],
        lineConfig: {
            yLabels: ['0', '20', '40', '60', '80', '100'],
            yaxisLabel: {
                label: 'No. Of Borrowed Books',
                color: 'white',
                size: 17,
                x: -2,
                y: -75
            },
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
                'blue': 'Action',
                'red': 'Adventure',
                'green': 'Comedy'
            },
            keysConfig: {
                fontColor: 'white',
                radius: 10,
                textPadding: 80,
                keyPadding: 45,
                lineWidth: 2, 
            },
            canvas: {
                fontColor: 'white',
                fontSize: 16,
                width: 800,
                height: 600,
                image: 'https://e0.pxfuel.com/wallpapers/594/871/desktop-wallpaper-chill-chill-nature.jpg',
            }
        }
    };
    
const chartBuffer = await painter.createChart(data, { chartType: 'line', chartNumber: 1 });
```
===

## Bar Chart

![Bar Chart](https://media.discordapp.net/attachments/1206055041065033833/1235092990461087805/barChart.png?ex=66331d7b&is=6631cbfb&hm=6865c35ddbdf10c0d6996ecefd729b5517e4d5ca9a958e78db07a690a6de7d71&=&format=webp&quality=lossless&width=883&height=662)

==- Code Sample
```js
const data = {
        chartData: {
            height: 600,
            width: 800,
            widthPerc: 0.8,
            heightPerc: 0.8,
            bg: {
                image: 'https://i.pinimg.com/originals/ae/41/07/ae4107956b28439588782359127047c2.jpg',
            },
            title: {
                title: 'Bar Chart Category',
                color: '#8f8d8d',
                size: 21
            },
            grid: {
                enable: true,
                color: '#2e2e2e',
                width: 1
            },
            labels: {
                color: '#8f8d8d',
                fontSize: 16
            },
            axis: {
                color: '#8f8d8d',
                size: 18
            }
        },
        xLabels: [0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 120], 
        yLabels: [0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100],
        data: {
            xAxis: [
                { label: 'Label 1', barColor: 'red', position: { startsXLabel: 10, endsXLabel: 25 }, value: 20 },
                { label: 'Label 2', barColor: 'red', position: { startsXLabel: 30, endsXLabel: 40 }, value: 60 },
                { label: 'Label 3', barColor: 'blue', position: { startsXLabel: 48, endsXLabel: 55 }, value: 40 },
                { label: 'Label 4', barColor: 'blue', position: { startsXLabel: 70, endsXLabel: 95 }, value: 80 },
                { label: 'Label 5', barColor: 'yellow', position: { startsXLabel: 100, endsXLabel: 110 }, value: 5 },
                { label: 'Label 6', barColor: 'yellow', position: { startsXLabel: 115, endsXLabel: 120 }, value: 100 }

            ],
            yAxis: [0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100],
            keys: {
            'red': 'Category 1',
            'blue': 'Category 2',
            'yellow': 'Category 3'
            }, // Legend keys
            xTitle: 'X-Title', // X-axis title
            yTitle: 'Y-Title', // Y-axis title
            labelStyle: { color: '#8f8d8d', size: 14 } // Bar label style
        }
    };

const chartBuffer = await painter.createChart(data, { chartType: 'bar', chartNumber: 1 });
```
===
