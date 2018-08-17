<template>
    <section id="heading" class="sidemenu--open">
        <div class="left">
            <a href="#" title="Search">
                <i class="fa fa-search" aria-hidden="true"></i>
            </a>
            <a href="#" title="Settings">
                <i class="fa fa-cog" aria-hidden="true"></i>
            </a>
            <a href="#" title="Toggle Fullscreen">
                <i class="fa fa-arrows-alt" aria-hidden="true"></i>
            </a>
            <a href="#" title="Notifications">
                <i class="fa fa-bullhorn" aria-hidden="true"></i>
            </a>
            <a href="#" title="Web View">
                <i class="fa fa-desktop" aria-hidden="true"></i>
            </a>
        </div>
        <div class="right">
            <a href="#" class="user montserrat" title="User">
                <img src="/public/images/users/gitasav.jpg" height="28px" width="28px">
                Gita Savitri
                <i class="fa fa-angle-down" aria-hidden="true"></i>
            </a>
            <a href="#" title="Lock Screen">
                <i class="fa fa-lock" aria-hidden="true"></i>
            </a>
        </div>
    </section>
</template>

<script>

export default {
    data () {
        return {

        }
    }
}

</script>

<style scoped>

    #heading {
        position: fixed;
        top: 0;
        left: 0;
        height: 60px;
        width: 100%;
        background: white;
        box-shadow: 0 1px 1px rgba(0,0,0,0.1);
    }

    #heading.sidemenu--open {
        padding-left: 280px;
    }

    #heading > div > a {
        float: left;
        width: 50px;
        height: 50px;
        margin-top: 5px;
        font-size: 20px;
        line-height: 50px;
        text-align: center;
        color: #858598;
    }

    #heading > .left {
        margin-left: 10px;
    }

    #heading > .right {
        margin-right: 10px;
    }

    .user img {
        border-radius: 50%;
        vertical-align: middle;
        margin-right: 10px;
    }

    .user {
        font-size: 13px !important;
        width: auto !important;
        font-weight: 600;
    }


</style>
