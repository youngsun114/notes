https://spring.io/understanding/REST

1. REST 理解
Representation State Transfer  代表性状态传输
2. REST 原则： 
   Resources -- 也就是URIs，要易于理解；
   Representations -- 使用JSON/XML代表数据对象和属性
   Messages  -- HTTP方法   GET/POST/PUT/PATCH/DELETE
   Stateless  -- 无状态的请求
3. HTTP请求
   GET 获取信息   GET /addresses/1 
   POST  提供一个实体请求URI做一些事情。比如Create/Update    POST  /addresses
   PUT   存储(替换)一个实体。是幂等的，POST不是幂等的。-- 如果一个方法反复执行多次，产生的效果是一样的。  PUT /addresses/1
   PATCH 用来对已知资源的局部更新  也是幂等的  PATCH /addresses/1
   DELETE   请求删除一个资源    DELETE /addresses/1  
   区别： POST和PUT都是传递的内容代表整个实体，POST是将没提供的属性不改变，PUT将没给的属性置为空或者null。
              幂等 -- 比如新建一个文章，两个POST请求可能产生两个文章，那么就不是幂等的，如果是后面的请求覆盖掉第一个，这个服务就是幂等的。 判断使用POST还是PUT就是根据这种方式。              
               PATCH是对PUT的补充，只对实体中的特定属性更新。
     -- 如果REST是放到网络中使用的话，最好遵循HTTP规范定义API.
4. HTTP 状态码
             1xx   informational  
             2xx   success
             3xx   redirection 
             4xx   client error
             5xx    server error 
  返回状态码的时候，根据错误的来源来确定使用那一个。
5. Media types
 Accept    
 Content-Type
如果希望response是JSON，设置Accept为application/json,如果发送的xml，设置Content-Type为application/xml