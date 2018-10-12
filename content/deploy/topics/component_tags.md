# Component tags and component resource tags {#concept_y51_3t2_z5 .concept}

You can tag components while you work on the **Components** tab, or you can tag components while you work in the **Resources** tab. However, the tags that you associate with components in these two contexts behave differently. Furthermore, you can also include components in a resource by using the tags that are associated with components in the **Component** tab.

In the **Components** tab, you can tag components according to your requirements. See [Adding tags to objects](addingtags_tsk.md#). You can organize and associate components by using tags.

In the **Resources** tab, you can tag components and other objects just as in other tabs. When you tag a component in the **Resources** tab, that tag is not applied to the component throughout all tabs. The component resource tag applies to the component only when the component is related to a resource.

As you develop processes, you can use the component resource tag for a few things. You can specify a set of components to be used for an Install Multiple Components or Rollback Multiple Components step in an application process. Specifying a set of components this way runs a process for each component with the specified component tag in the environment. Alternatively, you can also add a component resource tag to an agent resource in the resource tree. Adding the tag is a way of directing that this is a component slot that can be fulfilled with any component that is tagged with the corresponding component tag.

**Tip:** In the **Resources** tab, you can click the **Actions** menu, click **Component Tag**, and select the tag of components you want to add to the resource. By adding components this way, you automate the components that are included in resources. Otherwise, you have to add components manually and individually to resources.

**Parent topic:** [Tags](../topics/tags_ch.md)

