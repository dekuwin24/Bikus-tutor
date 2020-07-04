<!-- =========================================================================================
    File Name: Search.vue
    Description: Search Page
    ----------------------------------------------------------------------------------------
    Item Name: Vuexy - Vuejs, HTML & Laravel Admin Dashboard Template
      Author: Pixinvent
    Author URL: http://www.themeforest.net/user/pixinvent
========================================================================================== -->


<template>
    <div id="search-page">

      <!-- <vs-divider class="pt-5 mt-5 pb-0 mb-0" icon="star"/> -->

      <div class="m-5 p-5">
        <vx-card v-for="cour in cours"  class=" rounded border-black border-4 pb-8" noShadow cardBorder>
          <div class="p-5 " v-for="item in cour.exo"  v-if="item.id == $route.params.id">

            <div slot="header"  v-for="it in item.text">
             <h2 class="text-center font-bold pt-2">
              Text : {{it.titre}}
            </h2>
           </div>
           <div class="pb-5" v-for="it in item.text">
             <div  v-for="inner in it.paragraphe" class="leading-loose">
               <h4 class="pt-2 pl-3 pr-3 mt-5 leading-loose"> {{inner.paragraphe1}}</h4>
               <h4 class="pt-2 pl-3 pr-3 leading-loose"> {{inner.paragraphe2}}</h4>
               <h4 class="pt-2 pl-3 pr-3 leading-loose"> {{inner.paragraphe3}}</h4>
             </div>
             <h4 class="float-right pt-3 leading-loose font-bold ">
               {{it.auteur}}
             </h4>

           </div>

           <!-- <div class=""  v-for="it in item.text"> -->


           <!-- </div> -->

          </div>
        </vx-card>

      </div>



     <div class="ml-5 pl-5  mr-5 pr-5">
       <div class=" ml-5 pl-5  mr-5 pr-5">
         <vs-divider class="pt-0 mt-0 pb-5 mb-5 " icon="star"/>

       </div>

     </div>


      <!-- BEGINNER QUESTIONS -->


      <div class="m-5">
        <vx-card class="pb-5 rounded-none "  noShadow>
          <div class=""  v-for="quiz in quizs" v-if="quiz.id == $route.params.id" >
            <h2 class="text-center pt-5 pb-5">{{ quiz.tests.titre }}</h2>

            <div class="" v-for="(test, index) in quiz.tests.questions" :key="test "class="w-full">
              <div v-show="index === questionIndex" class="pl-5 pr-5">
                <h3 class="pt-3"> {{test.text.type}}</h3>
                <h4 class="pt-3 mt-4"> {{test.text.texts}}</h4>
                <h5 class="pt-3">{{test.text.questions}}</h5>
                <ol class="pt-5 w-full" >
                  <li  class="w-full" >
                    <vx-card  v-for="(response, ind) in test.responses" :key="response"   class="centerx noShadow rounded-l-none border-4 border-black container">

                        <div class="" v-if="response.correct == true " >
                          <vs-radio v-on:change="seen =!seen"  v-model="userResponses[index]" :name="index" :vs-value="response.correct" > <p class="pl-5 text-xl toggle">{{response.text}}</p>
                          </vs-radio>
                          <p v-if="userResponses[index]==true" class="w-full"> <i  class=" em em-heart_eyes mt-5 text-lg text-bottom ml-5 mr-5" aria-role="presentation" aria-label="SLIGHTLY SMILING FACE"></i>
                            <span>
                              {{response.answer}} <vs-button size="small" class="bg-primary w-48 text-lg rounded-none pl-5 ml-5  mt-5 float-right" v-on:click="next">Next</vs-button>
                            </span>
                          </p>

                        </div>

                      <div class=""  v-if="userResponses[index] == false"  >
                        <div class="" v-if="response.correct == true " @change="next" >
                          <div class="invisible hidden p-0 m-0 h-0 w-0">
                            <vs-radio  class="p-0 m-0 h-0 w-0" v-model="userResponses[false]" :name="index" :vs-value="response.text"><p class="pl-5 text-xl">{{response.text}}</p></vs-radio>
                          </div>
                        </div>
                        <div class="" v-else @change="next">
                          <vs-radio  v-model="userResponses[false]" :name="index" :vs-value="response.text" ><p class="pl-5 text-xl">{{response.text}}</p></vs-radio>

                        </div>
                      </div>
                  </vx-card>
                  </li>
                </ol>

                <!-- button next and previous  -->
                <!-- <div class="w-full flex pl-5 pr-5 pt-5">
                  <div class="w-4/5 h-12">
                    <vs-button size="small" class="mt-5 mr-5 bg-primary text-lg w-48 rounded-none" v-if="questionIndex > 0" v-on:click="prev">
                      prev
                    </vs-button>
                  </div>

                  <div class="w-4/5 h-12">
                    <vs-button size="small" class="mt-5  ml-5 w-48  bg-grey text-lg float-right" v-on:click="next">
                      next
                    </vs-button>
                  </div>
                </div> -->
                <div class="mt-5 text-sm text-center">
                  <p class=""> <span class="text-danger"> WARNING!</span> You only have one chance to choose. Choose wisely before clicking ! <i class="em em-wink ml-2" aria-role="presentation" aria-label="WINKING FACE"></i> </p>
                </div>
              </div>

            </div>
            <div class="ml-5 pl-5 mr-5 pr-5 pt-5 pb-5" v-show="questionIndex === quiz.tests.questions.length">
              <div class=" text-white bg-primary border-white container border-8 border-double ">

                <div class=" text-center">
                  <!-- <div class="w-1/3"></div> -->
                  <!-- <div class="w-1/3"> -->
                    <p class="pt-5 text-3xl text-center">
                      Score - Gade - Answers
                    </p >
                  <!-- </div> -->
                  <!-- <div class="w-1/3"></div> -->
                </div>

                <div class=" flex">
                  <div class="w-1/2">
                    <p class="text-xl  pt-3 mt-5 pb-5 mb-5 pl-0 ml-0">
                      <span> Total score: </span> <br/> <span class="pl-3 ml-3"> {{ score() }} / {{ quiz.tests.questions.length }} </span>
                    </p>
                  </div>

                  <!-- score total = 20 -->
                  <div class="w-1/2 text-right pr-2 mr-2" v-if= "quiz.tests.questions.length  == 20">
                    <p class="text-xl pt-3 mt-5 pb-5 mb-5" v-if="score() < 9 ">
                      <span> Grade :</span> <br/>
                      <span> Never give up! You will do better next time <i class="em em-slightly_smiling_face ml-2" aria-role="presentation" aria-label="SLIGHTLY SMILING FACE"></i> </span>

                    </p>
                    <p class="text-xl pt-3 mt-5 pb-5 mb-5" v-else-if="score() == 10 ">
                      <span> Grade :</span> <br/>
                      <span> Pass </span>

                    </p>
                    <p class="text-xl pt-3 mt-5 pb-5 mb-5" v-else-if="score() > 10 && score() <= 11">
                      <span> Grade :</span> <br/>
                      <span>Good Enough  </span>

                    </p>
                    <p class="text-xl pt-3 mt-5 pb-5 mb-5" v-else-if="score() > 11 && score() <= 12">
                      <span> Grade :</span> <br/>
                      <span> Good </span>

                    </p>
                    <p class="text-xl pt-3 mt-5 pb-5 mb-5" v-else="score() > 12 && score() <= 20">
                      <span> Grade :</span> <br/>
                      <span>Very Good  </span>

                    </p>
                  </div>


                  <!-- score total >20 -->
                  <div class="w-1/2 text-right pr-2 mr-2" v-else>
                    <p class="text-xl pt-3 mt-5 pb-5 mb-5" v-if="score() < 13 ">
                      <span> Grade :</span> <br/>
                      <span> Never give up! You will do better next time <i class="em em-slightly_smiling_face ml-2" aria-role="presentation" aria-label="SLIGHTLY SMILING FACE"></i> </span>

                    </p>
                    <p class="text-xl pt-3 mt-5 pb-5 mb-5" v-else-if="score() == 13 ">
                      <span> Grade :</span> <br/>
                      <span> Pass </span>

                    </p>
                    <p class="text-xl pt-3 mt-5 pb-5 mb-5" v-else-if="score() > 13 && score() <= 18">
                      <span> Grade :</span> <br/>
                      <span>Good Enough  </span>

                    </p>
                    <p class="text-xl pt-3 mt-5 pb-5 mb-5" v-else-if="score() > 18 && score() <= 21">
                      <span> Grade :</span> <br/>
                      <span> Good </span>

                    </p>
                    <p class="text-xl pt-3 mt-5 pb-5 mb-5" v-else="score() > 21 && score() <= 27">
                      <span> Grade :</span> <br/>
                      <span>Very Good  </span>

                    </p>

                  </div>

                </div>


              </div>
              <vs-button  class="mt-3 w-full" @click="restart()"> restart</vs-button>

              <vs-divider class="pt-5 mt-4 m-0" color="gray"  icon="star"></vs-divider>
              <!-- <vs-divider class="pt-5 mt-4 m-0" color="gray"  icon="star"></vs-divider> -->


              <!-- <vs-divider class=" mt-5 pt-5 mb-5 pb-5"/> -->

              <div class="pt- mt-5" v-for="(quiz, n) in quizs" v-if="quiz.id == $route.params.id">
                <div class="" v-for="(test, index) in quiz.tests.questions" class="">
                  <h3 class="pt-1 pb-2 text-2xl text-center"> {{test.text.type}}</h3>
                  <span class=" mt-2 text-xl"> {{test.text.texts}}</span> <br/>
                  <span class="text-base text-lg pl-3">{{test.text.questions}}</span><br/>
                  <div class=" flex pt-5 pl-5 ml-5 mb-5 pb-5 text-success text-center text-lg font-bold">
                    <div class="text-left pr-5 ">
                      <img style="width:55px; height:85px" src="@/assets/images/pages/african-woman.png">
                      <!-- <i  class=" em em-heart_eyes text-lg text-bottom mt-3 mr-5" aria-role="presentation" aria-label="SLIGHTLY SMILING FACE"></i> Answer : -->

                    </div>
                    <div class="text-center pt-5 mt-5">
                      <span v-for="(response, ind) in test.responses" :key="response" v-if="response.correct == true " >
                        {{response.text}}
                      </span>
                    </div>

                  </div>
                  <!-- <span class="pt-5 pl-5 ml-5 mb-5 pb-5 text-success text-center text-lg font-bold">
                    <img style="width:50px; height:80px" src="@/assets/images/pages/african-woman.png">

                    <i  class=" em em-heart_eyes text-lg text-bottom mt-3 mr-5" aria-role="presentation" aria-label="SLIGHTLY SMILING FACE"></i> Answer :
                    <span v-for="(response, ind) in test.responses" :key="response" v-if="response.correct == true " >
                      {{response.text}}
                    </span>
                  </span> -->
                </div>

                <div class="" v-for="cour in cours">
                      <!-- <div slot="header"  v-for="it in item.text">   -->
                    <div class="" v-for="item in cour.exo"  v-if="item.id == $route.params.id">
                      <div class=""  v-for="it in item.text">
                        <div class=""v-for="it1 in it.writing">
                          <div class="" v-if="it1.question == true">
                            <p class="text-black text-2xl text-center mt-5 pt-5 pb-2">{{it1.type}}</p>
                            <p class="text-black text-xl text-center pb-5">{{it1.essay}}</p>
                            <p class="text-success font-bold text-lg text-center">{{it1.text}}</p>
                          </div>
                          <div class="" v-else>
                            <p class="text-2xl text-center mt-5 pt-5 font-bold text-black">IV - WRITING : write a short esssay</p>
                            <p class="text-success font-bold text-lg text-center">Please do this part on your own then give it to an english speaking adult for correction</p>
                          </div>

                        </div>




                      </div>

                    </div>
                  <!-- if writing essay is different from the usual -->

                </div>


              </div>
            </div>
          </div>
        </vx-card>

      </div>

    </div>

