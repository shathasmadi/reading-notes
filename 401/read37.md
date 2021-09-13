# Read 37 : S3

## [Introduction to Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)

### What is Amazon S3?

- Amazon Simple Storage Service (Amazon S3) is storage for the Internet. 
- Amazon S3 has a simple web services interface that you can use to store and retrieve any amount of data, at any time, from anywhere on the web. 

---

### Advantages of using Amazon S3
- Following are some of the advantages of using Amazon S3:

- **Creating buckets** – Create and name a bucket that stores data. 

- **Storing data** – Store an infinite amount of data in a bucket.
- Upload as many objects as you like into an Amazon S3 bucket. Each object can contain up to 5 TB of data.
- Each object is stored and retrieved using a unique developer-assigned key.

- **Downloading data** – Download your data anytime.

- **Permissions** – Grant or deny access to others who want to upload or download data into your Amazon S3 bucket. 

- **Standard interfaces** – Use standards-based REST and SOAP interfaces designed to work with any internet-development toolkit.

---

### Amazon S3 concepts

#### 1. **Buckets**
- A bucket is a container for objects stored in Amazon S3.
- Every object is contained in a bucket. 

- ***Buckets serve several purposes:**
    - They organize the Amazon S3 namespace at the highest level.
    - They identify the account responsible for storage and data transfer charges.
    - They play a role in access control.
    - They serve as the unit of aggregation for usage reporting.

#### 2. **Objects**
- Objects are the fundamental entities stored in Amazon S3. 
- Objects consist of object **data** and **metadata**. 
- The **data** portion is **opaque** to Amazon S3.
- The **metadata** is a set of name-value pairs that describe the object.

#### 3. **Keys**
- A key is the unique identifier for an object within a bucket.
- Every object in a bucket has exactly one key.
- The combination of a bucket, key, and version ID uniquely identify each object. 

#### 4. **Regions**
You can choose the geographical AWS Region where Amazon S3 will store the buckets that you create.

---

### Amazon S3 data consistency model
- Amazon S3 provides strong read-after-write consistency for PUTs and DELETEs of objects in your Amazon S3 bucket in all AWS Regions. 
- This applies to both writes to new objects as well as PUTs that overwrite existing objects and DELETEs. In addition, read operations on Amazon S3 Select, Amazon S3 Access Control Lists, Amazon S3 Object Tags, and object metadata (e.g. HEAD object) are strongly consistent.

- Updates to a single key are atomic. 

- Amazon S3 achieves high availability by replicating data across multiple servers within AWS data centers. 
- If a PUT request is successful, your data is safely stored. Any read (GET or LIST) that is initiated following the receipt of a successful PUT response will return the data written by the PUT. **Here are examples of this behavior:**
    - A process writes a new object to Amazon S3 and immediately lists keys within its bucket. The new object will appear in the list.
    - A process replaces an existing object and immediately tries to read it. Amazon S3 will return the new data.
    - A process deletes an existing object and immediately tries to read it. Amazon S3 will not return any data as the object has been deleted.
    - A process deletes an existing object and immediately lists keys within its bucket. The object will not appear in the listing.


---

### Amazon S3 features

#### 1. **Storage classes**
Amazon S3 offers a range of storage classes designed for different use cases.

#### 2. **Bucket policies**
- Bucket policies provide centralized access control to buckets and objects based on a variety of conditions, including Amazon S3 operations, requesters, resources, and aspects of the request (for example, IP address). 
- The policies are expressed in the access policy language and enable centralized management of permissions. 
- The permissions attached to a bucket apply to all of the bucket's objects that are owned by the bucket owner account.

- Both individuals and companies can use bucket policies.

#### 3. **AWS Identity and Access Management**
- You can use AWS Identity and Access Management (IAM) to manage access to your Amazon S3 resources.

#### 4. **Access control lists(ACL)**
To control access to each of your buckets and objects.

#### 5. **Versioning**
To keep multiple versions of an object in the same bucket.

#### 6. **Operations**
- **Common operations**
    - Create a bucket.
    - Write an object.
    - Read an object.
    - Delete an object.
    - List keys – List the keys contained in one of your buckets. You can filter the key list based on a prefix.

---

### Amazon S3 application programming interfaces (API)
- **The REST interface**
- **The SOAP interface**