# Overview of blueprints

Two types of blueprints are available, depending on how you connect to the target cloud.

To provision environments on clouds that use virtual system patterns, you create blueprints on the HCL® UrbanCode™ Deploy server, using resource templates.

To provision environments on clouds through OpenStack Heat, you create blueprints on the blueprint design server.

-   **[Blueprints for clouds that use virtual system patterns](../../com.ibm.edt.doc/topics/blueprint_cpt_vsp.md)**  
You provision resources on virtual system pattern-based clouds through application blueprints in the HCL UrbanCode Deploy server.
-   **[Blueprints for clouds that you connect to through OpenStack Heat](../../com.ibm.edt.doc/topics/blueprint_cpt_heat.md)**  
You can provision environments on clouds through HEAT-based blueprints that you model on the blueprint design server. Heat-based blueprints use OpenStack Heat Orchestration Templates to model the infrastructure of a cloud environment, including its virtual images, network, and storage. A heat-based blueprint can also include software components to be deployed in the environment.

**Parent topic:** [Modeling cloud environments with the blueprint designer](../../com.ibm.edt.doc/topics/blueprint_ov.md)

