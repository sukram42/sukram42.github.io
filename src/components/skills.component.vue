<template>
    <SkillChart :dataset="this.dataset"/>
</template>

<script>
    import SkillChart from "./skill-chart.component";

    export default {
        name: "SkillsComponent",
        components: {SkillChart},
        data () {
            return {
                dataset: {
                    labels: ["SQL", "Python", "Tensorflow"],
                    datasets: [
                        {
                            label: "Data 1",
                            backgroundColor: "#E7E6E6",
                            data: [10, 15, 30]
                        }
                    ]
                }
            }
        },
        methods:{}

    }
</script>

<style scoped>

</style>
