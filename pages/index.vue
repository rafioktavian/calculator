<template>
	<section class="content">
		<h1 class="title">
			calculator
		</h1>
		<article class="form-group">
			<section class="row mb-4">
				<article class="col-10">
					<input type="number" name="number1" v-model="model.number1" class="form-control" v-if="model.checkbox1 == 1">
					<input type="number" name="number1" v-model="model.number1" class="form-control" readonly v-else>
				</article>
				<article class="col-2">
					<input type="checkbox" name="checkbox1" v-model="model.checkbox1" class="form-control">
				</article>
			</section>
			<section class="row mb-4">
				<article class="col-10">
					<input type="number" name="number2" v-model="model.number2" class="form-control" v-if="model.checkbox2 == 1">
					<input type="number" name="number2" v-model="model.number2" class="form-control" readonly v-else>
				</article>
				<article class="col-2">
					<input type="checkbox" name="checkbox2" v-model="model.checkbox2" class="form-control">
				</article>
			</section>
			<section class="row mb-4">
				<article class="col-10">
					<input type="number" name="number3" v-model="model.number3" class="form-control" v-if="model.checkbox3 == 1">
					<input type="number" name="number3" v-model="model.number3" class="form-control" readonly v-else>
				</article>
				<article class="col-2">
					<input type="checkbox" name="checkbox3" v-model="model.checkbox3" class="form-control">
				</article>
			</section>
			<section class="content-center mb-4">
				<button class="btn btn-secondary btn-calculate mr-5" @click="tambah"> + </button>
				<button class="btn btn-secondary btn-calculate mr-5" @click="kurang"> - </button>
				<button class="btn btn-secondary btn-calculate mr-5" @click="kali"> x </button>
				<button class="btn btn-secondary btn-calculate mr-5" @click="bagi"> / </button>
			</section>
		</article>
		<hr class="line-1">
		<h3>Hasil : {{model.result}}</h3>
	</section>
</template>

<script>
	export default {
		data() {
			return {
				model:{
					checkbox1: 0,
					checkbox2: 0,
					checkbox3: 0,
					number1: "",
					number2: "",
					number3: "",
					result: ""
				},
			}
		},
		methods: {
			tambah() {
				let _ = this
				if (_.model.number1=="") {
					_.model.result = parseInt(_.model.number2) + parseInt(_.model.number3)
				} else if(_.model.number2==""){
					_.model.result = parseInt(_.model.number1) + parseInt(_.model.number3)
				} else if(_.model.number3==""){
					_.model.result = parseInt(_.model.number1) + parseInt(_.model.number2)
				} else {
					_.model.result = parseInt(_.model.number1) + parseInt(_.model.number2) + parseInt(_.model.number3)
				}
			},
			kurang() {
				let _ = this
				if (_.model.number1=="") {
					_.model.result = parseInt(_.model.number2) - parseInt(_.model.number3)
				} else if(_.model.number2==""){
					_.model.result = parseInt(_.model.number1) - parseInt(_.model.number3)
				} else if(_.model.number3==""){
					_.model.result = parseInt(_.model.number1) - parseInt(_.model.number2)
				} else {
					_.model.result = parseInt(_.model.number1) - parseInt(_.model.number2) + parseInt(_.model.number3)
				}
			},
			kali() {
				let _ = this
				if (_.model.number1=="") {
					_.model.result = parseInt(_.model.number2) * parseInt(_.model.number3)
				} else if(_.model.number2==""){
					_.model.result = parseInt(_.model.number1) * parseInt(_.model.number3)
				} else if(_.model.number3==""){
					_.model.result = parseInt(_.model.number1) * parseInt(_.model.number2)
				} else {
					_.model.result = parseInt(_.model.number1) * parseInt(_.model.number2) + parseInt(_.model.number3)
				}
			},
			bagi() {
				let _ = this
				if (_.model.number1=="") {
					_.model.result = parseInt(_.model.number2) / parseInt(_.model.number3)
				} else if(_.model.number2==""){
					_.model.result = parseInt(_.model.number1) / parseInt(_.model.number3)
				} else if(_.model.number3==""){
					_.model.result = parseInt(_.model.number1) / parseInt(_.model.number2)
				} else {
					_.model.result = parseInt(_.model.number1) / parseInt(_.model.number2) + parseInt(_.model.number3)
				}
			},
		},
	}
</script>