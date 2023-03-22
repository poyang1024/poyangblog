<template>
    <div>
      <h1>Blog Posts</h1>
      <ul>
        <li v-for="post in posts" :key="post.id">
          <BlogPost :title="post.title" :author="post.author" :body="post.body" />
        </li>
      </ul>
    </div>
  </template>
  
<script>
  import BlogPost from './post.vue'
  
  export default {
    name: 'BlogList',
    components: {
      BlogPost
    },
    data() {
      return {
        posts: [
          {
            id: 1,
            title: 'My First Blog Post',
            author: 'Jane Doe',
            body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
          },
          {
            id: 2,
            title: 'My Second Blog Post',
            author: 'John Doe',
            body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
          },
          {
            id: 3,
            title: 'My Third Blog Post',
            author: 'John Doe',
            body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
          },
          {
            id: 4,
            title: 'My Forth Blog Post',
            author: 'John Doe',
            body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
          }
        ]
      }
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