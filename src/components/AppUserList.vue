<template>
  <section>
    <ul class="userlist">
      <li v-for="item in data.results" :key="item.email">
        <div>
          <img
            width="48"
            height="48"
            :src="item.picture.large"
            :alt="item.name.first + ' ' + item.name.last"
          />
          <div>
            <div>{{ item.name.first }}</div>
          </div>
        </div>
      </li>
    </ul>
  </section>
</template>

<script>
const states = {
  idle: "idle",
  loading: "loading",
  loaded: "loaded",
  failed: "failed"
};
export default {
  data() {
    return {
      state: "idle",
      data: undefined,
      error: undefined,
      states
    };
  },
  mounted() {
    this.load();
  },
  methods: {
    async load() {
      this.state = "loading";
      this.error = undefined;
      this.data = undefined;
      try {
        const response = await fetch("https://randomuser.me/api/?results=5");
        const json = await response.json();
        this.state = "loaded";
        this.data = json;
        return response;
      } catch (error) {
        this.state = "failed";
        this.error = error;
        return error;
      }
    }
  }
};
</script>

<style>
.userlist {
  margin: 10px;
  list-style-type: none;
}
.userlist img {
  border-radius: 50%;
  margin-right: 1rem;
}
.userlist li + li {
  margin-top: 10px;
}
.userlist li > div {
  display: flex;
  align-items: center;
}

</style> 