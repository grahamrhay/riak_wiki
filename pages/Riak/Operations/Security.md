# Riak Security

## Riak

Riak is a powerful open-source distributed database focused on scaling predictably and easily, while remaining highly available in the face of server crashes, network partitions or other (inevitable) disasters.

## Commitment

Data security is an important and sensitive issue to many of our users. A real-world approach to security allows us to balance appropriate levels of security and related overhead while creating a fast, scalable, and operationally straightforward database.

### Balance

More layers of security always increases operational and administrative costs. Sometimes those costs are warranted, sometimes they are not. Our approach is to strike an appropriate balance between effort, cost and security.

### Continuous Improvement

Though we make every effort to thwart security vulnerabilities whenever possible (including through independent reviews), no system is completely secure. We will never claim that Riak is 100% secure (and you should seriously doubt anyone who claims their solution is). What we can promise is that we openly accept all vulnerabilities from the community. When appropriate, we'll publish and make every attempt to quickly address these concerns.

If you run across any security issues, we gladly accept all submissions. You can email us at
security@basho.com. If you would prefer to send a secure message, the security team's GPG is


## Network Configurations

[Network Security and Firewall Configurations](/Network-Security-and-Firewall-Configurations.html)

## Multi Data Center Replication

For those version of Riak that support Multi Data Center (MDC) Replication, you can configure Riak 1.2+ to communicate over SSL, to seemlessly encrypt the message traffic.