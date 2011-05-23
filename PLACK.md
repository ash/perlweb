# Upgrade notes from Apache to Plack version

* request->uri now returns a URI object with some extra code to have
  it emulate the old behavior of just returning the path when
  stringified.

* There's no more Combust::Control::Error module

* proxyip_forwarders are not "chained"; only the most recent header is
read.  Plack::Middleware::ReverseProxy would have to be changed to fix
that.

* When using proxyip_forwarders, X-Forwarded-Server, X-Forwarded-Host,
X-Forwarded-Port, X-Forwarded-HTTPS and X-Forwarded-Proto headers are
also supported.
