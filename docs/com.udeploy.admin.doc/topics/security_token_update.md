---
keyword: agent relay
---

# Updating the agent relay authentication token password

The authentication token password for the agent relay is specified during installation of the agent relay. You can update the authentication token and provide a password for the token by updating the agent relay properties file.

The new authentication token for the server must be available before changing the password. For information about creating a token, see [Tokens](security_token.md).

1.   Open the agentrelay.properties file located in agent\_relay\_home/conf directory. 
2.   Change the value for the **agentrelay.codestation.server\_password** property to the new password value. The following is from the sample agentrelay.properties file. The password shown is encrypted.

    ```
    agentrelay.codestation.server_password=pbe{UlfTbYJYm2i7VIN4D0/8dYeqI6T54heliAURNECl0p4l8/3h72Fv2n3G3yylWwdCnRY57wXcLT8=}
    ```

    Specify the new password. The new password is encrypted when the agent relay is started.

    ```
    agentrelay.codestation.server_password=new\_password
    ```

3.   Save your changes and close the file. 
4.   Stop the agent relay. 
5.   Start agent relay . 
6.   Verify that the agents connected through the changed agent relay are connecting. 

**Parent topic:** [Tokens](../../com.udeploy.admin.doc/topics/security_token.md)

