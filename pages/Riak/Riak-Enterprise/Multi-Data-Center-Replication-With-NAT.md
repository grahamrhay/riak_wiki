<div class="info"><div class="title">Riak Enterprise Only</div>This documentation applies only to Riak Enterprise, Basho's commercial extension to <a href="http://wiki.basho.com/Riak.html">Riak</a>. To learn more about the differences between Riak and Riak Enterprise, <a href="http://basho.com/products/riak-overview/">read here</a>.  To talk to us about using Riak Enterprise,  <a href="http://info.basho.com/Wiki_Contact.html" target="_blank">let us know</a>.</div>

<div class="note"><div class="title">This feature is available in Riak Enterprise 1.2+</div></div>

Riak Enterprise now supports replication of data on networks that use static NAT.

This can be used for replicating data over the internet where servers have both internal and public IP addresses (see [[Riak REPL SSL|Multi Data Center Replication SSL]] if you replicate data over a public network).

### Requirements:
In order for Replication to work on a server configured with NAT, the NAT addresses must be configured statically.

### Example

Server A is the source of replicated data.

Servers B and C would like to be clients of the replicated data.

Server A is setup with static NAT, configured for IP addresses:

  * `192.168.1.10` (internal) and `50.16.238.123` (public)

Server A replication will listen on:

  * the internal IP address `192.168.1.10`, port 9010
  * the public IP address `50.16.238.123`, port 9011


Server B is setup with a single public IP address: `50.16.238.200`

  * Server B replication will connect as a client to the public IP address 50.16.238.123, port 9011


Server C is setup with a single internal IP address: `192.168.1.20`

  * Server C replication will connect as a client to the internal IP address of 192.168.1.10, port 9010

Configure a listener on Server A:

```
riak-repl add-nat-listener riak@192.168.1.10 192.168.1.10 9010 50.16.238.123 9011
```

Configure a site (client) on Server B

```
riak-repl add-site 50.16.238.123 9011 server_a_to_b
```

Configure a site (client) on Server C

```
riak-repl add-site 192.168.1.10 9010 server_a_to_c
```
