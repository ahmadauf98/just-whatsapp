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
        <label class="text-white d-block mb-2">&reg; All Right Reserved - {{ new Date().getFullYear() }}</label>
        <b-badge class="text-capitalize" href="https://github.com/ahmadauf98/just-whatsapp" target="_blank" rel="noopener" variant="warning">Github</b-badge>
        
      </div>
    </div>
  </footer>
</template>

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
