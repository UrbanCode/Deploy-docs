# Key terminology {#c_overview_terms .concept}

This topic included terms and concepts used within the UrbanCode Velocity environment.

 Activities
 :   Refer to item such as: releases, events, and deployment plans.

  Application
 :   Refers to the UrbanCode Deploy applications. Applications have processes, their steps usually start processes or modify resources. An application contains environments, which describe all the deployment locations that are needed in your deployment process, and you run application processes to deploy components to environments.

  Auto task
 :   Refers to task that start automatically as soon as they are eligible to run. Examples of auto task types include: UrbanCode Deploy, Continuous Delivery pipeline, email, and Slack.

  Dependent task
 :   A task that is dependent on another task to complete before it starts. The task that a dependent task waits for is called a prerequisite task. Dependent tasks cannot start until all its prerequisite tasks are resolved. Dependent tasks are used to ensure that tasks run in the expected order.

  Deployment
 :   The activities used to deliver a software project to a deployment target. Typically, you run deployments for each stage of your release lifecycle, ending with the production stage when the software becomes generally available. The activities that are performed during a deployment, called tasks, are defined in deployment plans. You start a deployment by starting one of the plan's eligible tasks. You complete a deployment by resolving all the tasks in the deployment plan.

  Duration
 :   The time a task takes to run. Duration is measured from the time a task starts until it is resolved. When you create some task types, you can estimate its expected duration. Duration is reported in minutes.

  Environment
 :   A collection of resources that identify the components that can be deployed by the parent application, along with the agents that do the work.

  Events
 :   Events are release-related activities that are applied to releases and tracked with the calendar. You can use events to organize your releases and other time-dependent activities, such as holidays and blackouts.

  Execution pattern
 :   Refers to the order in which tasks in a deployment plan become eligible to run. By default, a plan's execution pattern is sequential. Sequential tasks run in order beginning with the first task in the plan. You can combine tasks into groups and assign the parallel execution pattern to the group. Parallel tasks can run in any order and run simultaneously.

  Integration
 :   Refers to regularized communication between UrbanCode Velocity and external products and services. Communication with integrated products can be bidirectional.

  Process
 :   In UrbanCode Deploy, processes define automation activities, such as deploying components.

  Tag
 :   A label that you can apply to tasks or releases. When applied to tasks, tags can determine task applicability for a given deployment. When applied to releases, tags can be used to organize and filter releases.

  Task
 :   Represents a business-meaningful activity that has starting and ending points and a measurable duration. Durations are used to estimate deployment times. You add tasks to deployment plans. When you run a deployment, you complete the tasks in the plan

  Task group
 :   You can combine two or more tasks into a task group. When you form a group, you define the group's execution pattern, either sequential or parallel.

  Team
 :   A team is a collection of users and groups.

  Version
 :   Represents an UrbanCode Deploy application snapshot.

 **Parent topic:** [Overview](../topics/c_node_overview.md)

