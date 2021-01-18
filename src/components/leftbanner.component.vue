<template>
    <div class="leftSide">
        <div class="title">
            <div class="avatar">
                <img class="avatar-img"
                     alt="Picture of Markus"
                     src="../assets/markus_in_casual.jpg">

            </div>
            <div class="name">
                Markus <span class="boldFont">Böbel</span>
            </div>
            <div>
                {{ $t("DEGREE") }}
            </div>
        </div>
        <div class="skill-chart">
            <SkillsComponent />

        </div>
    </div>
</template>

<script>
    import SkillsComponent from "./skills.component";
    export default {
        name: "LeftBanner",
        components: {SkillsComponent}
    }
</script>

<style scoped lang="scss">
    @import "../variables";

    .leftSide {
        color: #FFF;
        font-size: 2em;
    }
    .name{
        color: #FFF;
        font-size: 2em;
    }

    .leftSide{

        @media only screen and (max-width: $breakpoint) {
            display: grid;

            grid-template-columns: 5% 90% 5%;

            grid-template-rows: 10% auto auto 10%;
            grid-template-areas: ". . ."
            ". content ."
            ". skills .";
        }
    }
    .title{
        grid-area: content;

        display: flex;
        align-items: center;
        flex-direction: column;
    }
    .skill-chart{
        width: 100%;
        grid-area: skills;
    }
    .avatar-img{
        border-radius: 50%;
        width:250px;
        height: 250px;
    }

</style>

<i18n>
    {
        "en": {
            "DEGREE": "M.Sc Information Systems"
        }
    }
</i18n>
