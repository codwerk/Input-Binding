<template>
 <div id="add-blog">
   <h2>New Blog Post</h2>
   <form>
     <label>Blog Titre</label>
     <input type="text" v-model.lazy="blog.title">
     <label>Blog Content</label>
     <textarea v-model.lazy="blog.content"></textarea>
     <div id="checkboxes">
       <label for="">Dev Front End</label>
       <input type="checkbox" value="front" v-model="blog.categories">
       <label for="">Dev Back End</label>
       <input type="checkbox" value="back" v-model="blog.categories">
       <label for="">Dev Full Stack</label>
       <input type="checkbox" value="full" v-model="blog.categories">
       <label for="">Dev Ops</label>
       <input type="checkbox" value="ops" v-model="blog.categories">
     </div>

     <label for="">Author:</label>
     <select name="" v-model="blog.author">
       <option value="authors" v-for="(author, index) in Authors" :key="index"> {{ author }}</option>
     </select>
   </form>

   <div id="preview">
     <h3>Preview Blog</h3>
     <p>Blog Title: {{ blog.title }}</p>
     <p>Blog Content: {{ blog.content }}</p>
     <p>Blog Category: </p>
     <ul class="list">
       <li v-for="(category, index) in blog.categories" :key="index"> {{ category }} </li>
     </ul>
     <p>Blog Author : {{ blog.author }}</p>
   </div>
 </div>
</template>

<script>
 export default {

   name: 'addBlog',
   data: () => {
     return {
       blog: {
         title: '',
         content: '',
         categories: [],
         author: ''
       },
       Authors: ['TraversyMedia', 'Grafikart', 'TheNetNinja']
     }
   }
  }
</script>

<style lang="scss" scoped>
  #add-blog {
    min-height: 100vh;
    max-width: 500px;
    margin: 0 auto;
    form {
      
      text-align: left;

      label {
        margin: 20px 0 10px;
      }

      label, input[type="text"], textarea {
        display: block;
      }

      input[type="text"], textarea {
        width: 100%;
      }

      #checkboxes {
        label, input[type="text"] {
          display: inline-block;
        }

        input[type="checkbox"] {
          margin-right: 10px;
        }
      }
    }

    #preview {
      padding: 10px 20px;
      border: 1px solid #ccc;
      margin: 30px 0;

      h3 {
        margin-top: 10px;
      }

      .list {
        padding: 0;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        li {
          list-style: none;
        }
      }
    }
  }
</style>