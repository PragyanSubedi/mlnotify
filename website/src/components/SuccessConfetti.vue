<template>
	<div class="success-confetti flex items-center justify-center"><VIcon /></div>
</template>
<script lang="ts">
import Vue from 'vue'

import party from 'party-js'
import VIcon from '../assets/icons/V.svg'

export default Vue.extend({
	name: 'SuccessConfetti',
	components: {
		VIcon,
	},
	data() {
		return {
			intervalToken: null as any,
		}
	},
	mounted() {
		party.confetti(this.$el as HTMLElement)
		this.intervalToken = setInterval(() => {
			party.confetti(this.$el as HTMLElement)
		}, 1500)
	},
	destroyed() {
		if (this.intervalToken) clearInterval(this.intervalToken)
	},
})
</script>
