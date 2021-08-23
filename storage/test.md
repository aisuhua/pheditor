```sh
location /foo {
     # fastcgi_pass/proxy_pass/...

     header_filter_by_lua_block { ngx.header.content_length = nil }
     body_filter_by_lua 'ngx.arg[1] = string.len(ngx.arg[1]) .. "\\n"';
 }
```