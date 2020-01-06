# API

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/5a0b8d940d4dce0cb7a6)

{% api-method method="get" host="http://localhost:8080" path="/greeting" %}

{% api-method method="get" host="http://localhost:8080/greeting" path="" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
This endpoint provides you with a nice greeting.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="name" type="string" required=false %}
Person or entity to greet
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Greeting successfully generated.
{% endapi-method-response-example-description %}

```text
{"id":8,"content":"Hello, World!"}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Code Examples

{% tabs %}
{% tab title="Java" %}
#### GreetingClient.java

```java
package com.example.http;

import java.net.URI;
import java.net.URLEncoder;
import java.net.http.HttpClient;
import java.net.http.HttpRequest;
import java.net.http.HttpResponse;

public class GreetingClient {

    private final HttpClient httpClient = HttpClient.newBuilder()
            .version(HttpClient.Version.HTTP_2)
            .build();
            
    public String getGreeting(String name) throws IOException {
        HttpRequest request = HttpRequest.newBuilder()
                .GET()
                .uri(URI.create("http://localhost:8080/greeting?name=" + name))
                .build();

        HttpResponse<String> response = httpClient.send(request, HttpResponse.BodyHandlers.ofString());
        
        if(response.statusCode() >= 400) {
                throw new IOException("Request failed");
        }
        
        return response.getBody();
    }
    
}
```

#### Application.java

```java
package com.example.http;

public class Application {

    public static void main(String[] args) throws Exception {
        GreetingClient client = new GreetingClient();
        String greeting = client.getGreeting("MyName");
        System.out.println(greeting);
    }

}
```
{% endtab %}

{% tab title="Python" %}
#### Install requests package

```bash
$ pip install --user requests
```

#### application.py

```text
import requests

def get_greeting(name: str) -> dict:
    r = requests.get(f"http://localhost/greeting?name={name}")
    return r.json()
    
print(get_greeting("MyName"))
```
{% endtab %}
{% endtabs %}

