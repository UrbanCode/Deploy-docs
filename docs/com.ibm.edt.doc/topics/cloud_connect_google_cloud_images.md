# Configuring Google Cloud Platform images

You can configure a custom image to use in your Google Cloud Platform environments.

After you configure the cloud discovery service for Google Cloud Platform image projects, you can access the latest version of the operating systems that Google Cloud offers. You can also configure custom images to use in your blueprints.

1.  Create an image disk in Google Cloud Platform.
    1.  From the Google Cloud Platform dashboard, click **Compute Engine**.
    2.  Click **Disks**, and then click **Create disk**.
    3.  Provide a name and optionally provide a description.
    4.  From the **Zone** list, select the zone in which to use the custom image.
    5.  From the **Source image** list, select an operating system image.
    6.  Specify the size of the image disk.
    7.  Click **Create**.
2.  Use the disk image to create a new operating system image.
    1.  Click **CREATE IMAGE**.
    2.  Provide a name for the image.
    3.  From the **Source** list, select the image disk that you created.
    4.  Click **Create**.

You can add the custom image to your blueprints and provision them to any available region in Google Cloud. See [Modeling environments for Google Cloud Platform](blueprint_edit_google_cloud.md#).

**Parent topic:** [Connecting to Google Cloud Platform](../../com.ibm.edt.doc/topics/cloud_connect_google_cloud.md)

