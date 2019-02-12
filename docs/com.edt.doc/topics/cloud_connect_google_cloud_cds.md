# Registering Google Cloud Platform public images

To use Google Cloud Platform public images in the blueprint designer, you must register image project types and families with the cloud discovery service.

After you configure operating system types, you can automatically access the latest version of the operating systems that are available on Google Cloud Platform. You can use these images in your blueprints.

1.   Open the cloud discovery service configuration file. If you do not have a cloud discovery service configuration file, see [Setting up images, regions, and flavors for the cloud discovery service and engine](../../com.udeploy.doc/topics/cds_configure.md).
2.  In the section of this file that is labeled `google`, add image projects and families.You can obtain a list of available image types from Google Cloud. See [Images](https://cloud.google.com/compute/docs/images#os-compute-support) in the Google Cloud Platform Compute Engine documentation. For example, the following code creates six different image project types:

    ```
     "google":{       
          "images":[  
             {  "name":"centos-cloud",
                "family":[  
                   "centos-7",
                   "centos-6"
                ]
             },
            {   "name":"debian-cloud",
                "family":[  
                   "debian-8"
                ]
             },
             {  
                "name":"rhel-cloud",
                "family":[  
                   "rhel-6",
                   "rhel-7"
                ]
             },
            {  
                "name":"windows-cloud",
                "family":[  
                   "windows-2008-r2",
                   "windows-2012-r2",
                   "windows-2016-core",
                   "windows-2016"
                ]
             },
            {  
                "name":"suse-cloud",
                "family":[  
                   "sles-12",
                   "sles-11"
                ]
             },
              {  
                "name":"ubuntu-os-cloud",
                "family":[  
                   "ubuntu-1204-lts",
                   "ubuntu-1404-lts",
                   "ubuntu-1610",
                   "ubuntu-1604-lts"              
                ]
             }
          ]  
        }
    }
    
    
    ```

    In this code, name is the image project name and family is the image family.

3.   Save the file and restart the cloud discovery service. To restart the cloud discovery service, see [Starting the blueprint designer, cloud discovery service, and engine](../../com.udeploy.install.doc/topics/start_patterns.md) and [Stopping the blueprint designer, cloud discovery service, and engine](../../com.udeploy.install.doc/topics/stop_patterns.md).

You can add images from the families that you specified to your blueprints.

**Parent topic:** [Connecting to Google Cloud Platform](../../com.edt.doc/topics/cloud_connect_google_cloud.md)

