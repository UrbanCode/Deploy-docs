# Introduction to releases and pipelines {#cr_release_ov .concept}

A release represents the delivery of multiple application through one or more phases of a lifecycle. A typical release includes many deployments to test environments and a small number of highly orchestrated deployments to staging and production. Release managers can define milestones that lead up to the release, as well as a plan to deliver participating applications to each phase of the lifecycle.

Releases can represent all kinds of events, from major events in the life of your company to comparatively minor events, like recurring maintenance. You assign the applications, which are business-meaningful pieces of a system or software that can be independently deployed, to the release. You create deployment plans, which define the tasks that must be completed when a deployment runs, for your release.

Pipelines automate releases. Pipeline stages organize input and jobs as your code is built, deployed, and tested. Stages accept input from either source control repositories \(SCM\) or other external applications, such as UrbanCode Deploy. Stages and jobs run serially; they enable flow control for your work.

**Parent topic:** [Overview](../topics/c_node_overview.md)

