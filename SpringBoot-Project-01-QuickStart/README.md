# springboot的基础演示
关于springboot的基础演示  
~~因为是早期生成的,有许多不完善的地方~~已更新  
主要进行了以下几点:  
 
- `QuickstartController` springboot中最基础的演示,包含了@RestController的应用,以及get的传参

- `PageController` 演示了如何通过@Controller路由到页面

- `ValueController` 演示了如何通过@Value从配置文件中获取数据

- `@ConfigurationProperties`的用法,与@Value相似,可以注入到javabean中  
  演示案例在测试文件`ConfigurationPropertiesTestContext`中
  
- `MybatisController` 演示了如何mybatis与springboot如何结合,以及事务的开启

- 过滤器和拦截器的使用
  关于filter和interceptor的区别:
  1. filter是servlet提供的,而interceptor属于springMVC.两者所在层次不一样
  2. 因此在spring的框架中,使用interceptor更容易些,且能可操作精细度更大
  3. 因为是filter属于servlet,因此会优先于interceptor
  2. filter可以拦截所有访问服务器的请求,而interceptor只能拦截访问controller的请求
    事实上当请求会先到达DispatcherServlet(前端控制器controller),然后再发送至interceptor  

## 拓展补充:关于@InitBinder(项目中未使用)

一般用于input标签中(表单),使用ognl表达式向后端发送数据(user.name,user.id; addr.name,addr.id)  
遇到后缀相同的时候springMVC无法进行解析,因此需要使用@InitBinder来区分各自的后缀  

>参考:https://blog.csdn.net/qq_24505127/article/details/54236583
