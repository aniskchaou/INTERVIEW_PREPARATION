## Observable vs Promise
![enter image description here](https://miro.medium.com/max/3168/1*DraWzmN4xkcazpq1G7FLMQ.png)
**Observable**

1.  Emits multiple values over a period of time
2.  Is not called until we subscribe to the Observable
3.  Can be canceled by using the unsubscribe() method
4.  Provides the map, forEach, filter, reduce, retry, and retryWhen operators

**Promise**

1.  Emits only a single value at a time
    
2.  Calls the services without .then and .catch
    
3.  Cannot be canceled
    
4.  Does not provide any operators

![enter image description here](https://1a61nt9057119c295doq7gnd-wpengine.netdna-ssl.com/wp-content/uploads/2018/11/8c5df81b-1953ab46-observable-vs-promise.png)
![enter image description here](https://i.stack.imgur.com/bazKh.png)