# API

{% api-method method="get" host="http://localhost:8080" path="/greeting" %}
{% api-method-summary %}
Get Default Greeting
{% endapi-method-summary %}

{% api-method-description %}
This endpoint provides you with a nice greeting for the whole World.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Greeting successfully generated.
{% endapi-method-response-example-description %}

```
{"id":8,"content":"Hello, World!"}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="http://localhost:8080/greeting" path="" %}
{% api-method-summary %}
Get Custom Greeting
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

```
{"id":8,"content":"Hello, World!"}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

