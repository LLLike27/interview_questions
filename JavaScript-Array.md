### 数组的方法

1. `push` 末尾添加

2. `unshift()` 数组的开头添加值

3. `pop()` 删除最后一个元素

4. `shift()` 删除第一个元素

5. `slice([startIndex], [endIndex])` 获取部分值，不改变原数组

6. `splice([operateIndex], [deleteCount], ?[add element])` 删除和添加

7. `filter([callback])` 回调函数

8. `map()` 主要用于获取数组内元素

   ```js
   const movies = [
     { name: 'Wonder Woman', year: 2017 },
     { name: 'Dark Phoenix', year: 2019 },
     { name: 'Spider-Man Homecoming', year: 2017 },
   ]
   const moviesName = movies.map((movie) => {
      return movie.name 
   })
   console.log(moviesName)
   // ['Wonder Woman', 'Dark Phoenix', 'Spider-Man Homecoming']
   ```

   

9. `find()` 查找其中1个元素

   ```js
   const movies = [
     { name: 'Wonder Woman', year: 2017 },
     { name: 'Dark Phoenix', year: 2019 },
     { name: 'Spider-Man Homecoming', year: 2017 },
   ]
   const findMovie = movies.find((movie) => {
      return movie.name === 'Dark Phoenix'
   })
   //Output: { name: 'Dark Phoenix', year: 2019 }
   ```

   

10. `forEach()` 方法与 `for` 相似，具有一个函数和一个参数movie，对于每个电影，它都会打印出名称`movie.name`。

    ```js
    const movies = [
      { name: 'Wonder Woman', year: 2017 },
      { name: 'Dark Phoenix', year: 2019 },
      { name: 'Spider-Man Homecoming', year: 2017 },
    ]
    movies.forEach((movie) => {
       console.log(movie.name)
    })
    // Wonder Woman
    // Dark Phoenix
    // Spider-Man Homecoming
    ```

    

11. `reduce()` 可用于累加操作

    ```js
    let 累计器初始值 = 0
    const testScore = [
      { name: 'Ben',  score: 88 },
      { name: 'Joel', score: 98 },
    ]
    const scoreCount = testScore.reduce((累计器, 当前值, 当前索引, 源数组) => {
      console.log(累计器, 当前值)
      累计器 += 当前值.score
      // return 下次累计器的值 = return 的内容
      return 累计器
    }, 累计器初始值)
    // 打印 186
    console.log(scoreCount)
    ```

    

12. `includes()` 检查数组是否包含某个值

    ```js
    // 打印 true
    const include3 = [1, 2, 3].includes(3)
    ```

    

### 数组去重

1. new Set() 转换为 set，再结构set为数组
2. 使用循环查找