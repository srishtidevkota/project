<template>

  <h1>Job Details Page</h1>  
  <P> The job id is {{ id }} </p>
  
</template>

<script>


export default {
    props: ['id'],
    mounted() {
      fetch('http://localhost:3000/jobs' + this.id)
        .then(res => res.json())
        .then(data => this.jobs = data)
        .catch(err => console.log(err.message))
    }
   // data() {
      //  return {
     //       id: this.$route.params.id
       // }
  //  },
}
</script>



