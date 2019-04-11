# SDGophers Challend 4/16/2019

## Building a proxy

### Level 1

Build a HTTP proxy that can simply take and incoming request and forward it to 
a backend server (e.g. google.com, walmart.com) and respond back to the user with
the backends response.

should also set the proper `X-Forwarded-For` header.

### Level 2

Add support for falling back to another backend if the primary fails.

## Level 3

Add support for modifiying the request object using go plugins, program should 
be able to import compiled go plugins and execute a known function in them in sequence.

Example:
```
package main

import "net/http"

func BeforeRequest(r *http.Request) {
  r.Header.Add("X-Debug", "1")
}

func BeforeResponse(resp http.Response) {
  r.Header.Add("X-Backend", "test-server")
}
```
