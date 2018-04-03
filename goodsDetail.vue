<template>
	<div class="detail">
      <detail-header></detail-header>
      <img :src="msg.img">
      <p>{{msg.title}}</p>
      <p>{{msg.price}}</p>
      <p class="site-title">树懒果园 泰国进口大金煌芒果</p>
      <p class="site-cont">5斤装，约2-4个果，大！！！甜！！！</p>
      <common-footer></common-footer>
 	</div>
</template>

<script>
	import DetailHeader from '../components/DetailHeader'
	import CommonFooter from '../components/commonFooter'
	
	export default {
	  data () {
	    return {
			msg: ''
	    }
	  },
	  components: {
	    DetailHeader,
	    CommonFooter
	  },
	  mounted: function () {
	  	this.getDetail();
	  },
	  methods: {
	  	getDetail () {
	  		let routerParams = this.$route.params
	  		console.log(this.$route.params);
	  		this.msg = routerParams
	  	}
	  },
	  watch: {
	  	'$route': 'getParams'
	  }
	}
</script>

<style scoped>
	.detail {
	    padding: 0.25rem;
	    font-size: 12px;
  	}
  	.detail > img {
	    display: block;
	    width: 80%;
	    margin:  0 auto 0.5rem;
  	}
  	.detail > p {
	    font-size: 1.1rem;
	    line-height: 1.5rem;
	    text-align: left;
	    padding-bottom: 0.5rem;
  	}
  	.detail > p.site-title {
	    color: #ff8000;
  	}
  	.detail > p.site-cont {
	    color: #666;
	    font-size: 0.9rem;
  	}
</style>