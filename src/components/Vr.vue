<template>
    <div id="Vr">
        <div id="vrOuter">
            <div><img :src="imgSrc" alt="vr"></div>
            <div id="description">
                <div>
                    <p class="number"><span>01</span></p>
                    <div id="h">
                    <p class="firstLine">VR全屋装</p>
                    <p class="firstLine">所见即所得</p>
                    </div>
                </div>
                <p class="lastLine one">区别于传统装修公司，我们提供整套的</p>
                <p class="lastLine">VR全景方案100%还原未来新家</p>
                <button id="aboutMore"><span>了解更多</span>
                    <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" preserveAspectRatio="xMidYMid" width="20.438" height="16.47" viewBox="0 0 20.438 16.47">
                    <defs>
                      <filter id="color-overlay-1" filterUnits="userSpaceOnUse">
                        <feFlood flood-color="#333"/>
                        <feComposite operator="in" in2="SourceGraphic"/>
                        <feBlend in2="SourceGraphic" result="solidFill"/>
                      </filter>
                    </defs>
                    <g class="cls-1">
                      <rect y="7.31" width="20" height="2" rx="0.9" ry="0.9" class="cls-2"/>
                      <path d="M20.156,7.615 L12.792,0.251 C12.441,-0.101 11.871,-0.101 11.520,0.251 C11.168,0.602 11.168,1.172 11.520,1.524 L18.883,8.888 C19.235,9.239 19.805,9.239 20.156,8.888 C20.508,8.536 20.508,7.966 20.156,7.615 Z" class="cls-3"/>
                      <path d="M12.792,16.187 L20.156,8.823 C20.508,8.472 20.508,7.902 20.156,7.551 C19.805,7.199 19.235,7.199 18.883,7.551 L11.520,14.915 C11.168,15.266 11.168,15.836 11.520,16.187 C11.871,16.540 12.441,16.540 12.792,16.187 Z" class="cls-3"/>
                    </g>
                    </svg>
                </button>
                <a href="#">
                    <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" preserveAspectRatio="xMidYMid" width="14" height="16" viewBox="0 0 14 16">>
                    <g>
                      <path d="M5.654,-0.000 L7.347,-0.000 L7.347,15.000 L5.654,15.000 L5.654,-0.000 Z" transform="translate(0.5 0.5)" class="cls-1" fill="#f3f4f9"/>
                      <path d="M1.218,7.429 L6.961,13.305 L5.741,14.554 L-0.002,8.677 L1.218,7.429 Z" transform="translate(0.5 0.5)" class="cls-1" fill="#f3f4f9"/>
                      <path d="M6.037,13.305 L11.781,7.429 L13.002,8.677 L7.258,14.554 L6.037,13.305 Z" transform="translate(0.5 0.5)" class="cls-1" fill="#f3f4f9"/>
                    </g>
                    </svg>
                    <span id="circleOne"></span>
                    <span id="circleTwo"></span>
                    <span id="circleThree"></span>
                </a>
            </div>
            <div id="downloadDescription">
                    <p>360旋转</p>
                    <p>VR全套方案</p>
                    <p>所见即所得</p>
                </div>
        </div>
    </div>
</template>

<script>
import Vr from '../assets/vr@3.png';

export default {
  name: 'Vr',
  data(){
    return{
      imgSrc: Vr,
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$designWidth : 752;
$deviceWidth : 100vw;

*{
    margin: 0px;
    padding: 0px;
    box-sizing: border-box;
}
.cls-1 {
  fill: #f3f4f9;
  fill-rule: evenodd;
}
.cls-2, .cls-3 {
  fill: #010000;
}
.cls-3 {
  fill-rule: evenodd;
}
.clearfix::after{
    content: '';
    display: block;
    clear: both;
}
#Vr{
    #vrOuter{
        position: relative;
        img{
            width: 100vw;
        }
        #description{
            width: 100%;
            position: absolute;
            left: round((104/$designWidth)*100vw);
            top: round((164/$designWidth)*100vw);
            text-align: start;
            div:first-child{
                position: relative;
            }
            div:first-child #h{
                position: relative;
                z-index: 2;
            }
            p.firstLine{
                font-size: round((48/$designWidth)*100vw);
                line-height: round((48/$designWidth)*100vw);
                height: round((48/$designWidth)*100vw);
                margin-bottom: round((30/$designWidth)*100vw);
                color: #333333;
            }
            p.number span{
                font-size: round((240/$designWidth)*100vw);
                color: #edf2f2; 
            }
            p.number{
                position: absolute;
                bottom: 0px;
                left: round((122/$designWidth)*100vw);
                height: round((220/$designWidth)*100vw);
                z-index: 1;
            }
            p.lastLine{
                font-size: round((27/$designWidth)*100vw);
                line-height: round((30/$designWidth)*100vw);
                height: round((30/$designWidth)*100vw);
                color: #999999;
            }
            p.lastLine.one{
                margin-top: round((78/$designWidth)*100vw);
                margin-bottom: round((12/$designWidth)*100vw);
            }
            button{
                padding-left: round((36/$designWidth)*100vw);
                padding-right: round((36/$designWidth)*100vw);
                padding-top: round((15/$designWidth)*100vw);
                padding-bottom: round((15/$designWidth)*100vw);
                border-radius: round((64/$designWidth)*100vw);
                border: 1px solid #666666;
                background-color: transparent;
                margin-top: round((88/$designWidth)*100vw);
                outline: none;
                span{
                display: inline-block;
                font-size: round((24/$designWidth)*100vw);
                text-align: start;
                vertical-align: center;
                }
                svg{
                    height: round((16/$designWidth)*100vw);
                    width: round((16/$designWidth)*100vw);
                }
            }
            a{
                width: round((50/$designWidth)*100vw);
                height: round((50/$designWidth)*100vw);
                border-radius: 50%;
                background-color: #39d5c2;
                display: block;
                display: flex;
                justify-content: center;
                align-items: center;
                position: relative;
                left: 50%;
                top: round((80/$designWidth)*100vw);
                svg{
                    width: round((25/$designWidth)*100vw);
                    height: round((25/$designWidth)*100vw);
                }
                span{
                    display: block;
                    position: absolute;
                    left: 0px;
                    top: 0px;
                    border-radius: 50%;
                    border: 1px solid #49e0ca;
                    width: 250%;
                    height: 250%;
                    margin-left: -75%;
                    margin-top: -75%;
                }
                span#circleOne{
                    animation: circle-opacity 4s infinite;  
                }
                span#circleTwo{
                    animation: circle-opacity 4s infinite;
                    animation-delay:1s;
                }
                span#circleThree{
                    animation: circle-opacity 4s infinite; 
                    animation-delay:2s;
                }
                @keyframes circle-opacity{  
                    from {  
                        opacity: 1;  
                        transform: scale(0);  
                    }  
                    to {  
                        opacity: 0;  
                        transform: scale(2);  
                    }  
                }
            }
        }
        #downloadDescription{
            position: absolute;
            bottom: 27%;
            right: 0%;
            margin-right: round((20/$designWidth)*100vw);
            p{
                text-align: start;
                font-size: round((27/$designWidth)*100vw);
                line-height: round((34/$designWidth)*100vw);
                height: round((34/$designWidth)*100vw);
                color: #999999;
            }
        }
    }
}

</style>