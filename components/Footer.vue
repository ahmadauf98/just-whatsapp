<template>
  <footer class="Footer py-3 d-flex justify-content-center text-center">
    <div class="row">
      <div class="col-12 col-md ">
        <b-navbar-brand class="text mx-auto my-auto h1" >
      <img
        src="~/static/brand.svg"
        alt="just whatsapp brand logo"
        width="30px"
      />
      Just <b>Whatsapp</b> Developer</b-navbar-brand
    >
        </svg>
        <div class="text-white d-block mb-3">&reg; All Right Reserved - {{ new Date().getFullYear() }}</div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {}
</script>

<style  scoped>
.Footer{
    background-color: #00473e;
}

.text{
  color: #faae2b;
}

.text-white{
    color: white;
}
</style>
