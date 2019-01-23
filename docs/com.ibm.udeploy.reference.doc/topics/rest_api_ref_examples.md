# Examples of REST API commands

Many REST and command-line client commands have examples in their help topics. A few more examples using various programming languages and scenarios are provided here. The commands are similar for the server and for the blueprint design server.

## Complete scenarios

For complete examples of using several REST commands together, see the following pages:

-   [Deploying applications by using REST commands: An example](rest_api_ref_example.md)
-   [Provisioning environments by using REST commands: An example](rest_api_ref_provision_example.md)

## Authentication

To run commands, you must first authenticate to the server. See [Authenticating for REST commands](rest_api_ref_authenticating.md).

## Running REST commands in process steps

Plug-ins contain many steps that do the same tasks as REST API commands, but if you want to run a REST command as part of a process, one way to do so is to use the Send HTTP Call step in the Web Utilities plugin. To use the REST API with this step, add the step to a process and specify the following information:

-   **Name**

    Specify a name for the step.

-   **URL**

    Specify the complete URL of the command. For example, to use the command [Get information about all applications on the server](../../com.ibm.udeploy.api.doc/topics/rest_cli_application_get.md), specify the URL `https://ucd-server.example.com:8443/cli/application`, using the host name or IP address of your server for `ucd-server.example.com`.

-   **HTTP Method**

    Specify the method for the command, such as GET or PUT. For the method to use, see the documentation for the command.

-   **Headers**

    Specify any headers for the command, separated by line breaks. If the command requires headers, the headers are listed in the documentation for the command. For example, if you are sending JSON data along with the command, add the following header:

    ```
    Content-Type: application/json
    ```

    The step automatically includes the headers Content-Length, Content-Type, Accept, and Connection. You can override each of these headers by specifying them in the **Headers** field except for the Content-Length header. The Accept & Content-Type headers are set by the value in the Request Content Type field, but you can still override these headers in the **Headers** field.

-   **Data / Data File**

    Specify the data payload to send along with the command or a file that contains the data.

-   **Request Content Type**

    Select the content type of the data. This field sets the value of the Accept and Content-Type headers.

-   **Allow Untrusted SSL Certs**

    Select the check box to ignore untrusted certifications, such as self-signed certificates.

-   **Username**

    Specify the user name with which to run the command. Running a command with the REST API requires the same permissions as using the web interface.

-   **Password**

    Specify the password with which to run the command.

-   **Output file**

    Optionally, specify a file name to store the result of the command.


## Running REST commands in the command-line interface

The Linux™ program curl is one of many programs that can run REST commands from the command line. For an example, see [Running REST commands](rest_api_ref_using.md).

## Running REST commands in Java™

For an example of running REST commands in Java, see [Authenticating for REST commands](rest_api_ref_authenticating.md).

## Running REST commands in Python

For an example of running REST commands in Python, see [Authenticating for REST commands](rest_api_ref_authenticating.md).

## Running REST commands in a Groovy script

For an example of running REST commands in a Groovy script, see the following page: [https://github.com/IBM-UrbanCode/groovy-sample-scripts-UCD](https://github.com/IBM-UrbanCode/groovy-sample-scripts-UCD)

**Parent topic:** [REST API reference](../../com.ibm.udeploy.reference.doc/topics/rest_api_ref_overview.md)

