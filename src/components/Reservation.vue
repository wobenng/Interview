<template>
    <div id="reservation">
        <div id="title">MEIJIA</div>
        <div id="appointmentNow">现在预约</div>
        <div id="dividingLine"></div>
        <div id="subtitle">免费获得客厅VR全景方案</div>
        <form @submit.prevent="checkInformation">
            <div id="SubmittedSuccessfully" v-show="Submit">提交成功</div>
            <select id="houses" name="houses" v-model="reservationInformation.houses">
                <option value="毛胚房">毛胚房</option>
                <option value="二手房">二手房</option>
            </select>
            <svg class="icon" aria-hidden="true" id="iconOne">
                <use xlink:href="#icon-xiangxiajiantou"></use>
            </svg>
            <select id="city" name="city" v-model="reservationInformation.city">
                <option value="杭州市">杭州市</option>
                <option value="温州市">温州市</option>
            </select>
            <svg class="icon" aria-hidden="true" id="iconTwo">
                <use xlink:href="#icon-xiangxiajiantou"></use>
            </svg>
            <input type="text" placeholder="所在小区" id="address" name="address" v-model="reservationInformation.address">
            <p v-show="caveat" id="caveat">请输入正确的详细地址</p>
            <input type="submit" value="立即提交">
        </form>
    </div>
</template>

<script>

export default {
  name: 'Reservation',
  data(){
    return{
        Submit: false,
        caveat: false,
        reservationInformation:{
            houses: '毛胚房',
            city: '杭州市',
            address: ''
        }
    }
  },
  methods:{
      checkInformation(){
          this.reservationInformation.address = this.reservationInformation.address.split(" ").join("");
          let chinese = this.reservationInformation.address.match(/[\u4e00-\u9fa5]/g) || [];
          if(chinese.length >= 5){
              this.caveat = false;
              this.reservationInformation = {
                  houses: '毛胚房',
                  city: '杭州市',
                  address: ''
              }
              console.log(this.reservationInformation)
              this.SubmittedSuccessfully();
              return true;
          }else{
              this.caveat = true;
              return false;
          }
      },
      SubmittedSuccessfully(){
          this.Submit = true;
          let time = setTimeout(()=>{
              console.log(this)
              this.Submit = false;
          },3000);
      }
  }
}
</script>

<style scoped lang="scss">
$designWidth : 752;
$deviceWidth : 100vw;
*{
    margin: 0px;
    padding: 0px;
    box-sizing: border-box;
}
#reservation{
    background-color: #f5f5f5;
    display: flex;
    flex-direction: column;
    align-items: center;
    #title{
        font-size: round((45/$designWidth)*100vw);
        color: #2b9f97;
        margin-top: round((72/$designWidth)*100vw);
    }
    #appointmentNow{
        font-size: round((50/$designWidth)*100vw);
        color: #333333;
        margin-top: round((56/$designWidth)*100vw);
        
    }
    #dividingLine{
        background-color: #159a91;
        width: round((56/$designWidth)*100vw);
        height: 2px;
        margin-bottom: round((24/$designWidth)*100vw);
        margin-top: round((24/$designWidth)*100vw);
    }
    #subtitle{
        margin-bottom: round((80/$designWidth)*100vw);
        font-size: round((27/$designWidth)*100vw);
        height: round((30/$designWidth)*100vw);
        color: #999999;
    }
    form{
        position: relative;
        width: 90%;
        display: flex;
        flex-direction: column;
        align-items: center;
        #iconOne{
            width: round((40/$designWidth)*100vw);
            height: round((30/$designWidth)*100vw);
            position: absolute;
            top: round((25/$designWidth)*100vw);
            right: round((20/$designWidth)*100vw);
            display: inline-block;
        }
        #iconTwo{
            width: round((40/$designWidth)*100vw);
            height: round((30/$designWidth)*100vw);
            position: absolute;
            top: round((145/$designWidth)*100vw);
            right: round((20/$designWidth)*100vw);
            display: inline-block;
        }
        #caveat{
            margin-top: round((10/$designWidth)*100vw);
            width: 100%;
            color: red;
            text-align: start;
        }
        #SubmittedSuccessfully{
            width: 50%;
            height: round((100/$designWidth)*100vw);
            position: absolute;
            top: round((110/$designWidth)*100vw);
            color: #39d5c2;
            line-height: round((50/$designWidth)*100vw);
            padding: round((25/$designWidth)*100vw) 0px;
            border: 1px solid #39d5c2;
        }
    }
    #houses{
        width: 100%;
        height: round((80/$designWidth)*100vw);
        padding: round((20/$designWidth)*100vw);
        color: #afafaf;
        border: none;
        outline: none;
        -moz-appearance:none;
        -webkit-appearance:none;
        background-color: #fff;
        option{
            width: 50px;
            height: 100%;
            -webkit-appearance:none;
        }
    }
    #city{
        width: 100%;
        height: round((80/$designWidth)*100vw);
        padding: round((20/$designWidth)*100vw);
        color: #afafaf;
        border: none;
        outline: none;
        margin-top: round((40/$designWidth)*100vw);
        -moz-appearance:none;
        -webkit-appearance:none;
        background-color: #fff;
    }
    input{
        width: 100%;
        height: round((80/$designWidth)*100vw);
        padding: round((20/$designWidth)*100vw);
        color: #afafaf;
        border: none;
        outline: none;
        margin-top: round((40/$designWidth)*100vw);
        -moz-appearance:none;
        -webkit-appearance:none;
    }
    input:last-child{
        color: white;
        background-color: #39d5c2;
        font-size: round((28/$designWidth)*100vw);
        margin-bottom: round((40/$designWidth)*100vw);
    }
}
</style>