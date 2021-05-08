<script>
    import { HorizontalBar } from "vue-chartjs";
    export default {
        name: "SkillChart",
        props: ["dataset"],
        extends: HorizontalBar,
        data: () =>({
            options: {
                responsive: true,
                maintainAspectRatio: false,
                legend: {

                    labels: {
                        fontColor: "#FFF",
                        fontSize: 18
                    }
                },
                scaleShowHorizontalLines: false,
                scales: {
                    yAxes: [{
                        gridLines:{
                            display: false
                        },
                        ticks: {
                            fontColor: "white",
                            fontSize: 18,
                            stepSize: 1,
                            beginAtZero: true,
                            barThickness: 1,
                        }
                    }],
                    xAxes: [{
                        barThickness:1,
                        gridLines:{
                            display: false
                        },
                        ticks: {
                            display: false
                        }
                    }]
                }
                },
        }),
        mounted() {
            this.renderChart(this.dataset, this.options)
        }
    }
</script>

<style scoped>

</style>
