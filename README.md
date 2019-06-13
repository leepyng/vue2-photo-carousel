# vue-photo-carousel
Photo display of a vue 2.0 component
<p align="center">


<img src="https://github.com/leepyng/vue-datepicker-infinite/blob/master/git/QQ20180508-153441.gif" alt="Coverage Status">


</p>

# install
	
	npm install vue-photo-carousel --save
	

# how to use
	template:
		 <PhotosBox :pics="photos" ></PhotosBox>
	
	script:
		//import
		import PhotosBox from 'vue-photo-carousel'//图片查看器
		
		//define
		components:{
			PhotosBox
		},
		//set default data
		data(){
			return{
				photos:['xx','xx']
			}
		}
		
	
# props description
	photos:photo address list

