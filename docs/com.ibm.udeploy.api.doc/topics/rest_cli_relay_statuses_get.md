# Returns a JSONObject with count of agent relays to status. Expected format: \{ "ONLINE":4, "OFFLINE":1, \} Requires Settings Tab permission.

## Request

```
GET https://{hostname}:{port}
    /cli/relay/statuses
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getRelayStatuses](udclient_getrelaystatuses.md).

**Parent topic:** [relay resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_relay.md)

