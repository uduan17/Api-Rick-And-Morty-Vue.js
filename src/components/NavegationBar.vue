<template>
<nav class="navbar navbar-expand-lg bg-body-tertiary bg-dark">
  <div class="container-fluid">
    <a class="navbar-brand mx-5" href="/"><img src="@/assets/ew.png" width="100" alt=""></a>
    <button class="navbar-toggler bg-white" type="button" data-bs-toggle="collapse" 
    data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" 
    aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0 d-flex justify-content-end ">
        <li class="nav-item">
          <a class="nav-link active text-white" aria-current="page" href="/">Person</a>
        </li>
        <li class="nav-item">
          <a class="nav-link text-white" href="/about">About the series</a>
        </li>
        <li class="nav-item">
          <a class="nav-link text-white" href="/suportt">Suportt us</a>
        </li>
      </ul>
    </div>
  </div>
</nav>
</template>
<!-- --------------------------------- -->
<script>
export default {
  name: 'NavegationBar',
}
</script>
<!-- ------------------------------- -->
<style scoped>
.navbar-collapse {
    flex-grow: 0;
}
</style>