</template>

<script>
import { videoPlayer } from 'vue-video-player'
import 'video.js/dist/video-js.css'
import axios from 'axios'
import {FormWizard, TabContent} from 'vue-form-wizard'
import 'vue-form-wizard/dist/vue-form-wizard.min.css'

var lessons = {
  title: 'QUESTIONS',
  questions: [
    {
      text: "A- Read the text and write the letter that is in front of the correct answer ",
    type:[
        {type1:"I - COMPREHENSION", text:"A- Read the text and write the letter that is in front of the correct answer"},
        {type2:"II - VOCABULARY"},
        {type3:"II - GRAMMAR"},
        {type4:"IV - WRITING"}
      ],
      responses: [
        {text: 'Wrong, too bad.'},
        {text: 'Wrong, too bad.'},
        {text: 'Right!', correct: true},
      ]
    }, {
      text: "Question 2",
      responses: [
        {text: 'Wrong, too bad.'},
        {text: 'Right answer', correct: true},
        {text: 'Wrong answer'},
      ]
    },
    {
      text: "Question 2",
      responses: [
        {text: 'Right answer', correct: true},
        {text: 'Wrong answer'},
      ]
    }
  ]
};
export default{
    data() {
        return {
          quizs: [],
          cours: [],
          lessons: lessons,
          // Store current question index
          questionIndex: 0,
          // An array initialized with "false" values for each question
          // It means: "did the user answered correctly to the question n?" "no".
          // userResponses: Array(lessons.questions.length).fill(false)
          // userResponses: Array(10).fill(null),
          userResponses: Array(50).fill(false),
          seen:true



//
        }
    },
    mounted () {
      axios
        .get('http://localhost:3000/quizs',{params:{id: this.$route.params.id}})
        .then(res => (this.quizs = res.data)),
        axios
          .get('http://localhost:3000/lessons')
          .then(res => (this.cours = res.data))
    },
    methods: {
      // Go to next question
     next: function() {
       this.questionIndex++;
     },
     // Go to previous question
     prev: function() {
       this.questionIndex--;
     },
     // Return "true" count in userResponses
     score: function() {
       return this.userResponses.filter(function(val) { return val }).length;
     },
         //return this.userResponses.filter(function(val) { return val }).length;
    restart: function(){
			this.questionIndex=0;
	 		this.userResponses=Array(50).fill(false);
		 },

    formSubmitted() {
        alert("Form submitted!");
      }

    },
    components: {
        videoPlayer,
        FormWizard,
        TabContent
    }
}
</script>

