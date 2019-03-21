# Snapshots

A snapshot is a collection of specific versions of components and processes. Typically, a snapshot represents a set of component versions that are known to work together. In most cases, snapshots include all of the components in an application.

A snapshot is typically created when a successful deployment runs in an uncontrolled environment, where there are no approval gates. Snapshots can be created in controlled environments too. When a snapshot is created, a picture of the application's current state is captured. As the application components move from one environment to another, HCL® UrbanCode™ Deploy ensures that the exact versions and processes that you selected are used in each environment.

Snapshots can help manage complex deployments, which have multiple environments and development teams. For example, after you test and confirm that team A's component works with team B's component, you can create a snapshot. Then, as development progresses, you can create more snapshots to model the effort and drive the entire deployment, coordinating versions, configurations, and processes.

