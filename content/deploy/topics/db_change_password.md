# Changing the database password {#db_change_password .task}

If you change the password for your database, you must update the password on the server.

1.  In a text editor, open the file conf\\server\\secured-installed.properties. 
2.  Specify the new database password in the following line of code:

    ```
    hibernate.connection.password=newPassword
    ```

    This password will be encrypted when you restart the server.

3.  Restart the server.

**Parent topic:** [Server settings and configuration](../topics/settings_ch.md)

