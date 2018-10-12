# Connecting the blueprint design server to the server {#ucdp_integrate .task}

In most cases, you connect the blueprint design server to the server at installation time, but you can also connect them later.

-   Install the server and blueprint design server, and obtain an engine.
-   On the server, create a token.
-   Download the installation files for the agent components. These files are available for download from the IBM® Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html).

1.   Connect the server to the blueprint design server: 
    1.   On the server, click **Settings** \> **Blueprint Designer Integrations**. 
    2.   Click **New Blueprint Designer Integration**. 
    3.   Specify a name for the connection to the blueprint design server. 
    4.   In the **URL** field, specify the complete URL to the blueprint design server, such as `http://blueprint_design_server.example.com:8080/landscaper`. 
    5.   Select the **Authentication Method**. 
        -   To require each user to authenticate to the blueprint design server, select **Automatically authenticate for each UrbanCode Deploy user.** On the blueprint designer, you must create an authentication realm for this UrbanCode Deploy server. See [Importing user accounts from IBM UrbanCode Deploy to the blueprint design server](../../com.ibm.udeploy.admin.doc/topics/security_realms_ucd.md#).
        -   To use only one set of blueprint designer credentials, select **Always authenticate with one blueprint designer username.** Ensure that blueprint designer user name that you enter has permissions to access the cloud platforms where you provision cloud environments. Specify the blueprint design server user name and password to use to connect. The server has access to only the blueprints that this user name has access to.
    6.   Click **Save**. 
2.   Connect the blueprint design server to the server: 
    1.   In the blueprint designer, click **Settings** \> **System Settings**. 
    2.   In the **UrbanCode Server URL** field, specify the complete URL of the IBM UrbanCode Deploy server, such as `https://ucdserver.example.com:8443`. 
    3.   With an IBM UrbanCode Deploy server account that has access to the components, authenticate with either a token or a user name and password: 

        -   To specify a token, set **Token Based Authentication** to **On**. On the server, generate a token by clicking **Settings** \> **Tokens** and then clicking **Create Token**. In the blueprint designer System Settings window, specify the token value in the **Token** field.
        -   To specify a user name and password, set **Token Based Authentication** to **Off**. In the **Username** and **Password** fields, enter the IBM UrbanCode Deploy server user name and password.
        **Note:** When a user edits a blueprint, that user can see the components that are associated with this token or user name. To restrict access to components, import user accounts from the IBM UrbanCode Deploy server; see [Importing user accounts from IBM UrbanCode Deploy to the blueprint design server](../../com.ibm.udeploy.admin.doc/topics/security_realms_ucd.md).

    4.   Click **Save**. 
3.   From a Linux™ or Windows™ computer, install the agent components on the server. These components are included automatically in deployments that require agents.
    1.   Extract the installation files for the blueprint design server and the agent components. 
    2.   Set the system JAVA\_HOME variable to a JRE. For example, you can set the system JRE to the JRE that is provided in the blueprint design server installation files. To temporarily set the JRE on a Linux computer, use the following command:

        ```
        export JAVA_HOME=installation\_directory/ibm-ucd-patterns-install/web-install/media/server/java/jre
        ```

        For `installation\_directory`, use the location of the blueprint design server installation files.

    3.   From the command line, change to the installation\_directory/ibm-ucd-patterns-install/agent-package-install/ folder, and run the installation program: 

        -   On a Linux computer, change to the directory where you extracted the agent components and run the following command:

            ```
            ./install-agent-packages.sh -s ucd\_url -a token
            ```

            -   ucd\_url is the full URL of the IBM UrbanCode Deploy server, such as `https://deployserver.example.org:8443`
            -   token is a token from the server
        -   On a Windows computer, change to the directory where you extracted the agent components and run the following command:

            ```
            .\install-agent-packages.ps1 -s ucd\_url -a token
            ```

            -   ucd\_url is the full URL of the IBM UrbanCode Deploy server, such as `https://deployserver.example.org:8443`
            -   token is a token from the server
        **Note:** If you are using Windows server, you must run the command from PowerShell.

    4.   On the IBM UrbanCode Deploy server, verify that the agent components were created. The names of the components are `ucd-agent-linux-ppc64`, `ucd-agent-linux-x86_64`, `ucd-agent-win-x86_64`, and `ucd-agent-linux-s390x`.
    5.   On the IBM UrbanCode Deploy server, add these components to any teams that provision environments from the blueprint designer. Users must have access to these components to provision environments from the blueprint designer.
4.   To test the connection between the server and the blueprint design server, install the sample application and ensure that you can access it from the blueprint designer: 

    1.   Set the system JAVA\_HOME variable to a JRE. For example, you can set the system JRE to the JRE that is provided in the blueprint design server installation files. To temporarily set the JRE on a Linux computer, use the following command:

        ```
        export JAVA_HOME=installation\_directory/ibm-ucd-patterns-install/web-install/media/server/java/jre
        ```

        For `installation\_directory`, use the location of the blueprint design server installation files.

    2.   From the command line, change to the installation\_directory/ibm-ucd-patterns-install/agent-package-install/ folder, and run the installation program: 

        -   On a Linux computer, change to the directory where you extracted the agent components and run the following command:

            ```
            ./install-ucd-blueprint-designer-test-app.sh -s ucd\_url -a token
            ```

            -   ucd\_url is the full URL of the IBM UrbanCode Deploy server, such as `https://deployserver.example.org:8443`
            -   token is a token from the server
        -   On a Windows computer, change to the directory where you extracted the agent components and run the following command:

            ```
            .\install-ucd-blueprint-designer-test-app.ps1 -s ucd\_url -a token
            ```

            -   ucd\_url is the full URL of the IBM UrbanCode Deploy server, such as `https://deployserver.example.org:8443`
            -   token is a token from the server
        **Note:** If you are using Windows server, you must run the command from PowerShell.

    3.   On the IBM UrbanCode Deploy server, verify that the sample component and application were created. The component is named `ucd_blueprint_designer_test` and the application is named `ucd_blueprint_designer_test_app`.
    4.   Log in to the blueprint designer. 
    5.   Create a blueprint. 
    6.   From the **Images** drawer of the palette, add a `Referenced Image` resource to the blueprint. 
    7.   From the **Components** drawer, drag the `ucd_blueprint_designer_test` component to the `Referenced Image` resource. 
    8.   From the Choose UCD Application window, select the check box next to the `ucd_blueprint_designer_test_app` application, click **OK**, and click **OK** again. 
    The component shows a warning that says `MISSING` because it has no versions. Other than that warning, if you can add the component in this way, the blueprint designer is connected to the IBM UrbanCode Deploy server.


**Parent topic:** [Installing the blueprint design server](../../com.ibm.edt.doc/topics/install_server_bds.md)

