<script>
import axios from "axios";
export de4fault {
  data: function () {
    return {
      posts: [],
    };
  },
  created: function () {
    this.indexPosts();
  },
  methods: {
    indexPosts: function () {
      axios.get("/posts.json").then((respons) => {
        this.posts = response.data;
        console.log("Posts: ", response.data);
      });
    },
  },
};
</script>
