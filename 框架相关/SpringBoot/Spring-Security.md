#### 认证操作流程：

1. 后端从前端的表单得到用户密码，包装成一个Authentication类的对象；
2. 将Authentication对象传给“验证管理器”ProviderManager进行验证；
3. ProviderManager在一条链上依次调用AuthenticationProvider进行验证；验证成功则返回一个封装了权限信息的Authentication对象（即对象的Collection<? extends GrantedAuthority>属性被赋值）；
4. 将此对象放入安全上下文SecurityContext中；
5. 需要时，可以将Authentication对象从SecurityContextHolder上下文中取出。

#### 认证操作

```java
public void configure(AuthenticationManagerBuilder auth) throws Exception {
    //配置认证，向设定用户名密码的用户 授予权限
    auth.inMemoryAuthentication().passwordEncoder(new BCryptPasswordEncoder()).withUser("root").
            password(new BCryptPasswordEncoder().encode("root")).roles("user","admin");
    auth.inMemoryAuthentication(AuthenticationManagerBuilder auth){
        auth.inMemoryAuthentication().passwordEncoder(new BCryptPasswordEncoder()).withUser("guest").
                password(new BCryptPasswordEncoder().encode("123456")).roles("user");
    }
}
```

#### 自定义其他认证

```java
@Component
public class MyAuthenicaton implements AuthenticationProvider {
    //Authentication代表一种认证方式，
    @Override
    public Authentication authenticate(Authentication authentication) throws AuthenticationException {
        //获取用户名
        String name = authentication.getName();
        //获取密码
        String password = authentication.getCredentials().toString();

        //设置认证规则，通过后用SimpleGrantedAuthority授予权限
        if(name.equals("dachuan")){
            Collection<GrantedAuthority> authorities =  new ArrayList<>();
            //ROLE_之后代表权限，注意区分大小写
            authorities.add(new SimpleGrantedAuthority("ROLE_admin"));
            authorities.add(new SimpleGrantedAuthority("ROLE_user"));
            //伪装成admin用户
            return new UsernamePasswordAuthenticationToken("admin",password,authorities);
        }
        return null;
    }

    @Override
    public boolean supports(Class<?> authenication) {
        return authenication.equals(UsernamePasswordAuthenticationToken.class);
    }
}
```

#### 取出输入的认证对象

```java
@RequestMapping({"/", "/index"})
public String index(Model model){
    Authentication auth = SecurityContextHolder.getContext().getAuthentication();
    Collection<GrantedAuthority> authorityCollection = (Collection<GrantedAuthority>) auth.getAuthorities();
    model.addAttribute("authorities", authorityCollection.toString());
    model.addAttribute("username", SecurityContextHolder.getContext().getAuthentication().getName());
    return "index";
}
```

#### 数据库认证





#### 授权操作

