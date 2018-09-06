<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li>
        <a
          href="https://vuejs.org"
          target="_blank"
        >
          Core Docs
        </a>
      </li>
      <li>
        <a
          href="https://forum.vuejs.org"
          target="_blank"
        >
          Forum
        </a>
      </li>
      <li>
        <a
          href="https://chat.vuejs.org"
          target="_blank"
        >
          Community Chat
        </a>
      </li>
      <li>
        <a
          href="https://twitter.com/vuejs"
          target="_blank"
        >
          Twitter
        </a>
      </li>
      <br>
      <li>
        <a
          href="http://vuejs-templates.github.io/webpack/"
          target="_blank"
        >
          Docs for This Template
        </a>
      </li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li>
        <a
          href="http://router.vuejs.org/"
          target="_blank"
        >
          vue-router
        </a>
      </li>
      <li>
        <a
          href="http://vuex.vuejs.org/"
          target="_blank"
        >
          vuex
        </a>
      </li>
      <li>
        <a
          href="http://vue-loader.vuejs.org/"
          target="_blank"
        >
          vue-loader
        </a>
      </li>
      <li>
        <a
          href="https://github.com/vuejs/awesome-vue"
          target="_blank"
        >
          awesome-vue
        </a>
      </li>
    </ul>
    <div class='test' id='test' @click='clickTest'>
        <span class='text'>{{ testText }}</span>
        <span class='text'>{{ demoData }}</span>
    </div>
  </div>
</template>

<script>
    import Router from '../router/index';

    let  i = 0;
export default {
  name: 'HelloWorld',
  data () {
    console.log('init data');
    return {
      msg: 'Welcome to Your Vue.js App',
      demoData: '123'
    }
  },
  computed: {
    testText() {
        console.log('computed testText');
        return 'testText';
    }
  },
  methods: {
    clickTest() {
        console.log('clickTest');
        let dom = document.getElementById('test');
        this.demoData = `click count ${++i}`;
        if (dom) {
            if (dom.style.backgroundColor == 'red') {
                dom.style.backgroundColor = 'blue';
            }
            else {
                dom.style.backgroundColor = 'red';
            }
        }
        Router.push('test');
    }
  },
  beforeCreate() {
    console.log('beforeCreate');
  },
  created() {
    console.log('created');
  },
  beforeMount() {
    console.log('beforeMount');
  },
  mounted() {
    console.log('mounted');
  },
  beforeUpdate() {
    console.log('beforeUpdate', this.demoData);
  },
  updated() {
    console.log('updated', this.demoData);
  },
  beforeDestroy() {
    console.log('beforeDestory');
  },
  destroyed() {
    console.log('destroyed');
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style style='less' scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.test {
    width: 200px;
    height: 100px;
    border: 1px solid blue;
    background-color: blue;
    color: black;
    line-height: 100px;
}
.text {
    display: block;
}
</style>
