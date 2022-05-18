# RestTemplate

Spring自带的HTTP请求工具类，主要方式包含：GET 请求、POST 请求、PUT 请求、DELETE 请求以及一些通用的请求执行方法 exchange 。

主要包含的方法：

- xxxForObject，常规的 Rest API（GET、POST、PUT、DELETE 等）方法调用，返回值直接是响应体内容转为的 json 对象
- xxxForEntity，常规的 Rest API（GET、POST、PUT、DELETE 等）方法调用，返回值的封装包含有响应头, 响应状态码的 `ResponseEntity` 对象
- exchange，接收一个 `RequestEntity` 参数，可以自己设置 HTTP method，URL，headers 和 body，返回 ResponseEntity
- execute，通过 callback 接口，可以对请求和返回做更加全面的自定义控制

xxxForEntity、exchange都可以通过HttpEntity的方式携带Hearder

## Query&Path传参

请求query参数，可以通过在请求地址中利用占位符的方式`query?id={id}&name={name}`传递参数，将参数放在map对象中。

``` java
    public void getForObjectExam() {
        HashMap<String, Object> map = new HashMap<>();
        map.put("id", 1);
        map.put("name", "zs");
        RestResponse<ResponseClass> restResponse = restTemplate.getForObject(BASE_URL + "/query?id={id}&name={name}", RestResponse.class, map);
    }
```





## Body传参
