# 참과 거짓 값 Truth & Falsy

### Falsy

{% code title="Falsy(거짓으로 평가되는)값" lineNumbers="true" %}
```javascript
false
undefined
null
0
-0
Nan
''
```
{% endcode %}

위 Falsy값을 제외한 나머지는 모두 Truthy이다.



```javascript
//"pending"은 이미 truthy이기 때문에 state === "pending"이 되어서 true
state === ("pending" || "accepted") 

//다음과 같이 구분해서 평가해야 한다.
state === "pending" || state === "accepted"
```
