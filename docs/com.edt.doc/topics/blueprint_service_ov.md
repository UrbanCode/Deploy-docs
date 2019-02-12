# Modeling software services

You can add software services to blueprints that you create on the blueprint design server so that your applications can access those services at provisioning time.

-   **[Modeling object storage with Amazon S3 and OpenStack Swift](../../com.edt.doc/topics/blueprint_service_objectstorage.md)**  
Object storage systems \(such as Amazon Simple Storage Service \(S3\) and OpenStack Swift\) host collections of files and provide them on demand. These collections are sometimes called object storage containers object storage buckets. By including containers in a blueprint, you can provide information about those containers to applications.
-   **[Modeling Amazon Elasticache cache clusters](../../com.edt.doc/topics/blueprint_service_cache.md)**  
Cache clusters like Amazon ElastiCache store data in fast in-memory caches. By including cache clusters in a blueprint, you can connect applications to those clusters so that the applications can use the cached data.
-   **[Modeling databases with Amazon RDS](../../com.edt.doc/topics/blueprint_service_database.md)**  
Relational database services such as Amazon Relational Database Service \(RDS\) provide cloud-based databases. You can model these databases in blueprints and connect applications to them.
-   **[Modeling DNS records with Amazon Route 53](../../com.edt.doc/topics/blueprint_service_dns.md)**  
DNS \(domain name service\) records refer host names such as `www.example.com` to IP addresses. Amazon Route 53 can manage DNS records for your domains.

**Parent topic:** [Modeling environments for clouds through OpenStack Heat](../../com.edt.doc/topics/blueprint_edit_clouds.md)

