<template>
    <highcharts class="chart" :constructor-type="chart" :options="load_chart()"/>
</template>

<script>
export default {
    name: "HistChart",
    data() {
        return {
            data: {
                vol: [1193, 2169, 1500],
                rel: [1.762, 2.918, 0.467],
                cat: ['2022-11-12','2022-11-14','2022-11-16']
            }
        }
    },
    methods: {
        load_chart() {
            return  {
                chart: {
                    zoomType: 'xy'
                },
                xAxis: {  
                    title: {
                        enabled: true,
                        text: 'Data comite'
                    },
                    categories: this.data.cat
                },
                yAxis: [{
                    title: {
                        text: 'Volume'
                    }
                },  {
                    title: {
                        text: 'Relevancia'
                    },
                    opposite: true,
                }], 
                tooltip: {
                    shared: true
                },
                series: [
                    {
                        name: 'Volume',
                        type: 'column',
                        color: '#23a2e7',
                        data: this.data.vol,
                    },
                    {
                        name: 'Relevancia',
                        type: 'spline',
                        color: '#f77f00',
                        data: this.data.rel,
                        yAxis: 1,
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