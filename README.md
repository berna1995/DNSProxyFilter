# DNS Proxy Filter

Just a simple DNS proxy with filtering capabilities implemented in Java.

To build it just:

```console
$ ./gradlew build
```

At this point you can will find the generate jar file under */build/libs*.

To execute the proxy just:

```console
$ java -jar DNSProxyFilter.jar
```
This will just spawn a DNS proxy server on port 53 and forward all queries to Google DNS.

To filter queries you can create a file to pass to the program, for example you can create a file called *domainstofilter.txt* formatted like so:

```
*.google.it
microsoft.com
```

To run the proxy and filter those domains out you can:

```console
$ java -jar DNSProxyFilter.jar -d domainstofilter.txt
```

And at this point you can check if it works just like that:

```console
$ host google.it 127.0.0.1
```

And you'll get **NXDOMAIN** as response.

For more details about the proxy capabilities:

```console
$ java -jar DNSProxyFilter.jar --help
```