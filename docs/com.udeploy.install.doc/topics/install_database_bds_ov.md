# Blueprint design server database configuration

The HCL® UrbanCode™ Deploy blueprint design server requires a database. For production installations, you can install a database, or you can reuse an engine database.

If you are installing an evaluation server, you can also allow the blueprint design server installation program to install an Apache Derby database for you. In this case, you do not need to install a database yourself. However, you cannot use Derby for production blueprint design servers. Derby is for evaluation only. To use this method, run the installation program, and when the program prompts you for the type of database, specify Derby.

