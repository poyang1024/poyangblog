<template>
    <div class="blog-post">
      <h2>{{ title }}</h2>
      <span class="author">{{ author }}</span>
      <p>{{ body }}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'BlogPost',
    props: {
      title: String,
      author: String,
      body: String
    }
  }
  </script>
  
  <style>
    .blog-post {
  margin: 20px 0;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.blog-post h2 {
  margin: 0;
  font-size: 1.5em;
}

.blog-post p {
  margin: 10px 0;
  font-size: 1.2em;
  line-height: 1.5;
}

.blog-post .author {
  display: block;
  font-size: 0.9em;
  color: #666;
}

  </style>
  