# Enabling the DevOps library {#enable_devops_library .task}

To manage DevOps assets in IBM® Rational® Asset Manager, you enable the DevOps library. The DevOps library is collection of asset types and relationships.

To enable the DevOps library, you must be a repository administrator.

1.  On the Rational Asset Manager web client home page, log on with an account that has master administrative permissions for the repository.
2.  Click **Administration**.
3.  On the sidebar, click **Libraries**. 

    **Important:** If the DevOps library is already enabled on the Rational Asset Manager server, you cannot import the library again. Continue to the next step.

    If the DevOps library was imported but not enabled, in the list of libraries, click the version number of the DevOps library. Then, continue to step [7](enable_devops_library_tsk.md#catadmin_11_enable)

4.  Click **Import Existing Library**. The Import Library window opens.
5.  Select **Select a built-in library**, and then select **DevOps** from the list. 
6.  Click **OK**.
7.  Confirm that the information in the DevOps library does not conflict with assets or metadata that are in the repository or that are controlled by other libraries on the page for the DevOps library. Then, in the Library Actions sidebar, click **Enable**.The assets, asset types, and asset attributes for the DevOps library are enabled on your repository.
8.  Click **Administration** to return to the list of communities in the repository.

After you activate the library, the DevOps search view is available in Rational Asset Manager.

**Parent topic:** [Integrating with IBM Rational Asset Manager](../topics/ramintegrat_cpt.md)

