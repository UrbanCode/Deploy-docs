# Environment inventory and compliance

The inventory for an environment lists the component versions that are intended to be deployed to that environment. Compliance shows whether the environment contains those component versions.

The inventory and compliance for an environment are updated each time that you run an application process or deploy a snapshot to the environment. For example, assume that you run an application process that deploys two component versions to an environment. Regardless of whether the application process completes successfully, the environment inventory shows that the two component versions are deployed. The compliance shows how many of the components are installed successfully. In this way, the inventory shows the intended state of a resource or environment, while the compliance shows how closely the resource or environment matches the intended state. By reviewing the difference between the environment inventory and compliance, you can determine whether another deployment is necessary to bring an environment into compliance.

The environment inventory and compliance track components but not snapshots or applications. For example, if you successfully deploy a snapshot with two component versions, the inventory is two components and the compliance is two components. If you successfully deploy a different snapshot with versions of two different components, the inventory is four components and the compliance is four components. In this way, the server counts component versions for inventory and compliance, not the versions in a snapshot or applications.

-   **[Managing environment inventory and compliance](../topics/inventory_manage_app.md)**  
You can allow the server to manage the environment inventory and compliance automatically, or you can manage the environment inventory and compliance with steps in an application process.

**Parent topic:** [Inventories](../topics/inventory_ch.md)

