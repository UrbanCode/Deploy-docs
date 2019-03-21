# Uninstalling components with an application process

You can uninstall components by using an Uninstall Component step in an application process.

-   Create an uninstall-type component process for each component version to remove. This process is run by the Uninstall Component step in an application process.
-   If you intend to uninstall the component as part of a rollback process, create an application snapshot that contains the component versions to restore.

There are several ways to uninstall a component. To replace an existing component version, you can install another version over it by running an application process that contains a deployment process for the component. To remove a component version, you run an application process that includes the Uninstall Component step.

1.  To uninstall a component version, complete these steps:
2.   Create an application process that contains the Uninstall Component step. 
3.   In the Uninstall Component step, select the component to remove and the uninstall-type component process that is defined for it. 
4.   In the **Uninstall Type** field, specify **All Existing** to remove all versions of the component from the environment's inventory. Otherwise, specify **All Selected For Process** to remove only the versions that you select when you run the application process. 
5.   Run the application process. The selected component versions are no longer in the environment inventory.

