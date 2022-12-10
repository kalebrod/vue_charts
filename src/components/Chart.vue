<template>
    <highcharts class="chart" :constructor-type="chart" :options="load_chart()"/>
</template>

<script>
export default {
    name: "TestChart",
    data() {
        return {
            data: {
                atual: [                            
                    [1276, 1.762, 'PAPEL0'],
                    [1249, 2.918, 'PAPEL1'],
                    [929, 2.251, 'PAPEL2'],
                    [1007, 1.705, 'PAPEL3'],
                    [1193, 2.111, 'PAPEL4'],
                    [1224, 2.163, 'PAPEL5'],
                    [1183, 2.083, 'PAPEL6'],
                    [1396, 2.657, 'PAPEL7'],
                    [1058, 2.384, 'PAPEL8'],
                    [1318, 0.898, 'PAPEL9'],
                    [1376, 1.955, 'PAPEL10'],
                    [1335, 0.512, 'PAPEL11'],
                    [1007, 0.823, 'PAPEL12'],
                    [1477, 0.636, 'PAPEL13'],
                    [1236, 2.971, 'PAPEL14'],
                    [1432, 0.624, 'PAPEL15'],
                    [1338, 2.834, 'PAPEL16'],
                    [1130, 1.907, 'PAPEL17'],
                    [926, 2.672, 'PAPEL18'],
                    [954, 1.683, 'PAPEL19']
                ],
                xp_bid: [                            
                    [1193, 2.169, 'PAPEL4'], 
                    [954, 1.744, 'PAPEL19']
                ],
                xp_ask: [                            
                    [1183, 1.937, 'PAPEL6'],
                    [1007, 1.643, 'PAPEL3'],
                    [1276, 1.565, 'PAPEL0']
                ],
                ativa_bid: [                            
                    [1318, 0.720, 'PAPEL9'],
                    [1376, 1.936, 'PAPEL10'],
                    [1183, 1.972, 'PAPEL6'],
                    [1396, 2.703, 'PAPEL7'],
                    [1432, 0.762, 'PAPEL15'],
                    [926, 2.522, 'PAPEL18'],
                    [929, 2.361, 'PAPEL2'],
                    [1130, 1.751, 'PAPEL17'],
                    [954, 1.605, 'PAPEL19'],
                ],
                ativa_ask: [                            
                    [1432, 0.4477931473236852, 'PAPEL15'],
                    [1130, 1.882430306822625, 'PAPEL17'],
                    [1236, 3.1169174583841013, 'PAPEL14'],
                    [1335, 0.47129296838763596, 'PAPEL11']
                ],
                cm_bid: [                            
                    [1130, 2.0616777145531815, 'PAPEL17'],
                    [1318, 0.7629745050379114, 'PAPEL9'],
                    [926, 2.82614596653382, 'PAPEL18'],
                    [1338, 2.8861783542184742, 'PAPEL16'],
                    [1193, 2.0956258251181943, 'PAPEL4'],
                    [1236, 2.8007784963834794, 'PAPEL14'],
                    [1335, 0.6269744489526216, 'PAPEL11'],
                    [1396, 2.5831547787550844, 'PAPEL7'],
                    [1183, 2.127589264059295, 'PAPEL6']
                ],
                cm_ask: [                            
                    [1376, 1.8143218295923176, 'PAPEL10'],
                    [1058, 2.2929724133553617, 'PAPEL8'],
                    [1007, 1.5695068307999624, 'PAPEL3'],
                    [1007, 0.7804083689785775, 'PAPEL12'],
                    [929, 2.391644298615561, 'PAPEL2'],
                    [1477, 0.5736187888372589, 'PAPEL13'],
                    [1183, 1.9947483628536578, 'PAPEL6'],
                    [1249, 2.9247198051159815, 'PAPEL1'],
                    [1130, 1.9907285531690564, 'PAPEL17']
                ],
                negocio: [                            
                    [987, 1.143, 'PAPEL1'],
                    [1249, 1.117, 'PAPEL2'],
                    [942, 2.478, 'PAPEL3'],
                    [1272, 1.365, 'PAPEL6'],
                    [1305, 0.71, 'PAPEL7'],
                    [909, 1.741, 'PAPEL8'],
                    [990, 2.243, 'PAPEL9'],
                ],
            }
        }
    },
    methods: {
        load_chart() {
            return  {
                chart: {
                    type: 'scatter',
                    zoomType: 'xy'
                },
                xAxis: {  
                    title: {
                        enabled: true,
                        text: 'Duration'
                    },
                    startOnTick: true,
                    endOnTick: true,
                    showLastLabel: true,
                },
                yAxis: {
                    title: {
                        text: 'Spread'
                    },
                    startOnTick: true,
                    endOnTick: true,
                    showLastLabel: true
                },
                plotOptions: {
                    scatter: {
                        tooltip: {
                            headerFormat: '<b>{series.name}</b><br>',
                            pointFormat: 'duration : {point.x}<br> spread : {point.y} <br> papel : {point.name}',
                        }
                    }
                },
                series: [
                    {
                        name: 'Spread Atual',
                        keys: ['x','y','name'],
                        marker: {
                            symbol: 'cross',
                            lineColor: null,
                            lineWidth: 3,
                            radius: 4,
                        },
                        color: '#23a2e7',
                        data: this.data.atual,
                    },
                    {
                        name: 'Xp_bid',
                        keys: ['x','y','name'],
                        marker: {
                            symbol: 'square'
                        },
                        color: '#f77f00',
                        data: this.data.xp_bid,
                    },
                    {
                        name: 'Xp_Ask',
                        keys: ['x','y','name'],
                        marker: {
                            symbol: 'triangle'
                        },
                        color: '#f77f00',
                        data: this.data.xp_ask,
                    },
                    {
                        name: 'Ativa_bid',
                        keys: ['x','y','name'],
                        marker: {
                            symbol: 'square'
                        },
                        color: '#1B1C22',
                        data: this.data.ativa_bid,
                    },
                    {
                        name: 'Ativa_Ask',
                        keys: ['x','y','name'],
                        marker: {
                            symbol: 'triangle'
                        },
                        color: '#1B1C22',
                        data: this.data.ativa_ask,
                    },
                    {
                        name: 'CM_bid',
                        keys: ['x','y','name'],
                        marker: {
                            symbol: 'square'
                        },
                        color: '#3EA923',
                        data: this.data.cm_bid,
                    },
                    {
                        name: 'CM_Ask',
                        keys: ['x','y','name'],
                        marker: {
                            symbol: 'triangle'
                        },
                        color: '#3EA923',
                        data: this.data.cm_ask,
                    },
                    {
                        name: 'Spread Negocio',
                        keys: ['x','y','name'],
                        marker: {
                            symbol: 'circle',
                            radius: 4,
                        },
                        color: '#d62828',
                        data: this.data.negocio,
                    },
                ]
            }
        }
    },

}
</script>
<style>
.chart {
    width: 100%;
    background-color: whitesmoke;
}
</style>