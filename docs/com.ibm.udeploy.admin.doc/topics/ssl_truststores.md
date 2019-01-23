# Implementing custom trust stores

A trust store defines the roots of the certificate trust chain. Typically, these are the certificate authority root certificates that sign other certificates. It can also be end entity certificates that are directly trusted. Java® includes a default trust store that contains certificate authority root certificates for many well-known authorities. This trust store is a file called cacerts and is contained in the Java installation. The file has the same format as a keystore, but it never contains a private key. It is possible to modify or replace this file to alter the trust roots with the keytool program. Otherwise, a custom trust store must be used instead.

A custom trust store is simply another keystore file containing the custom trust roots. It is even possible to copy cacerts and modify the copy to expand the set of trust roots. Unlike with the default trust store, a configuration step is required enable use of a custom trust store.

You can turn on custom trust stores selectively. For example, you can configure agents to always verify the server without the server doing any verification, or you can have the servers verify each other only in the client role.

**Note:** Trust stores can be used with agents and servers, but not agent relays. The agent relay has no custom trust store support for web agent communication because it does not participate in authenticating communications.

## Agent

For web agent communication, the agent permits a custom trust store for validating connections to the server. For the custom trust store to take effect, verify.server.identity must be set to true. This parameter can be configured in the installer \([Agent installation properties](../../com.ibm.udeploy.install.doc/topics/agent_properties.md)\), although it can also be set without configuring a custom trust store.

By default, setting this property will use the default trust store in the cacerts file. It also performs an extra hostname verification on the server certificate, which is the same as in a web browser.

A custom trust store is configured by setting agentcomm.truststore to the path of trust store file and setting agentcomm.truststore.password to the keystore file password. If unset, it will default to changeit.

```
installed.properties:
  verify.server.identity=true
  agentcomm.truststore=<path>
  agentcomm.truststore.password=<password>
```

## Server

The server's use of a trust store is similar to the agent, but has potentially two custom trust stores, depending on the role of the server in the connection. The trust stores are independent and can be selectively enabled, or both can be configured to share the same trust store file.

**Server: Server Role**

When the server is in the server role, it will authenticate clients, which are both agents and other servers in the same cluster. In this scenario, verify.client.identity must be set to true.

The default cacerts trust store is used. There is no hostname verification step because client certificates do not contain a hostname. agentcomm.serverTruststore is set to the path of the trust store file. agentcomm.serverTruststore.password is set to the trust store file password \(changeit by default\). Unlike the agent, the password property is stored in secured-installed.properties with other passwords.

**Note:** Although the trust store is configured for the server role, that server verifies the identity of clients. This explains the asymmetry in the names of this group of properties. When the server is in the client role, the naming is reversed.

```
installed.properties:
  verify.client.identity=true
  agentcomm.serverTruststore=<path>

secured-installed.properties
  agentcomm.serverTruststore.password=<password>
```

**Server: Client Role**

When the server is the client role, it is only verifying the identity of the other server members of its cluster. In this scenario, verify.server.identity must be set to true.

The default cacerts trust store is used. As required by the client role, a hostname verification step is also performed. agentcomm.serverTruststore is set to the path of the trust store file. agentcomm.serverTruststore.password is set to the trust store file password \(changeit by default\).

```
installed.properties:
  verify.server.identity=true
  agentcomm.clientTruststore=<path>

secured-installed.properties
  agentcomm.clientTruststore.password=<password>
```

**Parent topic:** [SSL configuration](../../com.ibm.udeploy.doc/topics/SSLinstall.md)

