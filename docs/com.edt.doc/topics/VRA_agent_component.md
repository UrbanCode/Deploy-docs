# Creating agent components in VMware vRealize Automation

After you configure the integration with VMware vRealize Automation Enterprise, you can create software components for HCL® UrbanCode™ Deploy agents.

You can import VMware vRealize Automation Enterprise catalog items into empty blueprints in the blueprint designer. To add HCL UrbanCode Deploy components to images in these catalog items without creating a new blueprint in vRealize automation, the image must contain a vRealize Automation software component for an HCL UrbanCode Deploy agent.

1.  To create vRealize Automation software components for the agent, complete the following steps:
2.   Extract the installation files for the agent components. 
3.   From the command line, change to the installation\_directory/ibm-ucd-patterns-install/agent-package-install/ folder, and run the installation program: 
    -   On a Linux™ computer, run the following command:

        ```
        ./create-ucd-windows-agent-swcomp-for-vra.ps1 
        -s <VRA\_SERVER\_URL> 
        -u <VRA\_USERNAME> 
        -p <VRA\_PASSWORD> 
        -t <VRA\_TENANT>
        ```

        This command is split onto separate lines for clarity, but it must be entered on a single line.

        -   VRA\_SERVER\_URL is the URL of the vRealize Automation server
        -   VRA\_USERNAME is a vRealize Automation user that is assigned a role with permission to create a software component, such as the Infrastructure Architect or Software Architect role.
        -    VRA\_PASSWORD is the password for that user.
        -   VRA\_TENANT is the tenant that can access the component.
        **Note:** The VRA\_SERVER\_URL and VRA\_TENANT values must match the values that were used to configure the vRealize Automation cloud project in the blueprint designer.

    -   On a Windows™ computer, run the following command:

        ```
        ./create-ucd-windows-agent-swcomp-for-vra.ps1 
        -s <VRA\_SERVER\_URL> 
        -u <VRA\_USERNAME> 
        -p <VRA\_PASSWORD> 
        -t <VRA\_TENANT>
        ```

        This command is split onto separate lines for clarity, but it must be entered on a single line.

        -   VRA\_SERVER\_URL is the URL of the vRealize Automation server
        -   VRA\_USERNAME is a vRealize Automation user that is assigned a role with permission to create a software component, such as the Infrastructure Architect or Software Architect role.
        -    VRA\_PASSWORD is the password for that user.
        -   VRA\_TENANT is the tenant that can access the component.
        **Note:** The VRA\_SERVER\_URL and VRA\_TENANT values must match the values that were used to configure the vRealize Automation cloud project in the blueprint designer.


Now you can create vRealize Automation blueprints that contain software components for the agents. Then, users can import catalog items that are based on the blueprint into the blueprint designer and add HCL UrbanCode Deploy components to images that contain an agent. They can provision these blueprints from the blueprint designer without modifying or creating assets in vRealize Automation.

**Parent topic:** [Connecting to VMware vRealize Automation v7 and v7.1](../../com.edt.doc/topics/cloud_connect_vra.md)

