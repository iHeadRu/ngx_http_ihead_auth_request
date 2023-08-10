# ngx_http_ihead_auth_request
Improved version of core nginx [ngx_http_auth_request module](https://nginx.org/en/docs/http/ngx_http_auth_request_module.html)

Originally only 2XX, 401 and 403 status codes are allowed to be returned from auth subrequest.

**Codes 400, 412, 412, 444 are allowed.**

## Directives
### ihead_auth_request (as original auth_request)
 Syntax: 	ihead_auth_request uri | off;  
 Default: 	ihead_auth_request off;  
 Context: 	http, server, location  

Enables authorization based on the result of a subrequest and sets the URI to which the subrequest will be sent. 

### ihead_auth_request_set (as original auth_request_set)
 Syntax: 	ihead_auth_request_set $variable value;  
 Default: —  
 Context: http, server, location  

Sets the request variable to the given value after the authorization request completes. The value may contain variables from the authorization request, such as $upstream_http_*. 

### ihead_auth_request_return_ok_on_error (added)
 Syntax: 	ihead_auth_request_return_ok_on_error on | off;  
 Default: 	ihead_auth_request_return_ok_on_error off  
 Context: 	http, server, location  

The directive controls module behavior if subrequest returned error code (500, 502, 504).  
If off the module will return 444 on error.  
If on the module will return 200 on error.  
