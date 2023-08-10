# ngx_http_ihead_auth_request
Improved version of core nginx ngx_http_auth_request module

Originally only 2XX, 401 and 403 status codes are allowed to be returned from auth subrequest.

Codes 400, 412, 412, 444 are allowed.

Also the directive **ihead_auth_request_return_ok_on_error** was added. The default value is off.
The directive controls module behavior if subrequest returned error code (500, 502, 504).

If off the module return 444 if error code was returned from nginx subrequest.
If on the module return 200 if error code was returned from nginx subrequest.
