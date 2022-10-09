<template>
  <div>
     <!-- MODAL -->
     <div class="modal is-active" style="z-index: 100">
      <div class="modal-background"></div>
      <div class="modal-content">
        <div class="box">
          <div class="media">
          <div class="media-left">
            <figure class="image is-48x48">
              <img
                src="@/assets/icon.png"
                alt="Nkamar app"
              />
            </figure>
          </div>
          <div class="media-content">
            <p class="title is-4">{{user.code}} {{user.mobile}}</p>
            <p class="subtitle is-6">@{{user.mobile}}</p>
          </div>
        </div>
        <div class="content">
          Votre inscription est bientot terminee, veuillez indiquez votre parrain
          <br />
          
        </div>
        </div>
      </div>
    </div>

    <!--  -->
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>