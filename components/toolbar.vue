<template>
  <div>
    <b-navbar class="d-block d-sm-block d-md-block d-lg-none" toggleable type="dark" breakpoint="medium">
     <b-navbar-toggle target="navbar-toggle-collapse">
       <template #default="{ expanded }">
         <b-icon icon="justify"></b-icon>
       </template>
     </b-navbar-toggle>

     <b-collapse id="navbar-toggle-collapse" is-nav>
       <b-navbar-nav class="ml-auto">
         <b-nav-item href="#">Home</b-nav-item>
         <b-nav-item href="#educations">Educations</b-nav-item>
         <b-nav-item href="#experience">Experiences</b-nav-item>
         <b-nav-item href="#contact">Contact</b-nav-item>
       </b-navbar-nav>
     </b-collapse>
   </b-navbar>
    <b-navbar
    class="d-none d-lg-block font"
    toggleable="lg"
    type=""
    variant="transparent">
      <b-navbar-brand href="#" class="font">Home</b-navbar-brand>
      <b-navbar-brand href="#educations" class="font">Educations</b-navbar-brand>
      <b-navbar-brand href="#experience" class="font">Experiences</b-navbar-brand>
      <b-navbar-brand href="#contact" class="font">Contact</b-navbar-brand>
    </b-navbar>
  </div>
</template>

<style scoped>
  .font {
    color: white
  }
</style>
