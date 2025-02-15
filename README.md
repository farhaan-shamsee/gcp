# GCP

## Storage

### Cloud storage

- object storage
- Data commonly stored as objects include video, pictures, and audio recordings.
- A few examples include serving website content, storing data for archival and disaster recovery, and - distributing large data objects to end users via Direct Download.
- Buckets
- versioning
- how to do security
- ACL, IAM
- Roles are inherited from project to bucket to object.
- lifecycle management
- Storage classes:
  - standarad: best for frequently accessed, or “hot,” data. It’s also great for data that’s stored for only brief periods of time.
  - Nearline Storage.: This is best for storing infrequently accessed data, like reading or modifying data on average once a month or less.data backups, long-tail multimedia content, or data archiving.
  - Coldline Storage low-cost option for storing infrequently accessed data. Nearline Storage, Coldline Storage is meant for reading or modifying data, at most, once every 90 days.
  - Archive Storage. option, used ideally for data archiving, online backup, and disaster recovery. data that you plan to access less than once a year,
  - autoclass: Autoclass simplifies and automates cost saving for your Cloud Storage data.
  - Cloud Storage always encrypts data on the server side, before it’s written to disk, at no additional charge.
- Data transfer
  - Many customers simply carry out their own online transfer using gcloud storage, which is the Cloud Storage command from the Cloud SDK.
  - Data can also be moved in by using a drag and drop option in the Cloud Console, if accessed through the Google Chrome web browser.
  - Storage Transfer Service enables you to import large amounts of online data into Cloud Storage quickly and cost-effectively.
  - The Storage Transfer Service lets you schedule and manage batch transfers to Cloud Storage from another cloud provider, from a different Cloud Storage region, or from an HTTP(S) endpoint.
  - And then there is the Transfer Appliance, which is a rackable, high-capacity storage server that you lease from Google Cloud. You connect it to your network, load it with data, and then ship it to an upload facility where the data is uploaded to Cloud Storage.
  - 

### Cloud SQL

Cloud SQL offers fully managed relational databases, including MySQL, PostgreSQL, and SQL Server as a service.

- automatic replication
- ![image](https://github.com/user-attachments/assets/2aec1b72-66c3-4369-b27f-42c24ac4f723)


### Spanner

Spanner is a fully managed relational database service that scales horizontally, is strongly consistent, and speaks SQL.

![image](https://github.com/user-attachments/assets/5017f499-ede8-4eed-8658-7bc2dec7920b)

### Firestrom
Firestore is a flexible, horizontally scalable, NoSQL cloud database for mobile, web, and server development. With Firestore, data is stored in documents and then organized into collections. Each document contains a set of key-value pairs.

![image](https://github.com/user-attachments/assets/b77cb8fd-6434-4c3d-bc64-09c153b3fcf8)

![image](https://github.com/user-attachments/assets/0540e0ea-e555-473e-b34e-0c3a7e519f4f)

### Bigtable

Bigtable is Google's NoSQL big data database service. same database that powers many core Google services, including Search, Analytics, Maps, and Gmail.
When deciding which storage option is best, customers often choose Bigtable if: They’re working with more than 1TB of semi-structured or structured data.
Data is a time-series or has natural semantic ordering.


## CloudRun

- We’ll begin with Cloud Run, which is a managed compute platform that runs stateless containers via web requests or Pub/Sub events.
- Bult on Knative
- ![image](https://github.com/user-attachments/assets/e35680ca-ba39-4afb-bc23-78a7ff272810)
- Source based workflow
  - The source-based approach will deploy source code instead of a container image.
  - Cloud Run then builds the source and packages the application into a container image.
  - Cloud Run does this using Buildpacks - an open source project.
  - You can use Cloud Run to run any binary, as long as it’s compiled for Linux sixty-four bit.
  - As long as your app handles web requests, you’re good to go.
  - Events from Cloud Storage and Pub/Sub can trigger Cloud Run functions asynchronously, or you can use HTTP invocation for synchronous execution.

