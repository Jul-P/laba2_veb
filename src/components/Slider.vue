<template>
  <v-carousel v-model="model" height="100%" continuous="true">
    
    <v-carousel-item

      v-for="(item, i) in pictures"
      :key="i"
    >
      <v-sheet
        :color="item.color"
        height="100%"
        tile
      >
        <v-row
          class="fill-height"
          align="center"
          justify="center"
        >
          <div class="display-3">

               <v-card width="900" class="mx-auto" elevation="10">
            <v-list-item>
                <v-list-item-content>
                    
                    <v-list-item>
                        <div>
                            
                            <p>Name: {{Name}}</p>                           
                            <p>Company: {{Company}}</p>
                           
                        </div>
                    </v-list-item>
                </v-list-item-content>
                <v-list-item-avatar size="200">
                    <v-img
                    :src="item.picture"
                    >
                    </v-img>
                </v-list-item-avatar>
                <v-list-item-action>
                </v-list-item-action>
            </v-list-item>
            <v-card-actions>
                <v-btn
                        :color="item.color"
                        text
                    >
                        Comment:
                    </v-btn>

                   <!-- <v-spacer></v-spacer>-->

                    <v-btn
                        icon
                        @click="Show = !Show"
                    >
                    <v-icon>{{ Show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
                    </v-btn>
            </v-card-actions>
            <div v-show="Show">

                <p> {{item.text}}</p>
            </div>

        </v-card>
            
          </div>
        </v-row>
      </v-sheet>
    </v-carousel-item>
  </v-carousel>
</template>

<script>
  export default {
    data: () => ({
      model: 0,
      Show: false,
      colors: [
        'primary',
        'secondary',
        'yellow darken-2',
        'red',
        'orange',
      ],
      pictures: [
          { picture:"https://i.pinimg.com/originals/23/bb/46/23bb46556219e001c18136aab903eed8.jpg",
             color:"primary",
             text:"привет"
          },
          
          {picture:"https://get.pxhere.com/photo/hair-fur-sheep-mammal-fauna-chile-llama-alpaca-furry-lama-vertebrate-south-america-animal-world-camel-like-mammal-dog-breed-group-595906.jpg",
             color:"red",
             text:"Здесь будет магия"},

          {picture:"https://fb.ru/media/i/6/1/4/7/2/3/i/614723.jpg",
             color:"yellow darken-2",
             text:"Всё плохо"},

             {picture:"http://ae01.alicdn.com/kf/HTB1HrsSakL0gK0jSZFtq6xQCXXaJ/DIAPAI-5D-DIY.jpg",
             color:"yellow darken-2",
             text:"Отлично!!!"}
          ]
    }),
  }
</script>