  <template>
  <div id="nav">
  <h1 class="headers">TodoList :)</h1>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
</template>

<script>
export default {
    name:"headers"
 
 
}
</script>
<style  scoped>
.headers{
    background: #333;
    color:#fff;
    text-align: center;
    padding: 10px;
}
.headers a {
    color: #fff;
    padding-right: 5px;
}
</style>

