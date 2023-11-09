<template>
  <div>{{ greet }} {{ name }}</div>
  <div>{{ channel }}</div>
  <div v-html="channel"></div>
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

  <h2 v-bind:style="{ color: highlightColor,fontSize : headerSize + 'px', padding: '20px'}">
    Inline Style
  </h2>

  <h2 v-bind:style="headerStyleObject">Inline Style</h2>

  <div v-bind:style="[baseStyleObject, successStyleObject]">
    Success Style
  </div>

  <div v-bind:style="[baseStyleObject, dangerStyleObject]">
    Success Style
  </div>
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
        highlightColor: 'orange',
        headerSize: 50,
        headerStyleObject:
        {
          color: 'orange',
          fontSize: '50px',
          padding: '20px'
        },
        baseStyleObject:
        {
          fontSize: '50px',
          padding: '10px'
        },
        successStyleObject:
        {
          color: 'green',
          backgroundColor: 'lightgreen',
          border: '1px solid green',
          padding: '20px'
        },
        dangerStyleObject:
        {
          color: 'darkred',
          backgroundColor: 'red',
          border: '1px solid red',
          padding: '20px'
        }
      };
    }
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
