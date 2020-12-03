```java
filterMap.put("/**","user"); //user表示配置记住我或认证通过可以访问的地址
/*修改被拦截之后跳转的页面  参数为controller的 RequestMapping*/
shiroFilterFactoryBean.setLoginUrl("/tologin");
/*登录成功后跳转的连接*/
//shiroFilterFactoryBean.setSuccessUrl("/index");
/*设置未授权跳转的页面*/
shiroFilterFactoryBean.setUnauthorizedUrl("/noAuth");
/*将存好的权限交给shiroFilterFactoryBean 处理*/
shiroFilterFactoryBean.setFilterChainDefinitionMap(filterMap);
```