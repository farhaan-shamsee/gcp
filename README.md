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


1. Cloud SQL
2. Spanner
3. Firestrom
4. Bigtable
