<!-- =========================================================================================
    File Name: KnowledgeBase.vue
    Description: Knowledge Base Page
    ----------------------------------------------------------------------------------------
    Item Name: Vuexy - Vuejs, HTML & Laravel Admin Dashboard Template
      Author: Pixinvent
    Author URL: http://www.themeforest.net/user/pixinvent
========================================================================================== -->


<template>
    <div id="knowledge-base-page ml-5 mr-5">


        <!-- KNOWLEDGE BASE CARDS  -->
        <div class="flex flex-row w-full">
          <div class="px-4 py-2 m-2 w-full">
            <router-link :to="{ name: 'page-faq', params: {} }">
              <vs-card class="text-center cursor-pointer">
                <div slot="header">
                  <h3>
                    ENGLISH <i class="em em-slightly_smiling_face ml-5" aria-role="presentation" aria-label="SLIGHTLY SMILING FACE"></i>
                  </h3>
                </div>

                <div slot="media">
                  <img src="@/assets/images/pages/card-image-1.jpg">
                </div>
                Clickez
              </vs-card>

            </router-link>

          </div>
          <div class="px-4 py-2 m-2 w-full">
            <router-link :to="{ name: 'page-faq-math', params: {} }">
              <vs-card class="text-center cursor-pointer">
                <div slot="header">
                  <h3>
                    MATH <i class="em em-thinking_face ml-5" aria-role="presentation" aria-label="THINKING FACE"></i>
                  </h3>
                </div>
                <div slot="media">
                  <img src="@/assets/images/pages/card-image-3.jpg">
                </div>
                Clickez
              </vs-card>
          </router-link>
          </div>
          <div class="px-4 py-2 m-2 w-full">
            <router-link :to="{ name: 'page-faq-francais', params: {} }">

            <vs-card class="text-center cursor-pointer">
              <div slot="header">
                <h3>
                  FRANÇAIS <i class="em em-fr ml-5" aria-role="presentation" aria-label="France Flag"></i>
                </h3>
              </div>
              <div slot="media">
                <img src="@/assets/images/pages/card-image-2.jpg">
              </div>
              Clickez

            </vs-card>
          </router-link>

          </div>


        </div>
    </div>
</template>

<script>

export default{
    data() {
        return {
            knowledgeBaseSearchQuery: '',
            kb: [
                {
                  id          : 1,
                  title       : 'Sales Automation',
                  description : 'Muffin lemon drops chocolate carrot cake chocolate bar sweet roll.',
                  graphic     : require("@/assets/images/pages/graphic-1.png"),
                  url         : '/pages/knowledge-base/category'
                },
                {
                  id          : 2,
                  title       : 'Marketing Automation',
                  description : 'Gingerbread sesame snaps wafer soufflé. Macaroon brownie ice cream',
                  graphic     : require("@/assets/images/pages/graphic-2.png"),
                  url         : '/pages/knowledge-base/category'
                },
                {
                  id          : 3,
                  title       : 'Marketing BI',
                  description : 'cotton candy caramels danish chocolate cake pie candy. Lemon drops tart.',
                  graphic     : require("@/assets/images/pages/graphic-3.png"),
                  url         : '/pages/knowledge-base/category'
                },
                {
                  id          : 4,
                  title       : 'Personalization',
                  description : 'Pudding oat cake carrot cake lemon drops gummies marshmallow.',
                  graphic     : require("@/assets/images/pages/graphic-4.png"),
                  url         : '/pages/knowledge-base/category'
                },
                {
                  id          : 5,
                  title       : 'Email Marketing',
                  description : 'Gummi bears pudding icing sweet caramels chocolate',
                  graphic     : require("@/assets/images/pages/graphic-5.png"),
                  url         : '/pages/knowledge-base/category'
                },
                {
                  id          : 6,
                  title       : 'Demand Generation',
                  description : 'Dragée jelly beans candy canes pudding cake wafer. Muffin croissant.',
                  graphic     : require("@/assets/images/pages/graphic-6.png"),
                  url         : '/pages/knowledge-base/category'
                },
            ]
        }
    },
    computed: {
        filteredKB() {
            return this.kb.filter((item) => item.title.toLowerCase().includes(this.knowledgeBaseSearchQuery.toLowerCase()) || item.description.toLowerCase().includes(this.knowledgeBaseSearchQuery.toLowerCase()));
        }
    },
    methods: {},
    components: {}
}
</script>

<style lang="scss">
.knowledge-base-jumbotron-content {
    background-image: url('../../assets/images/pages/knowledge-base-cover.jpg');
    background-size: cover;
}
</style>
