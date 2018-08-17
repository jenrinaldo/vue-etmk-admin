<template>
    <section id="main-routes">
        <main>
            <router-view></router-view>
        </main>
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

<style>

    #main-routes {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        padding-top: 60px;
        padding-left: 280px;
        background: #F4F5F7;
    }

    main {
        position: relative;
        overflow-y: auto;
        overflow-x: hidden;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        padding: 20px 30px;
    }

    .page-title {
        padding: 20px 30px;
        position: relative;
        background: rgba(252,252,252,.89);
        margin: -20px -30px 30px;
    }

    .page-title h2 {
        font-size: 18px;
        padding: 0;
        font-weight: 600;
        margin: -5px 0 0;
        color: #414C59;
        line-height: 25px;
    }

    .page-title p {
        color: #3e4855;
        opacity: 0.6;
        font-size: 13px;
    }

    .panel {
        margin-bottom: 20px;
        box-shadow: 0 1px 1px rgba(0,0,0,.05);
        background-color: #fff;
        padding: 15px 20px;
        border-radius: 4px;
    }

    .title-hero {
        margin: -15px -20px 15px;
        padding: 10px 15px;
        font-size: 14px;
        border-bottom: #F7F7F7 solid 1px;
        font-weight: 500;
        color: #3e4855;
        line-height: 20px;
    }

    .form-group {
        margin-bottom: 15px;
    }

    .control-label {
        padding-top: 7px;
        margin-bottom: 0;
        margin-top: 0;
        text-align: right;
    }

    label {
        display: block;
        font-weight: 700;
        font-size: 13px;
    }

    .form-control {
        font-size: 13px;
        display: block;
        float: none;
        background-color: #fff;
        width: 100%;
        height: 34px;
        border-radius: 3px;
        padding: 6px 12px;
        color: #2b2f33;
        border: 1px solid #dfe8f1;
        box-shadow: inset 1px 1px 3px #f6f6f6;
    }

    textarea {
        overflow: auto;
        resize: vertical;
        min-height: 150px;
    }

    span.field-error {
        color: #f62b70;
        font-size: 11px;
        margin-top: 8px;
        display: block;
    }

    .form-control.field-error {
        border-color: #f62b70;
    }

    .image-preview {
        height: auto;
        margin-bottom: 9px;
        border-style: dashed;
        text-align: center;
        font-size: 12px;
        color: rgba(62,72,85,0.4);
        padding: 12px;
    }

    .image-preview span {
        margin: 40px 0;
        display: block;
    }

    .image-preview img {
        width: 100%;
        display: block;
    }

    .btn {
        border-radius: 3px;
        font-size: 12px;
        display: inline-block;
        padding: 12px;
        height: 34px;
        min-width: 34px;
        background: #f62b70;
        text-align: center;
        cursor: pointer;
        color: #fff;
        font-weight: 700;
        text-transform: uppercase;
    }

    .btn-lg {
        padding: 0 16px;
        line-height: 44px;
        font-size: 15px;
        height: 46px;
        min-width: 56px;
    }

    .btn, .form-control {
        font-family: 'Raleway', sans-serif;
    }

    .btn-note {
        font-size: 12px;
        color: rgba(62,72,85,0.6);
        margin: 0 10px;
    }

    .panel-separator {
        width: 100%;
        height: 1px;
        border-bottom: #F1F1F1 solid 1px;
        margin-bottom: 15px;
    }

    .mrg15 {
        margin-bottom: 15px;
    }

    .left-align {
        text-align: left;
    }

    .right-align {
        text-align: right;
    }

    .center-align {
        text-align: center;
    }

    .content-box {
        background: #EFEFEF;
        border: 1px solid rgba(158,173,195,.16);
        padding: 20px;
        margin: 20px 0;
        border-radius: 3px;
        display: block;
    }

</style>
