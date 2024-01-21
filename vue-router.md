### 有哪些导航守卫

全局守卫：

1. router.beforeEach
2. router.afterEach
3. router.beforeResolve
   1. 这和 `router.beforeEach` 类似，因为它在 **每次导航**时都会触发，但是确保在导航被确认之前，**同时在所有组件内守卫和异步路由组件被解析之后，解析守卫就被正确调用**。

路由守卫：

`beforeEnter` 守卫 **只在进入路由时触发**，不会在 `params`、`query` 或 `hash` 改变时触发。例如，从 `/users/2` 进入到 `/users/3` 或者从 `/users/2#info` 进入到 `/users/2#projects`。它们只有在 **从一个不同的** 路由导航时，才会被触发。

组件内的守卫：

- `beforeRouteEnter(to, from, next)`
- `beforeRouteUpdate(to, from)`: 在当前路由改变，但是该组件被复用时调用
- `beforeRouteLeave(to, from)`