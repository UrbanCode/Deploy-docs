# Importing and exporting generic processes {#app_genProcess .task}

You can move generic processes between servers by exporting and importing them.

Exporting a generic process creates a JSON file \(with a json file extension\) that contains the process and the properties that are associated with the process.

When you export components, applications, processes, or templates, and then import them on a different computer, the same versions of the same plug-ins must be installed on both computers.

Importing a generic process makes the exported version of the process available from another server.

1.   On the first server, click **Processes** to open the **Processes** tab. 
2.   Click **Export** in the **Actions** column to export the process. You can load the file into a text editor or save it.

    **Important:** You must create the JSON file that contains the process definition from a server that uses the same version of IBM® UrbanCode® Deploy as the destination server.

3.   Save the file. A file is created with the same name as the selected process. The file name takes the form of this example: exampleprocess.json.
4.   Make the file available to the second server. 
5.   On the second server, click **Processes** \> **Import Process** to open the Import Process window. 
6.   Click **Choose File**, and then select the JSON file that contains the process definition. 
7.   To upgrade an existing process, select **Upgrade Process**. If the name of the process in the JSON file matches an existing process, the process parameters are updated with new values. If the process name is not found, the command has no effect.

    **Note:** An existing process must match the name of the process in the JSON file, not the name of the file itself. The process name is the first parameter in the JSON file. The following text is the JSON representation of a process named `Post-process test`.

    ```
    "name": "Post-process test",
    ```

8.  Click **Submit**.

**Parent topic:** [Generic processes](../topics/genProcess_ch.md)

