<template>
	<b-container class="bv-example-row">
		<b-row class="justify-content-md-center">
			<b-col col lg="2"></b-col>

			<b-col cols="12" md="auto">
				<b-form @submit="onSubmit" @reset="onReset" v-if="show">
					<b-form-group
					id="input-group-1"
					label="Engrese el dominio:"
					label-for="input-1"
					>
					<b-form-input
					id="input-1"
					v-model="form.email"
					placeholder="Ingrese el dominio"
					></b-form-input>
				</b-form-group>

				<b-button type="submit" variant="primary">Submit</b-button>
				<b-button type="reset" variant="danger">Reset</b-button>
			</b-form>
			<b-card class="mt-3" header="Form Data Result">
				<pre class="m-0">{{ form }}</pre>
			</b-card>
		</b-col>
		<b-col col lg="2"></b-col>
	</b-row>
</b-container>
</template>

<script>
export default {
	data() {
		return {
			form: {
				domain: '',
			},
			show: true
		}
	},
	methods: {
		onSubmit(evt) {
			evt.preventDefault()
			alert(JSON.stringify(this.form))
		},
		onReset(evt) {
			evt.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.show = false
        this.$nextTick(() => {
        	this.show = true
        })
    }
}
}
</script>