<template>
    <section id="sidemenu" class="raleway">
        <div class="heading">
            <div class="left">
                <img src="/public/assets/logo28px-textwhite.png" height="10px">
                <span>Admin Panel</span>
            </div>
            <div class="right">
                <a href="#" title="Search">
                    <i class="fa fa-dedent" aria-hidden="true"></i>
                </a>
            </div>
        </div>
        <div class="scroll-sidebar">
            <ul class="menu-list">
                <li class="header montserrat">
                    <span>Overview</span>
                </li>
                <li>
                    <a href="#">
                        <i class="fa fa-dashboard" aria-hidden="true"></i>
                        <span>Dashboard</span>
                    </a>
                </li>
                <li class="header montserrat">
                    <span>Feed &amp; Post</span>
                </li>
                <li>
                    <router-link to="/artikel" exact>
                        <i class="fa fa-rss" aria-hidden="true"></i>
                        <span>Berita &amp; Artikel</span>
                    </router-link>
                    <router-link to="/artikel/new" class="right adder">
                        <i class="fa fa-plus-square" aria-hidden="true"></i>
                    </router-link>
                </li>
                <li>
                    <a href="#">
                        <i class="fa fa-bullhorn" aria-hidden="true"></i>
                        <span>Pengumuman</span>
                    </a>
                    <a href="#" class="right adder">
                        <i class="fa fa-plus-square" aria-hidden="true"></i>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <i class="fa fa-money" aria-hidden="true"></i>
                        <span>Beasiswa</span>
                    </a>
                    <a href="#" class="right adder">
                        <i class="fa fa-plus-square" aria-hidden="true"></i>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <i class="fa fa-link" aria-hidden="true"></i>
                        <span>Tautan Aktif</span>
                    </a>
                    <a href="#" class="right adder">
                        <i class="fa fa-plus-square" aria-hidden="true"></i>
                    </a>
                </li>
                <li class="header montserrat">
                    <span>Component</span>
                </li>
                <li>
                    <a href="#">
                        <i class="fa fa-home" aria-hidden="true"></i>
                        <span>Halaman Utama</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <i class="fa fa-users" aria-hidden="true"></i>
                        <span>Profil</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <i class="fa fa-user-md" aria-hidden="true"></i>
                        <span>Sekilas Prodi</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <i class="fa fa-vcard" aria-hidden="true"></i>
                        <span>Kontak</span>
                    </a>
                </li>
                <li class="header montserrat">
                    <span>Development</span>
                </li>
                <li>
                    <a href="#">
                        <i class="fa fa-code" aria-hidden="true"></i>
                        <span>Unduh Source Code</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <i class="fa fa-book" aria-hidden="true"></i>
                        <span>Referensi Web</span>
                    </a>
                </li>
            </ul>
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

    #sidemenu {
        position: fixed;
        width: 280px;
        height: 100%;
        left: 0;
        top: 0;
        background-color: #272634;
    }

    .heading {
        width: 100%;
        height: 60px;
        background: rgba(0,0,0,0.22);
        padding: 0 20px;
    }

    .heading img {
            margin-top: 19px;
    }

    .heading span {
        display: block;
        font-size: 11px;
        color: rgba(255,255,255,0.5);
        font-weight: 600;
    }

    .heading > div > a {
        float: left;
        height: 50px;
        margin-top: 5px;
        font-size: 20px;
        line-height: 50px;
        text-align: center;
        color: #858598;
    }

    .scroll-sidebar {
        width: 100%;
        height: calc(100% - 60px);
        overflow-x: hidden;
        overflow-y: auto;
    }

    .menu-list {
        padding: 5px 20px;
    }

    .menu-list > li {
        margin: 9px 0;
    }

    .menu-list > li.header {
        padding: 5px 0;
        font-size: 12px;
        text-transform: uppercase;
        font-weight: 700;
        color: rgba(255,255,255,.5);
        letter-spacing: 1px;
    }

    .menu-list a {
        color: #858598;
        font-size: 13px;
        font-weight: 500;
        transition: color 0.2s ease;
    }

    .menu-list a.active {
        color: #C9C7EF;
        font-weight: 600;
    }

    .menu-list a:hover {
        color: #C9C7EF;
    }

    .menu-list a > i.fa {
        background : rgba(0,0,0,.31);
        font-size: 16px;
        width: 32px;
        height: 32px;
        line-height: 33px;
        text-align: center;
        margin-right: 10px;
        opacity: 0.6;
    }

    .menu-list a.active > i.fa {
        color: #fff!important;
    }

    .adder i {
        background-color: transparent !important;
        margin-right: 0 !important;
        width: auto !important;
    }

    .router-link-active {
        color: #C9C7EF !important;
        font-weight: 600 !important;
    }

</style>
