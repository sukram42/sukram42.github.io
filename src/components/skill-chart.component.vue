<script>
    import { HorizontalBar } from "vue-chartjs";
    export default {
        name: "SkillChart",
        props: ["dataset"],
        extends: HorizontalBar,
        data: () =>({
            options: {
                responsive: true,
                maintainAspectRatio: false
            }
        }),
        mounted() {
            this.renderChart(this.dataset, this.options)
        }
    }
</script>

<style scoped>

</style>
