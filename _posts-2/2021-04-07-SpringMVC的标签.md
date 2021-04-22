---
layout: post
title: "SpringMVC的标签"
date: 2021-04-07
description: "SpringMVC的标签"
tag: SpringMVC
---   
@PostMapping
映射一个POST请求

Spring MVC新特性 
提供了对Restful风格的支持
增加了get,post,delete,patch

@GetMapping，处理get请求，是@RequestMapping(method = RequestMethod.GET)的缩写。
@PostMapping，处理post请求，是@RequestMapping(method = RequestMethod.POST)的缩写。
@PutMapping，处理put请求 
@DeleteMapping，处理delete请求

> @PostMapping(value = "/user/login")

等价于

> @RequestMapping(value = "/user/login",method = RequestMethod.POST)

> @PostMapping(value = "/user/login")
> public String login(@RequestParam("user") String name,
>					  @RequestParam("pass") String pass) {

![](/images/posts/spring/1.png)
![](/images/posts/spring/2.png)
![](/images/posts/spring/3.png)
![](/images/posts/spring/4.png)

### Request Get的2种方式
#### 方式1.
> @RequestMapping(value = "/user.do", method = RequestMethod.GET)
> public ModelAndView getUserByID(int id) {

访问连接 http://localhost:8080/ssm/user.do?id=1

#### 方式2.
> @GetMapping(value = "/user.do/{id}")
> public ModelAndView getUserByID(@PathVariable("id") int id) {

访问连接 http://localhost:8080/ssm/user.do/1
