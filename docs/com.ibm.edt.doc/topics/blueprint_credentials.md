# Providing cloud credentials in a blueprint

By default, when you provision an environment from a blueprint, the environment is created by using the cloud account information of its cloud project. However, when you create a blueprint for most kinds of clouds, you can specify different user credentials.

Create a blueprint for your cloud project. See [Creating files with the blueprint designer](blueprint_edit.md).

You store credentials for each cloud project. If you modify the properties in a blueprint's source code, you can provide different credentials that are used to create individual environments.

**Note:** You cannot specify different user credentials for OpenStack clouds or for Microsoft™ Azure.

1.   Obtain the credentials for the cloud account to use with your environment. 
2.   To edit a blueprint's source code, click **Blueprints**, select your blueprint's name, and click **Source.** 
3.   In the parameters section of the blueprint source code, enter the appropriate properties and credentials for your cloud type: 
    -   For Amazon Elastic Compute Cloud, enter these lines:

        ```
        IBM::AWS::Access_ID:
          type: string
          description:AWS ID
          default: 'your\_id'
        IBM::AWS::Secret_Key:
          type:string
          description: AWS key
        default: 'your\_secret\_key'
        ```

    -   For SoftLayer® clouds, enter these lines:

        ```
        IBM::SoftLayer::User:
          type: string
          description: SoftLayer ID
          default: 'your\_id'
        IBM::SoftLayer::API_Key:
          type: string
          description: SoftLayer key
          default: 'your\_api\_key'
        ```

    -   For VMware, enter these lines:

        ```
          IBM::VMWare::User:
          type: string
          description: VMware User
          default: 'your\_user\_name'
        IBM::VMWare::Password:
          type: string
          description: VMware password
          default: 'your\_password'
        ```

4.   Click **Save**. 

Provision an environment by using your blueprint. See [Provisioning cloud environments](env_provision_ov.md).

**Parent topic:** [Modeling environments for clouds through OpenStack Heat](../../com.ibm.edt.doc/topics/blueprint_edit_clouds.md)

