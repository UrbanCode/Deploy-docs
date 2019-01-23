# Troubleshooting Heat-engine plug-in extensions

Installing the Blueprint Designer Heat extension plug-ins into an IBM Cloud Manager Heat engine results in stopping SSL communication.

When you install the Blueprint Designer Heat orchestration extension plug-ins into IBM Cloud Manager with OpenStack and HTTPS is enabled on Keystone and Heat API endpoints, the following two types of error occur:

1.  ```
keystoneclient.exceptions.SSLError: SSL exception connecting to https://{keystone Identity Endpoint}/auth/tokens: [SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed
```

2.  ```
heatclient.exc.HTTPUnauthorized: ERROR: Authentication required.
```


**Note:** If HTTPS not enabled on Keystone and HEAT API endpoints of IBM Cloud Manager, which is the default configuration, the problem does not occur.

When you install the Blueprint Designer Heat extension plug-ins, the installation deploys new Python module versions through Pip. The new Python module versions change the Python request module in the IBM Cloud Manager controller environment so that the Heat client is prevented from communicating over SSL.

To continue HTTPS communications on the Keystone and Heat API endpoints of IBM Cloud Manager, install the Python request module:

```
yum reinstall python-requests-{version}.noarch
```

If you use your own CA certificate, import it again. The default location of the certificate for IBM Cloud Manager 4.3 is /etc/pki/tls/certs/ca-bundle.crt.

**Parent topic:** [Troubleshooting engines](../../com.ibm.edt.doc/topics/trouble_engines.md)

