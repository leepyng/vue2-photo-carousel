<template>
	<div class="photo-view-box" v-if="pics&&pics.length>0">
        <img :src="pics[index].Url|replaceImgSrc(4)" alt=""  class="tdp-a" />
        <div class="tdp-b" v-if="pics.length>0">
        	<div class="tdpb-content"  >
        		<ul class="tdp-list" :style="'top:'+top+'px'" id="photoViewBox">
        			<li>
        				<img :src="p.Url|replaceImgSrc(4)"  v-for="(p,index) in pics" :id="'photoView'+index" @click="select(index)" />
        				
        			</li>
        		</ul>
        	</div>
            <div class="tdp-b-arrow">
                <i class="iconfont icon-xiala" @click="prev(false)"></i>
                <i class="iconfont icon-xiala" @click="next(false)"></i>
            </div>
        </div>
    </div>
	
</template>
<script>
	export default{
		name:'photo-box',
		props:{
			pics:{
				type:Array,
				default:()=>{
					return []
				}
			}
		},
		data(){
			return{
				index:0,
				top:0
			}
		},

		methods:{
			select(index){
				var isUp=index>this.index?false:true;
				this.index=index;
				// var top=document.getElementById('photoView'+this.index).offsetTop;
				if(isUp){
					this.prev(true)
				}else{
					this.next(true)
				}
			},
			prev(isSelect){
				if(!isSelect){this.index=this.index>0?this.index-1:this.index;}
				var top=document.getElementById('photoView'+this.index).offsetTop;
				
				var toTop=-this.top;
				var that=this;
				var scrollInterval = setInterval(function(){
					toTop--;
			        if ( top <=toTop ) {
			            that.top=-toTop; 
			        } 
			        else clearInterval(scrollInterval); 
			    },5);

			},
			next(isSelect){
				if(!isSelect){this.index=this.index<this.pics.length-1?this.index+1:this.index;}
				var top=document.getElementById('photoView'+this.index).offsetTop;
				var toTop=-this.top;
				var that=this;
				var scrollInterval = setInterval(function(){
					toTop++;
			        if ( top >=toTop ) {
			            that.top=-toTop; 
			        } 
			        else clearInterval(scrollInterval); 
			    },5);

			}
		},

	}
</script>