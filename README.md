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

1. Cloud SQL
2. Spanner
3. Firestrom
4. Bigtable
