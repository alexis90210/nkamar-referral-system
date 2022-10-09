<template>
  <div class="has-background-link-dark h100">
  
  </div>
</template>

<script>
export default {
  data() {
    return {
      isLoading: true,
    };
  },
  async mounted(){
    this.$router.push({path:'/inscription' , query:{
        parrainnage:true,
        from_registered_user:true,
        formule:1,
        referral:this.$route.params.identifiant
    }})
  }
};
</script>

<style></style>
