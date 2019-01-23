# **HCL UrbanCode Deploy Terraform provisioner**

The HCL® UrbanCode™ Deploy provisioner installs an HCL UrbanCode Deploy agent on a virtual machine that is created by a Terraform configuration.

## Argument reference

|Name|Required|Description|
|----|--------|-----------|
|agent\_name|True|The agent name.|
|agent\_package\_version|False|The agent package component version to install. The default is version 7.1.|
|agent\_team|False|The agent team.|
|agent\_relay\_url|False|The agent relay URL when using an agent relay.|
|jms\_port|False|The JMS port used by the agent for communication to the HCL UrbanCode Deploy server. If connecting through an agent relay, the default is 7916. If connecting directly to the HCL UrbanCode Deploy server, the default is 7918.|
|os\_type|False|The operating system that the agent will be installed on. Specify either Linux or Windows. The default is Linux.|
|ucd\_proxy\_port|False|The HCL UrbanCode Deploy server proxy port. The default is 20080.|
|ucd\_server\_url|True|The HCL UrbanCode Deploy server URL.|
|username|True|The HCL UrbanCode Deploy user name.|
|password|True|The HCL UrbanCode Deploy password.|

**Example usage**

```
resource "aws_instance" "server" {
     connection {
         user = "ubuntu"
         private_key = "${file("./keys/private_key")}"
     }

     provisioner "ucd" {
         agent_name      = "server-agent"
         ucd_server_url  = "https://ucd-server.raleigh.ibm.com:8443"
         ucd_user        = "admin"
         ucd_password    = "admin_password"
     }

     instance_type = "t2.micro"
     ami = "ami-13be557e"
 }
```

**Parent topic:** [Terraform](../../com.ibm.udeploy.reference.doc/topics/terraform_ch.md)

