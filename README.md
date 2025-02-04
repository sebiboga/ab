# ab
Apache Bench
### SUMMARY
`ab` is a tool for benchmarking your Apache Hypertext Transfer Protocol (HTTP) server. It is designed to give you an impression of how your current Apache installation performs. This especially shows you how many requests per second your Apache installation is capable of serving.

### OPTIONS
- **-A auth-username:password**  
  Supply BASIC Authentication credentials to the server. The username and password are separated by a single `:` and sent on the wire base64 encoded. The string is sent regardless of whether the server needs it (i.e., has sent a 401 authentication needed).

- **-b windowsize**  
  Size of TCP send/receive buffer, in bytes.

- **-c concurrency**  
  Number of multiple requests to perform at a time. Default is one request at a time.

- **-C cookie-name=value**  
  Add a Cookie: line to the request. The argument is typically in the form of a name=value pair. This field is repeatable.

- **-d**  
  Do not display the "percentage served within XX [ms] table" (legacy support).

- **-e csv-file**  
  Write a Comma separated value (CSV) file which contains for each percentage (from 1% to 100%) the time (in milliseconds) it took to serve that percentage of the requests. This is usually more useful than the 'gnuplot' file; as the results are already 'binned'.

- **-f protocol**  
  Specify SSL/TLS protocol (SSL2, SSL3, TLS1, or ALL).

- **-g gnuplot-file**  
  Write all measured values out as a 'gnuplot' or TSV (Tab separate values) file. This file can easily be imported into packages like Gnuplot, IDL, Mathematica, Igor or even Excel. The labels are on the first line of the file.

- **-h**  
  Display usage information.

- **-H custom-header**  
  Append extra headers to the request. The argument is typically in the form of a valid header line, containing a colon-separated field-value pair (i.e., "Accept-Encoding: zip/zop;8bit").

- **-i**  
  Do HEAD requests instead of GET.

- **-k**  
  Enable the HTTP KeepAlive feature, i.e., perform multiple requests within one HTTP session. Default is no KeepAlive.

- **-n requests**  
  Number of requests to perform for the benchmarking session. The default is to just perform a single request which usually leads to non-representative benchmarking results.

- **-p POST-file**  
  File containing data to POST. Remember to also set -T.

- **-P proxy-auth-username:password**  
  Supply BASIC Authentication credentials to a proxy en-route. The username and password are separated by a single `:` and sent on the wire base64 encoded. The string is sent regardless of whether the proxy needs it (i.e., has sent a 407 proxy authentication needed).

- **-q**  
  When processing more than 150 requests, `ab` outputs a progress count on stderr every 10% or 100 requests or so. The `-q` flag will suppress these messages.

- **-r**  
  Don't exit on socket receive errors.

- **-s**  
  When compiled in (ab -h will show you), use the SSL protected https rather than the http protocol. This feature is experimental and very rudimentary. You probably do not want to use it.

- **-S**  
  Do not display the median and standard deviation values, nor display the warning/error messages when the average and median are more than one or two times the standard deviation apart. And default to the min/avg/max values (legacy support).

- **-t timelimit**  
  Maximum number of seconds to spend for benchmarking. This implies a -n 50000 internally. Use this to benchmark the server within a fixed total amount of time. Per default there is no timelimit.

- **-T content-type**  
  Content-type header to use for POST/PUT data, e.g., application/x-www-form-urlencoded. Default: text/plain.

- **-u PUT-file**  
  File containing data to PUT. Remember to also set -T.

- **-v verbosity**  
  Set verbosity level - 4 and above prints information on headers, 3 and above prints response codes (404, 200, etc.), 2 and above prints warnings and info.

- **-V**  
  Display version number and exit.

- **-w**  
  Print out results in HTML tables. Default table is two columns wide, with a white background.

- **-x <table>-attributes**  
  String to use as attributes for `<table>`. Attributes are inserted `<table here>`.

- **-X proxy[:port]**  
  Use a proxy server for the requests.

- **-y <tr>-attributes**  
  String to use as attributes for `<tr>`.

- **-z <td>-attributes**  
  String to use as attributes for `<td>`.

- **-Z ciphersuite**  
  Specify SSL/TLS cipher suite (See openssl ciphers).

### BUGS
There are various statically declared buffers of fixed length. Combined with the lazy parsing of the command line arguments, the response headers from the server and other external inputs, this might bite you.
