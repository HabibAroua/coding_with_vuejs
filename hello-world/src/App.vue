<template>
  <div>{{ greet }} {{ name }}</div>
  <div>{{ channel }}</div>
  <div v-html="channel"></div>text
  <div v-html="hack"></div>
  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">Bind</button>
  <h2 class="underline">Underlined text</h2>
  <h2 class="underline" v-bind:class="status">Status</h2>
  <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 v-bind:class="isSoldOut ? 'sold-out' : 'new' " >SoldOut? movie</h2>
  <h2 v-bind:class="['new', 'promoted']" >Newly promoted movie</h2>
  <h2 v-bind:class="[isPromoted && 'promoted',isSoldOut ? 'sold-out' : 'new']" >
    Array conditional movie
  </h2>
  <h2 v-bind:class="{ promoted: isPromoted, new: !isSoldOut, 'sold-out': isSoldOut }" >
    Object conditional movie
  </h2>

  <h2 v-bind:style="{color: highlightColor}">Inline Style</h2>
</template>

<script>

  export default 
  {
    name: 'App',
    data()
    {
      return {
        greet: "Hello",
        name: "Habib Aroua",
        channel: "<b>Codeevolution</b>",
        hack: `<a href="#" onclick="alert('You have been hacked')">Win a prize!</a>`,
        headingId: 'heading',
        isDisabled: false,
        status: 'success',
        isPromoted: true,
        isSoldOut: true,
        highlightColor: 'orange'
      };
    }
  //Font Size
  }
</script>

<style>
  #app 
  {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  .underline
  {
    text-decoration: underline;
  }

  .promoted
  {
    font-style: italic ;
  }

  .new 
  {
    color: olivedrab;
  }

  .sold-out 
  {
    color: red;
  }
</style>
