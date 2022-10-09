<template>
    <div class="max-height-100 cs">
      <!-- stats -->
      <p class="menu-label mt-3">NOTIFICATIONS</p>
      <div class="box" v-for="i in 10" :key="i" style="zoom:90%">
        <div class="columns" >
          <div class="column">
            <div class="media">
              <div class="media-left">
                <figure class="image is-48x48">
                  <img
                    src="@/assets/icon.png"
                    alt="Placeholder image"
                    style="border-radius: 50%"
                  />
                </figure>
              </div>
              <div class="media-content">
                <p class="title is-4 is-size-6">ALERTE</p>
                <p
                  class="subtitle is-6 is-size-7 is-flex is-flex-direction-row is-justify-content-start is-align-items-center"
                >
                  message de la notification
                </p>
              </div>
            </div>
          </div>
  
          <div class="column is-one-fifths">
            <div class="go-right">
             <p class="is-size-7"> {{new Date().toISOString()}}</p>
            </div>
          </div>
        </div>      
      </div>

  
    </div>
  </template>
  
  <script>
  export default {
    layout: "dashboard",
    components: {},
    data() {
      return {
        preview: false,
        isFeedback:false,
        file: {},
      };
    },
    methods: {},
  };
  </script>
  
  <style>
  .max-height-100 {
    height: 100vh;
    max-height: 100vh;
    overflow-y: scroll;
  }
  </style>
  