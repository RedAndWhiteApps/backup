<template>
  <v-card class="mx-auto d-flex flex-column" max-width="344" height="100%">
    <v-card-text>
      <div class="text-right">{{textTopRight}}</div>

      <p class="text-h4 font-weight-black">{{titleCard}}</p>

      <!-- <p>adjective</p> -->

      <div class="text-medium-emphasis"> {{TextOnFrontOfCard}}
        
      </div>
    </v-card-text>
    <v-card-actions>
      <v-btn
        color="primary"
        text="Learn More"
        variant="text"
        @click="reveal = true"
      ></v-btn>
    </v-card-actions>

    <v-expand-transition>
      <v-card
        v-if="reveal"
        class="position-absolute w-100"
        height="100%"
        style="bottom: 0"
      >
        <v-card-text class="pb-0">
          <p class="text-h4">...</p>

          <p class="text-medium-emphasis">
            {{TextOnBackofCard}}
          </p>
        </v-card-text>

        <v-card-actions class="pt-0">
          <v-btn
            color="primary"
            text="Close"
            variant="text"
            @click="reveal = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-expand-transition>
  </v-card>
</template>

<script>
export default {
  props: {
    titleCard: {
      type: String,
      required: true
    },
    textTopRight: {
      type: String,
      required: true
    },
    TextOnBackofCard: {
      type: String,
      required: true
    },
    TextOnFrontOfCard: {
      type: String,
      required: true
    }
  },
  data: () => ({
    reveal: false,
  }),
};
</script>
