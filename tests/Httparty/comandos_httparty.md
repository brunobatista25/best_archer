http://watir.com/guides/wysiwyg/

## classe metods

#base_uri(uri = nil) ⇒ Object
Allows setting a base uri to be used for each request.
#basic_auth(u, p) ⇒ Object
Allows setting basic authentication username and password.
#ciphers(cipher_names) ⇒ Object
Allows setting of SSL ciphers to use.
#connection_adapter(custom_adapter = nil, options = nil) ⇒ Object
Allows setting a custom connection_adapter for the http connections.
#cookies(h = {}) ⇒ Object
#copy(path, options = {}, &block) ⇒ Object
Perform a COPY request to a path.
#debug_output(stream = $stderr) ⇒ Object
Set an output stream for debugging, defaults to $stderr.
#default_params(h = {}) ⇒ Object
Allows setting default parameters to be appended to each request.
#default_timeout(t) ⇒ Object
Allows setting a default timeout for all HTTP calls Timeout is specified in seconds.
#delete(path, options = {}, &block) ⇒ Object
Perform a DELETE request to a path.
#digest_auth(u, p) ⇒ Object
Allows setting digest authentication username and password.
#disable_rails_query_string_format ⇒ Object
Do not send rails style query strings.
#follow_redirects(value = true) ⇒ Object
Proceed to the location header when an HTTP response dictates a redirect.
#format(f = nil) ⇒ Object
Allows setting the format with which to parse.
#get(path, options = {}, &block) ⇒ Object
Allows making a get request to a url.
#head(path, options = {}, &block) ⇒ Object
Perform a HEAD request to a path.
#headers(h = nil) ⇒ Object
Allows setting HTTP headers to be used for each request.
#http_proxy(addr = nil, port = nil, user = nil, pass = nil) ⇒ Object
Allows setting http proxy information to be used.
#logger(logger, level = :info, format = :apache) ⇒ Object
Turns on logging.
#maintain_method_across_redirects(value = true) ⇒ Object
Declare that you wish to maintain the chosen HTTP method across redirects.
#mkcol(path, options = {}, &block) ⇒ Object
Perform a MKCOL request to a path.
#move(path, options = {}, &block) ⇒ Object
Perform a MOVE request to a path.
#no_follow(value = false) ⇒ Object
Declare whether or not to follow redirects.
#open_timeout(t) ⇒ Object
Allows setting a default open_timeout for all HTTP calls in seconds.
#options(path, options = {}, &block) ⇒ Object
Perform an OPTIONS request to a path.
#parser(custom_parser = nil) ⇒ Object
Allows setting a custom parser for the response.
#patch(path, options = {}, &block) ⇒ Object
Perform a PATCH request to a path.
#pem(pem_contents, password = nil) ⇒ Object
Allows setting a PEM file to be used.
#pkcs12(p12_contents, password) ⇒ Object
Allows setting a PKCS12 file to be used.
#post(path, options = {}, &block) ⇒ Object
Allows making a post request to a url.
#put(path, options = {}, &block) ⇒ Object
Perform a PUT request to a path.
#query_string_normalizer(normalizer) {|Hash, String| ... } ⇒ Object
Override the way query strings are normalized.
#raise_on(codes = []) ⇒ Object
Raises HTTParty::ResponseError if response's code matches this statuses.
#read_timeout(t) ⇒ Object
Allows setting a default read_timeout for all HTTP calls in seconds.
#resend_on_redirect(value = true) ⇒ Object
Declare that you wish to resend the full HTTP request across redirects, even on redirects that should logically become GET requests.
#ssl_ca_file(path) ⇒ Object
Allows setting an OpenSSL certificate authority file.
#ssl_ca_path(path) ⇒ Object
Allows setting an OpenSSL certificate authority path (directory).
#ssl_version(version) ⇒ Object
Allows setting of SSL version to use.
#uri_adapter(uri_adapter) ⇒ Object
Allows setting a custom URI adapter.