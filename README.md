## Resilenet Multizone SFTP Server, with IBM Kubernetes and IBM Cloud object Storage

IBM Offer Cloud object Storag, can be used to build a cost effective resilient and secure storage solution, mean while still legacy system depends on SFTP and legacy file protocols for file trasfer.

IBM Cloud Object used to provide SFTP access to object storage but it is deprecated since 10 Decemebr 2018
https://console.bluemix.net/docs/infrastructure/objectstorage-swift/connect-object-storage-using-sftp.html#connecting-to-object-storage-with-sftp

Using sftp docker ready instance provided by [atomz/sftp](https://hub.docker.com/r/atmoz/sftp/)

### Comparing storage options 

As elaborated in the below image IBM Cloud object storage, spawn over 3 zones
![Comparing Storag options](https://console.bluemix.net/docs/api/content/containers/images/cs_storage_options_multizone.png)


### Define Cloud object Storage, plugin to IBM Kubernetes Service

The steps in the documentation using user space file system [Fuse](https://en.wikipedia.org/wiki/Filesystem_in_Userspace), to make Cloud Object Storage, accessed as traditional File system 

In order to connect IBM kubernetes cluster follow this [Documentation](https://console.bluemix.net/docs/containers/cs_storage_cos.html#object_storage)

#### NOTE: the previous steps works mainly standard cluster, as the provided sotrage classes get the Cloud object storage End Point URL based on the Cluster region, which will not work with lite cluster, to make it work with lite cluster or use specific URL a [new storageclass need to created](https://raw.githubusercontent.com/ahmadsayed/ibm-cloud-object-storage-sftp/master/lite-only/ibmc-s3fs-standard-regional-lite.yaml), insure updating the URL as per the object storage provisioned region

### 
