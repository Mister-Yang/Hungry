<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
  </div>
</template>

<script>
import { getSeller } from 'api'
import VHeader from 'components/v-header/v-header.vue'

export default {
	name: 'app',
	data() {
		return {
			seller: {}
		}
	},
	created() {
		this._getSeller()
	},
	methods: {
		_getSeller() {
			getSeller().then((seller) => {
				this.seller = seller
			})
		}
	},
	components: {
		VHeader
	}
}
</script>
<style lang="stylus" scoped>
  #app
    .tab-wrapper
      position: fixed
      top: 136px
      left: 0
      right: 0
      bottom: 0
</style>
