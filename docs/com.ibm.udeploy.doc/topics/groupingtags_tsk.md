# Grouping servers by using tags

You can use tagging to group target servers for organized deployments.

By using tags and filtering, you can separate resources that represent production servers into two logical groups. If you tag half the resources with a blue tag and half with a green tag, then you can run deployments in a fashion that is sometimes called blue-green deployment. When you plan to deploy a new version of an application to a production environment, deploy it to the blue group first. Meanwhile, the green group of servers still provides the older version of the application. After the new version of the application is deployed to the blue group, repeat the process with the green group. In this way, you can deploy a new version of software while still providing uninterrupted service in your production environment.

1.   Tag resources, which represent target servers, in two groups. To learn more about tagging, see [Adding tags to objects](addingtags_tsk.md). If you have resources that are organized in groups, you can apply a tag to a top-level group. For example, create top-level groups for the Blue servers and the Green servers. If you tag the two top-level groups as Blue and Green, then all resources that a particular group contains are included in deployment steps when you limit deployment to a specific tag.
2.  Create two application deployment processes that correspond to the two tags.When you add an Install Component step to an application process, you can use the **Limit to Tag** field to restrict the deployment to resources that have a specific tag.
3.  Deploy the new version of an application by using the first application deployment process.For example, deploy the application to a group of servers that are tagged as Blue servers.
4.  Check that the new version of the application is running as expected.
5.  Deploy the new version of an application by using the other application deployment process.For example, deploy the application to a group of servers that are tagged as Green servers.

**Parent topic:** [Tags](../topics/tags_ch.md)

