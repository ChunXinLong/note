# setup

## ref

```vue
<template>
	<navBar ref="navBar"></navBar>
</template>

<script>
  import { ref, onMounted } from "vue"
  steup(){
    const navBar = ref() // 这里的navBar必须和模板里定义的名称相同
    
    onMounted(()=>{
      console.log(navBar.value)  //这里的navBar只能获取navBar组件里的steup函数导出的值，未导出无法获取
    })
    
    return {
      navBar
    }
  }
</script>
```



## prop

```js
// 定义
const props = defineProps({
  title: String,
  likes: Number
})
// 使用,如果非语法糖写法，那么steup函数的第一个参数就是props
props.title
props.likes
// 在模板里使用，需要导出，如果是语法糖写法会自动导出，非语法糖写法需要手动导出，可以使用toRefs
steup(){
  return {
    ...toRefs(props)
  }
}
```

**使用TS**

```ts
const props = defineProps<{
  title?: string
  likes?: number
}>()
//或
type props = {
  title?: string
  likes?: number
}
const props = defineProps<props>()
```

### emits

```js

```

