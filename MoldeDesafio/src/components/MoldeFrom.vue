<script>
export default {
  name: "AppNavbar",
};

</script>

<template>
    <div class="NavBar ">
        <ul class="nav justify-content-center">
        <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="Moldetable">Pagina Inicial</a>
        </li>
        <li class="nav-item">
            <a class="nav-link" href="https://molde.me/sobre">Sobre</a>
        </li>
        <li class="nav-item">
            <a class="nav-link" href="https://molde.me/contato">Contatos</a>
        </li>
        <li class="nav-item">
            <a class="nav-link " href="https://molde.me" tabindex="-1" aria-disabled="true">Molde.me</a>
        </li>
        </ul>
</div>
</template>



<style scoped>
.NavBar{
    background-color: rgb(255, 255, 255);
    color: white;
    font-size: 20px;
    font-family:'Courier New', Courier, monospace;
     box-shadow: 0 4px 6px rgba(0,3,2,10.3);
    
    
}
.nav-link {
    color: black;
}
</style>
