<template>
  <section class="container">
    <h1>This is area for ckeditor</h1>
      <textarea name="editor1" v-model="content" class="ckarea"></textarea>
  </section>
</template>

<script>
// import ckeditor from 'ckeditor'
export default {
  data(){
    return {
      content: ` code javascript:
      <pre><code class="language-javascript">
var x, y, z;  // Declare 3 variables
x = 5;        // Assign the value 5 to x
y = 6;        // Assign the value 6 to y
z = x + y;    // Assign the sum of x and y to z

document.getElementById("demo").innerHTML =
"The value of z is " + z + ".";
</code></pre><br>`
    }
  },
  head: {
    script: [
      { 
        src: '/ckeditor/ckeditor.js' 
        
        }
    ]
  },

  mounted(){
    var roxyFileman = '/fileman/index.html'; 
    CKEDITOR.replace( 'editor1',{
      // customConfig:'/custom_config.js',
      extraPlugins : 'codesnippet',
      // filebrowserBrowseUrl: '/fileman/browse.vue',
      // filebrowserUploadUrl : '/fileman/upload.php'
      filebrowserBrowseUrl:roxyFileman,
      filebrowserImageBrowseUrl:roxyFileman+'?type=image',
      removeDialogTabs: 'link:upload;image:upload'
    } );
  }
}
</script>

<style>
.cke_contents{
  height: 50vh !important;
}

</style>
