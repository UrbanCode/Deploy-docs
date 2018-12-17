# Mixed mode licensing

Mixed Mode Licensing gives you the ability to use both Authorized Agent licenses and Floating licenses on the same UrbanCode instance for greater flexibility.

## Automatic agent license type

-   Go to **Settings \> System Settings**, under the new Licensing field it displays the current server license mode.
-   To enable **Automatic Agent License Type** click on drop down box which lists valid license types that you can set for the current server license mode. This will automatically set new agent license type to the specified type when they come online.

## Set license type

-   Agent license types are displayed on the Agents page, **Resources \> Agents**.
-   Select agents that you want to set license type for then under **Actions** scroll down and click on **Set License Type**.
-   You can set the license type of one or more agents at a time.
-   Only valid license types for the current server license mode are listed.

## Agent license types

1.  Authorized - agents use the Authorized Agent License.
2.  Floating - agents use Floating Agent \(Simultaneous Session\) licenses.
3.  RDT - agents are z/OS development agents and do not require a license. The RDT license type is automatically set when the server detects the zOS-RDT property on the agent. A RDT agent cannot change their type from RDT.
4.  Unlicensed - agents have no license and cannot be used in deployments.

## Server licensing modes

1.  PVU – Requires a Server PVU license. Any number of agents connected to a PVU licensed server may have the "PVU-Agent" license type, except for RDT agents – those will always be licensed. It is the responsibility of the user to not exceed any usage limitations they have from their licensing agreement with IBM. Additional information about PVU licensing may be found [here](https://www-03.ibm.com/software/sla/sladb.nsf/lilookup/627F88E77EC9516E8525829E0072B8AE?OpenDocument#ibm-top).
2.  Mixed – Requires an Authorized Server License. "Mixed" means we support Authorized and Floating agents simultaneously.
3.  Floating – requires that the Rational License Key Server \(RLKS\) has a Floating Agent Feature. It only allows agents licensed with Floating licenses to be used.
4.  Unlicensed – there are no valid server licenses \(or floating agent licenses\) in the license server and the server is running on a platform that supports the license library. Unlicensed servers cannot run deployments outside of the trial period.
5.  Unavailable - the server is running on a system which does not support licensing, such as zLinux.

UrbanCode Deploy is configured with a finite number of Server Agent licenses for an organization. When the maximum number of licenses are in use, any additional agents configured will become unlicensed and cannot run processes. Any processes that are running on an unlicensed agent will log an error message. To resolve licensing warnings, additional licenses must be obtained, or existing licenses must be reassigned among the agents.

## Agent license types usable by servers with server license mode

Only certain agent license types are available to be set on an agent depending on the server license mode. These are laid out in the following table:

|Server Mode|Authorized Agent|Floating Agent|PVU-Agent|RDT|Unlicensed|
|-----------|----------------|--------------|---------|---|----------|
|PVU Server|NO|NO|YES|YES|YES|
|Floating Server|NO|YES|NO|YES|YES|
|Mixed Mode|YES|YES|NO|YES|YES|
|Unlicensed|NO|NO|NO|NO|YES|
|Unavailable|YES|YES|YES|YES|YES|

## Valid agent license types for specific server licensing mode

The Server License Mode will dictate which agents are allowed to run processes depending on what license type the agent has assigned to it.

|Server Mode|Authorized Agent|Floating Agent|PVU-Agent|RDT|Unlicensed|
|-----------|----------------|--------------|---------|---|----------|
|PVU Server|NO|NO|YES|YES|NO|
|Floating Server|NO|YES|NO|YES|NO|
|Mixed Mode|YES|YES|NO|YES|NO|
|Unlicensed|NO|NO|NO|NO|NO|
|Unavailable|YES|YES|YES|YES|YES|

## Server licensing

-   When a server starts it communicates with the IBM Rational Common Licensing \(RCL\) server, and the server's license mode will be set.
-   Updating the server licensing mode does not change the license type of any existing agents, instead, the server will restrict agents with an unsupported license type from running deployments.
-   If the server is on a platform that supports the licensing library, and if no licenses are available to the server, the server mode will remain unlicensed.
-   The server will attempt to checkout server licenses in the following order of priority:
    -   Authorized Server License
    -   PVU License

-   The server will set the license mode on startup based on the server license it checked out. If there are no server licenses but there exists a floating agent license, the server license mode will be set to Floating.
-   If the license library is unsupported \(for example, on zLinux or powerLE machines\) then the server licensing mode will be set to Unavailable and all agent license types are allowed to be used / set.
-   If a server is in Mixed Mode and the Rational License Key Server \(RLKS\) does not support Floating licenses, then a display message in the UI will state that there are no floating licenses loaded in the license server.

|Authorized|PVU|Agent Floating|Server License Mode|
|----------|---|--------------|-------------------|
|x|x|x|Mixed|
|x|x| |Mixed|
|x| |x|Mixed|
|x| | |Mixed|
| |x|x|PVU|
| |x| |PVU|
| | |x|Floating|
| | | |Unlicensed|

## Server licensing in HA \(high availability\)

-   The server license mode is stored such that each server in the cluster can reference the current license mode.
-   Each server will checkout licenses, they use a clustering ID to allow all servers in the cluster to consume the same license.
-   If a server cluster attempts to checkout a license that is already checked out from another server cluster – it will fail, and the servers will be Unlicensed.
-   The first server online in a cluster will determine the server licensing mode and propagate that information to the other servers in the cluster.
-   When a server is started, if the server:

    ```
    is in HA:
              n = countAuthAgents() 
              CheckoutLicenses(Auth, n) 
          else:
              mark all agents offline 
              Set all floating agents “licensed” column to false 
              True-up other agents based on license type (ensure RDT agents are licensed, etc) 
    ```


## Server evaluation mode

-   The UCD Server Evaluation Mode is available for sixty days.
-   While in evaluation mode, neither the server or agent are licensed.
-   Licenses are not required to run deployments during the evaluation period.
-   After the evaluation period concludes the server licensing mode will be set to Unlicensed.
-   After a connection to the IBM Rational License Key Server \(RLKS\) has been establish the evaluation period will end, and the server will set its license mode.

## Agent licensing

-   Agents require a license type to be specified.
-   All deployments using an unlicensed agent will fail with an error message.
-   When an agent's license type is changed the currently held license will be returned to the license server.
-   You will need an "edit license type" permission to successfully change the agent's license type.
-   Authorized licenses are acquired as soon as the agent's license type is set.
-   When a process is run on an agent with the Floating license type, the server will attempt to checkout a floating license. When that process concludes the floating license will be checked back into the license server.
    -   Agents will not fail if a floating license cannot be checked out at time of deployment, but a warning will be written to the server log.
-   Changing the license type of an agent while it is being used will have an undefined effect on any processes using that agent which are currently in progress.

**Parent topic:** [License management](../topics/licenseManage.md)

