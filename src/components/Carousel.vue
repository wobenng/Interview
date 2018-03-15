<template>
    <div id="carousel">
        <div id="outer" v-bind:class="nowPicture">
            <div v-for="img in imgSrc" v-bind:key="img.id"><img  :src="img.src" alt="banner1"></div>
        </div> 
        <ul class="clearfix">
            <li v-bind:class="[isActive? 'active':'silence']"></li>
            <li v-bind:class="[isActive? 'silence':'active']"></li>
        </ul> 
    </div>
</template>

<script>
import banner1URL from './../assets/banner1@3.png'
import banner2URL from './../assets/banner2@3.png'

export default {
  name: 'Carousel',
  data(){
    return{
      imgSrc:[
          {src: banner1URL,id:1},
          {src: banner2URL,id:2}
      ],
      isActive: true,
      switchIndex: 1,
      nowPicture: 'first',
      isSwitch: ['first','second']
    }
  },
  created: function(){
    setInterval(()=>{
        this.nowPicture = this.isSwitch[this.switchIndex];
        this.switchIndex = this.switchIndex + 1;
        if(this.switchIndex === 2){
            this.switchIndex = 0;
        }
        this.isActive = !this.isActive;
    },3000)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
*{
    margin: 0px;
    padding: 0px;
    box-sizing: border-box;
}
.clearfix::after{
    content: '';
    display: block;
    clear: both;
}
#carousel{
    width: 100vw;
    height: 70vw;
    position: relative;
    overflow: hidden;
    #outer{
        display: flex;
        flex-direction: row;
        img{
            width: 100vw;
            height: 70vw;
        }
        transition: all 0.5s linear;
    }
    #outer.first{
        transform: translateX(0px) translateZ(0);
    }
    #outer.second{
        transform: translateX(-100%) translateZ(0);
    }
    ul{
        position: absolute;
        left: 30px;
        bottom: 20px;
        li{
            width: 8px;
            height: 8px;
            border-radius: 50%;
            border: 1px solid gray;
            background-color: white;
            margin: 0px 10px;
            float: left;
            list-style: none;
        }
        li.active{
            background-color: gray;
        }
        li.silence{
            background-color: transparent;
        }
    }
}
</style>