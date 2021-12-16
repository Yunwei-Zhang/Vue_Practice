# client

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).



<div v-for="(item, key) in skills" :key="key">
<a-card :title="item.skillname" :bordered="false">
在<div>中调用，原来在react中是title = {item.skillname}, 儿子vue中是 :title= "item.skillname"

<p>{{item.skillname}}</p>
文本调用时， react是{item.skillname}, vue是{{item.skillname}}

<div class="resume_skillitem" :style="{'--p-height': item.percentage}"></div>
.resume_skillitem{
    height: 30px;
    width: var(--p-height);
    background-color: aqua;
}
在vue中css和variable交互使用以上方法，而react是<div style={{height: this.state.xxx}}></div>