<style lang="scss">
@import "@/assets/scss/vuexy/pages/search.scss";

$trans_duration: 0.3s;
$primary_color: #3D5AFE;

@import url("https://fonts.googleapis.com/css?family=Montserrat:400,400i,700");
@import url("https://fonts.googleapis.com/css?family=Open+Sans:400,400i,700");
//
// .form-radio
// {
//      // -webkit-appearance: none !important;
//      // -moz-appearance: none !important;
//      // appearance: none!important;
//      display: inline-block;
//      position: relative;
//      background-color: #f1f1f1;
//      color: #666;
//      top: 10px;
//      height: 25px;
//      width: 25px;
//      border: 0;
//      border-radius: 50px;
//      cursor: pointer;
//      margin-right: 7px;
//      outline: none;
// }
//
// .form-radio:checked::before
// {
//      position: absolute;
//      font: 13px/1 'Open Sans', sans-serif;
//      left: 11px;
//      top: 7px;
//      content: '\02143';
//      background-color:"red";
//      transform: rotate(40deg);
// }
//
// .form-radio:hover
// {
//      background-color: purple;
// }
//
// .form-radio:checked
// {
//      background-color: #f1f1f1;
// }


//     .button {
//        transition: $trans_duration;
//     }
// .title,
// .subtitle {
//    font-family: Montserrat, sans-serif;
//    font-weight: normal;
// }
// .animated {
//    transition-duration: $trans_duration/2;
// }
//
// .container{
// 	margin: 0 0.5rem;
// }
//
// .questionBox {
//
// 	max-width: 30rem;
// 	width: 30rem;
// 	min-height: 30rem;
//
// 	 background: #FAFAFA;
//    position: relative;
//    display: flex;
//
// 	border-radius: 0.5rem;
// 	overflow: hidden;
// box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
//
// 	header{
// 		background:rgba(0,0,0,0.025);
// 		padding: 1.5rem;
// 		text-align: center;
// 		border-bottom: 1px solid rgba(0,0,0,0.1);
//
// 		h1{
// 			font-weight: bold;
// 			margin-bottom: 1rem !important;
// 		}
// 		 .progressContainer {
//        width: 60%;
// 			 margin: 0 auto;
// 			 >progress{
// 				 margin:0;
// 				 border-radius: 5rem;
// 				 overflow: hidden;
// 				 border:none;
//
// 				 color:$primary_color;
// 				&::-moz-progress-bar { background: $primary_color; }
// 				&::-webkit-progress-value { background: $primary_color; }
// 			 }
// 			 >p{
// 				 margin:0;
// 				 margin-top: 0.5rem;
// 			 }
//          }
// 	}
//    .titleContainer {
// 		 text-align: center;
// 		 margin: 0 auto;
// 		 padding: 1.5rem;
//
//       }
//
//    .quizForm {
//       display: block;
//       white-space: normal;
//
//       height: 100%;
//       width: 100%;
//
//       .quizFormContainer {
//          height: 100%;
//          margin: 15px 18px;
//
//          .field-label {
//             text-align: left;
//             margin-bottom: 0.5rem;
//          }
//       }
//    }
//    .quizCompleted {
//       width: 100%;
//       padding: 1rem;
// 		 text-align:center;
//
// 		 > .icon{
// 			 color: #FF5252;
// 			 font-size: 5rem;
//
// 			 .is-active{
// 				 color: #00E676;
// 			 }
// 		 }
//    }
//    .questionContainer {
//       white-space: normal;
//
//       height: 100%;
//       width: 100%;
//
//       .optionContainer {
//          margin-top: 12px;
//          flex-grow: 1;
//          .option {
//             border-radius: 290486px;
//             padding: 9px 18px;
//             margin: 0 18px;
//             margin-bottom: 12px;
//             transition: $trans_duration;
//             cursor: pointer;
//             background-color: rgba(0, 0, 0, 0.05);
// 					 color: rgba(0,0,0,0.85);
//             border: transparent 1px solid;
//
//             &.is-selected {
//                border-color: rgba(black,0.25);
//                background-color: white;
//             }
//             &:hover {
//                background-color: rgba(0, 0, 0, 0.1);
//             }
//             &:active {
//                transform: scaleX(0.9);
//             }
//          }
//       }
//
//       .questionFooter {
// 				background:rgba(0,0,0,0.025);
// 				border-top: 1px solid rgba(0,0,0,0.1);
//          width: 100%;
//          align-self: flex-end;
//
//          .pagination {
//             //padding: 10px 15px;
//             margin: 15px 25px;
//          }
//       }
//    }
// }
// .pagination{
// 	display: flex;
// 	justify-content: space-between;
// }
// .button{
// 	padding: 0.5rem 1rem;
// 	border: 1px solid rgba(0,0,0,0.25);
// 	border-radius: 5rem;
// 	margin: 0 0.25rem;
//
// 	transition:0.3s;
//
// 	&:hover{
// 		cursor: pointer;
// 		background: #ECEFF1;
// 		border-color:rgba(0,0,0,0.25);
// 	}
// 	&.is-active{
// 		background: $primary_color;
// 		color: white;
// 		border-color: transparent;
//
// 		&:hover{
// 			background: darken($primary_color,10%);
//
// 		}
// 	}
// }
//
// @media screen and (min-width: 769px) {
//    .questionBox {
//       align-items: center;
//       justify-content: center;
//
//       .questionContainer {
//          display: flex;
//          flex-direction: column;
//       }
//    }
// }
//
// @media screen and (max-width: 768px) {
//    .sidebar {
//       height: auto !important;
//       border-radius: 6px 6px 0px 0px;
//    }
// }

</style>
