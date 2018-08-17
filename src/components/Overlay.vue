<template>
	<div class="overlay-fixed raleway">
		<div v-if="" class="notification-bar" v-bind:class="[(overlayed == 'notif-bar')? 'active' : '', color]">
			<span class="notif-text">{{ message }}</span>
		</div>
		<div v-if="overlayed == 'fileman'" class="modal-fileman">
			<h3 class="modal-header montserrat">File Manager<a style="cursor:pointer" v-on:click="overlayed = ''" class="model-header-close-btn right"><i class="fa fa-times"></i></a></h3>
			<div class="modal-content">
				<iframe src="http://localhost/fileman/index.html?integration=custom" frameborder="0"></iframe>
			</div>
		</div>
	</div>
</template>

<script>

import { bus } from '../main';

export default {

    data () {
        return {
        	color : 'bg-trans',
        	overlayed : '',
        	message: '',
        	waitProc : false
        }
    },
    created () {
    	bus.$on('overlay',(data) => {

    		if (this.waitProc != false) {
    			clearTimeout(this.waitProc);
    		}

    		this.overlayed = data.overlayed;

    		if (this.overlayed == 'notif-bar') {

    			this.color = data.color;
    			this.message = data.message;

	    		this.waitProc = setTimeout(() => {
	    			this.overlayed = '';
	    			this.color = 'bg-trans';
	    			this.waitProc = false;
	    		}, 3500);
    		}
    		
    	})
    }
}

</script>

<style scoped>

	.overlay-fixed > div {
		position: fixed;
		transition: all 0.5s ease;
	}

	.modal-header {
		padding: 10px 15px;
		font-size: 14px;
        border-bottom: #F2F2F2 solid 1px;
        font-weight: 500;
        color: #3e4855;
        line-height: 20px;
	}

	.modal-fileman {
		width: 90%;
		height: 90%;
		top: 50%;
		left: 50%;
		transform: translate(-50%,-50%);
		background: #fff;
		box-shadow: 0 1px 1px rgba(0,0,0,.05);
		border-radius: 4px;
		border: #F2F2F2 solid 1px;
	}

	.modal-content {
		width: 100%;
		height: calc(100% - 41px);
		position: absolute;
		top: 41px;
		overflow: auto;
	}

	.modal-fileman iframe {
		width: 100%;
		height: 100%;
	}

	.notification-bar {
		width: 100%;
		top: 0;
		left: 0;
		padding: 14px 20px;
		text-align: center;
		transform: translateY(-100%);
	}

	.overlay-fixed > .notification-bar.active {
		transform: translateY(0%);
	}

	.notif-text {
		line-height: 20px;
		font-weight: 600;
		font-size: 12px;
	}

	.bg-success {
		color: #fff;
		background: #4CAF50;
	}

	.bg-wait {
		color: #fff;
		background: #D09420;
	}

	.bg-fail {
		color: #fff;
		background: red;
	}

	.bg-trans {
		color: #fff;
		background: transparent;
	}


</style>
