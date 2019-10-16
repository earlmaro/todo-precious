<template>
  <div id="app">
     <headers/>
    <router-view/>
  </div>
</template>
<script>
import headers from "./components/layouts/headers";
export default {
  name: 'app',
  components:{
    headers
  }
}
</script>

<style >
*{
  box-sizing:border-box;
  margin: 0;
  padding: 0;
}
body{
  font-family: arial,helvetica,sans-serif;
  line-height: 1.4;
}
.btn{
  cursor:pointer;
  padding:7px 20px;
  text-transform: capitalize;
  display: inline;
}
.btn:hover{
  background:#666
}
</style>

