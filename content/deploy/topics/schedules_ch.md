# Scheduling deployments {#schedulingDeployments.d12e2}

IBM® UrbanCode® Deploy has a built-in deployment scheduling system for setting regular deployments, or even black-out dates, for your Deployments.

Deployments for an individual application are scheduled on a per-environment basis, set when you run a deployment of a snapshot or deployment process. Black-out dates are set within the individual environments.

IBM UrbanCode Deploy stores all times relative to Coordinated Universal Time and displays them based on your time zone. A process that you schedule during Daylight Saving Time moves back an hour after Daylight Saving Time ends.

To set up a scheduled deployment, click **Applications**, click your application, and next to the environment, click **Request Process**![](../images/request_process_icon.gif), and in the Run Process window, select the **Schedule Deployment?** check box.

When you select the **Schedule Deployment?** check box, the **Date** and **Time** fields appear for you to specify the date and time for the deployment to run. The **Make Recurring** setting deploys the application on a regular schedule. For example, if you are practicing continuous delivery, the `Daily` option deploys the application to the target environment every day.

After you schedule the deployment, it is added to the calendar. There, if you click the scheduled deployment, you can edit, delete, or investigate the deployment. You can also add scheduled deployments directly from the calendar by opening the calendar and clicking **Schedule Process**.

**Note:** Do not change the starting time of a scheduled deployment. Instead, delete the recurring deployment and recreate it.

A blackout is a set per-environment, per-application. After the blackout is set, no deployments or snapshots can be scheduled to occur in that environment. Any previously scheduled deployments to the environment fail if they fall within the blackout date you set. To set up a blackout, go to \(**Application** \> **Environments** \> **Calendar** \> **Add Blackout**\). If you must set blackouts for more than one environment, you must set a separate blackout for each environment. IBM UrbanCode Deploy prompts you to give the dates and times for the blackout.

**Parent topic:** [Deploying](../topics/deployment_ov.md)

