<template>
      <div id="box">
        <aside>
          <div id="one">
          <router-link to="/"><input type="button" value="首页"></router-link>
          </div>
          <div id="two">
          <router-link to="/about"><input type="button" value="文章"></router-link>
          </div>
        </aside>
        <div id="right">
            <header></header>
            <article><router-view/></article>
        </div>
    </div>
</template>

<style>
#box {
    position: absolute;
    display: flex;
    width: 100%;
    height: 100%;
}

aside {
    width: 170px;
    border: 1px solid black;
    margin-right: 5px;
    text-align: center;
}

#one{
  margin-top: 80px;
}

#two{
  margin-top: 30px;
}

input{
  height: 40px;
  width: 120px;
}

#right {
    display: flex;
    width: 100%;
    flex-direction: column;
}

header {
    border: 1px solid black;
    height: 80px;
    margin-bottom: 5px;
}

article {
    border: 1px solid black;
    height: 100%;
    text-align: center;
}
</style>
