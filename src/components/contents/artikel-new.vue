<template>
	<div class="raleway">
		<div class="page-title">
			<h2 class="montserrat">Artikel Baru</h2>
			<p>The most complete user interface framework that can be used to create stunning admin dashboards and presentation websites.</p>
		</div>
		<div class="panel">
			<h3 class="title-hero montserrat">Form</h3>
			<form v-on:submit.prevent="validateBeforeSubmit" ref="newArtForm" autocomplete="off">
				<div class="row">
					<div class="col-md-6">
						<div class="form-group row">
							<div class="col-sm-3">
								<label class="control-label">Judul</label>
							</div>
							<div class="col-sm-6">
								<input v-validate="'required'" name="judul" v-model="formData.judul" type="text" class="form-control" v-bind:class="{ 'field-error' : errors.has('judul') }">
								<span v-show="errors.has('judul')" class="field-error">{{ errors.first('judul') }}</span>
							</div>
						</div>
						<div class="form-group row">
							<div class="col-sm-3">
								<label class="control-label">Deskripsi</label>
							</div>
							<div class="col-sm-6">
								<textarea v-validate="'required'" name="deskripsi" v-model="formData.deskripsi" class="form-control" v-bind:class="{ 'field-error' : errors.has('deskripsi') }"></textarea>
								<span v-show="errors.has('deskripsi')" class="field-error">{{ errors.first('deskripsi') }}</span>
							</div>
						</div>
						<div class="form-group row">
							<div class="col-sm-3">
								<label class="control-label">Author</label>
							</div>
							<div class="col-sm-6">
								<select v-model="formData.author" name="author" class="form-control">
									<option value="Himatekkom" selected="true">Himatekkom</option>
									<option value="Infokom">Infokom</option>
								</select>
							</div>
						</div>
					</div>
					<div class="col-md-6">
						<div class="form-group row">
							<div class="col-sm-3">
								<label class="control-label">Featured</label>
							</div>
							<div class="col-sm-6">
								<select v-model="formData.featured" name="featured" class="form-control">
									<option value="0" selected="true">Tidak</option>
									<option value="1">Ya</option>
								</select>
							</div>
						</div>
						<div class="form-group row">
							<div class="col-sm-3">
								<label class="control-label">Cover</label>
							</div>
							<div class="col-sm-6">
								<input type="file" v-validate="{required: true, size: 1024, mimes: 'image/*'}" name="cover" v-on:change="previewThumbnail" class="form-control" style="display:none" ref="coverInput">
								<div class="image-preview form-control" v-bind:class="{ 'field-error' : errors.has('cover') }">
									<span v-show="formData.imageSrc == '' || errors.has('cover')">Tidak ada gambar dipilih</span>
									<img v-show="formData.imageSrc != '' && !errors.has('cover')" v-bind:src="formData.imageSrc" />
									<!-- <img src="http://localhost/fileman/Uploads/Documents/1.jpg?_=1512149889133" id="customRoxyImage"> -->
								</div>
								<a class="btn" v-on:click="openfileman">Pilih File</a>
								<span class="btn-note">File size max. 1 MB</span>
								<span v-show="errors.has('cover')" class="field-error">{{ errors.first('cover') }}</span>
							</div>
						</div>
					</div>
				</div>
				<div class="panel-separator"></div>
				<div class="form-group">
					<label class="control-label mrg15 left-align">Content</label>
					<ckeditor v-model="formData.content" name="content" v-validate="'required'"></ckeditor>
					<span v-show="errors.has('content')" class="field-error">{{ errors.first('content') }}</span>
				</div>
				<div class="content-box center-align">
					<button type="submit" class="btn btn-lg" v-show="!submitted">publish</button>
					<img v-show="submitted" src="/public/assets/puff.svg" height="46px">
				</div>
			</form>
		</div>
	</div>
</template>

<script>

import Ckeditor from 'vue-ckeditor2';
import { bus } from '../../main';

export default {

	components: { Ckeditor },
    data () {
        return {
        	formData : {
        		judul: '',
	        	deskripsi: '',
	        	author: 'Himatekkom',
	        	featured: 0,
	        	content: '',
	        	imageSrc: ''
        	},
        	submitted: false
        }
    },
    methods: {
	    previewThumbnail: function(event) {
	      	var input = event.target;

	      	if (input.files && input.files[0]) {
		        var reader = new FileReader();

		        var vm = this;

		        reader.onload = function(e) {
		          vm.formData.imageSrc = e.target.result;
		        }

		        reader.readAsDataURL(input.files[0]);
	      	}
	  	},
	  	validateBeforeSubmit() {
	      	this.$validator.validateAll().then((result) => {
		        if (result) {

		        	this.submitted = true;

		        	bus.$emit('overlay',{
		          		color : 'bg-wait',
		          		overlayed: 'notif-bar',
		          		message: 'Sedang diproses...'
		          	})

		          	this.$http.post('http://localhost/uploader/index.php',this.formData, {
		          		emulateJSON: true,
		          		headers: {
							'Content-Type': 'application/x-www-form-urlencoded'
						}
		          	}).then(response => {

		          		setTimeout(() => {
		          			bus.$emit('overlay',{
				          		color : 'bg-success',
				          		overlayed: 'notif-bar',
				          		message: 'Artikel telah berhasil dipublish.'
				          	})

				          	this.submitted = false;
		          		}, 1500);
		          		
		          	}, response => {

		          		setTimeout(() => {
		          			bus.$emit('overlay',{
				          		color : 'bg-fail',
				          		overlayed: 'notif-bar',
				          		message: 'Terjadi kesalahan, coba lagi.'
				          	})

				          	this.submitted = false;
		          		}, 1500);
		          	})

		          	return;
		        }

		    });
	    },
	    openfileman () {
	    	bus.$emit('overlay', {
	      		overlayed: 'fileman'
	    	})
	    },
	    closefileman() {
	    	bus.$emit('overlay', {
	      		overlayed: ''
	    	})
	    }
    },
    watch: {
    	
    }
}

</script>

<style>


</style>
