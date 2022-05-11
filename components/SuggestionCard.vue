<template>
<div>
    <v-row class="mt-10">
        <v-col v-for="suggestion in suggestions" :key="suggestion._id" height="300" cols="12" md="6" lg="4">
            <v-card outlined>
                <div class="d-flex justify-center">
                    <div>
                        <v-img 
                            class="white--text align-end" 
                            width="250" 
                            height="250" 
                            :src="suggestion.image">
                       
                        </v-img>
                         <v-card-title
                          class="d-flex justify-center"
          
                         >{{ suggestion.title }}</v-card-title>
                        <div class="mt-2 d-flex justify-center">
                        
                          <!-- <div
                              width="40"
                                height="40"
                                alt=""
                              
                            
                          >
                           {{ suggestion.profile}}
                          </div> -->
                          <v-img
                            width="40"
                                height="40"
                                alt=""
                          >  {{ suggestion.profile}}</v-img>
                           <span
                            style="font-weight:700" > {{suggestion.name}} </span>
                        </div>
                    </div>
                </div>
                
                <v-card-text height="140">
                    <div class="line-clamp">
                       {{ suggestion.des }}
                    </div>
                </v-card-text>

                <YourIdea />
            </v-card>
        </v-col>
    </v-row>

    <!-- <v-row> -->
      
    <!-- </v-row> -->
</div>
</template>

<script>

export default {
    data() {
        return {
            suggestions: [
                {
                    _id: 1,
                    image: 'https://images.unsplash.com/photo-1571844088753-73ca0880bcd9?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NHx8YW5na29yJTIwd2F0fGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=500&q=60'
                    ,
                    title: "Angkor Thom",
                    des: " Angkor Thom is home to some of the most popular temples and nearly all tours will incorporate parts of the great city.The Angkor Wat Small Circuit Tour will take you to Bayon, the Terrace of the Elephants, the Leper King Terrace, and many others..."
                    ,
                    // profile: "../assets/pictures/pf1.png"
                    // profile: "https://data.whicdn.com/images/200614624/original.jpg"
                    // ,
                    name: "Vitou"
                },

                 {
                    _id: 2,
                    image: 'https://miro.medium.com/max/1170/1*BZoLp2qFmu80KzncTFMnpQ.jpeg'
                        ,
                        title: "Floating Village",
                        des: " I admire people who live in Floating Villages, travel to floating schools, and eat at Floating restaurants. It is very attractive for many visitors to Cambodia."
                        , name: "Tevy"

              },
              {
                    _id: 3,
                    image: 'https://ndm-travel.com/images/thumbnails/49448.png'
                        ,
                        title: "Tatai",
                        des: " Amazing place. Really natural, and also the people there very friendly and the food reasonable price and the boat has fixed price. "
                        , name: "Daro"

              },
              {
                    _id: 4,
                    image: 'https://a0.muscache.com/im/pictures/69b16064-12b5-4763-b899-b52d55a452e7.jpg?im_w=720'
                        ,
                        title: "Koh Kong",
                        des: " The island has many hills and is rich in natural scenery. There are waterfalls and you will stand mesmerized before the cascading waters of the fall from the height of 25 m."
                        , name: "Neary"

              },
              {
                    _id: 5,
                    image: 'https://s9.kh1.co/32/32ec2412b401c8d64c42ca01d46869e0499a441c.gif'
                        ,
                        title: "Knong Psar",
                        des: " If you're a camping lover, Knong Psar is where we highly recommend you to explore in cambodia. The nature in there will let you to find something new."
                        , name: "Yuthna"

              },
              {
                    _id: 6,
                    image: 'https://img.theculturetrip.com/1440x807/smart/wp-content/uploads/2021/05/2c4j3en-e1625485939998.jpg'
                        ,
                        title: "Koh Ta Kiev",
                        des: " Located in Ream National Park on the eastern edge of Sihanoukville, Koh Ta Kiev is just a stone’s throw from the mainland. "
                        , name: "Khemrith"

              },
            ],
            hasSaved: false,
            model: null,
            password: 'Password',
      show: false,
      message: '',
      marker: true,
      iconIndex: 0,
      icons: [
        'mdi-emoticon',
        'mdi-emoticon-cool',
        // 'mdi-emoticon-dead',
        'mdi-emoticon-excited',
        'mdi-emoticon-happy',
        'mdi-emoticon-neutral',
        // 'mdi-emoticon-sad',
        'mdi-emoticon-tongue',
      ],
        }
    },
     computed: {
      icon () {
        return this.icons[this.iconIndex]
      },
    },
    methods: {
        send() {
            this.hasSaved = true
        },toggleMarker () {
        this.marker = !this.marker
      },
      sendMessage () {
        this.resetIcon()
        this.clearMessage()
      },
      clearMessage () {
        this.message = ''
      },
      resetIcon () {
        this.iconIndex = 0
      },
      changeIcon () {
        this.iconIndex === this.icons.length - 1
          ? this.iconIndex = 0
          : this.iconIndex++
      },



    },
}
</script>

<style>
.line-clamp {
  display: -webkit-box;
  -webkit-line-clamp: 4;
  -webkit-box-orient: vertical;  
  overflow: hidden;
}

</style>
