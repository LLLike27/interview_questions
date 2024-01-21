**webpack优化**



**结果优化**

1. 分包处理

2. - 多入口

   - 动态导入

   - - webpackPrefetch 空闲下载
     - webpackPreload 并行下载

   - 防止重复

3. 代码压缩（丑化）

4. 删除无用代码

5. CDN服务器

6. - 全部放到CDN: publicPath

   - 部分放入CDN

   - - externals 配置不打包
     - html中引入CDN地址



打包速度

1. excluse/cache