# vue2-photo-carousel
Photo display of a vue 2.0 component
<p align="center">


<img src="https://github.com/leepyng/vue-photo-carousel/blob/master/git/imt.gif" alt="Coverage Status">


</p>

# install
	
	npm install vue2-photo-carousel --save-dev
	

# how to use
	template:
		 <PhotosBox :pics="photos" ></PhotosBox>
	
	script:
		//import
		import PhotosBox from 'vue2-photo-carousel'
		
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

