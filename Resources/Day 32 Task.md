🎯 Day 32 Task


✅ THM Room


https://tryhackme.com/room/burpsuiterepeater

-----------------------------------------------------------------------------------------------------------------------------------------------
eJPT Journey (with consistency)

🎯 eJPT Day 1 

🔃 Introduction (1-3)

1. The Information Security Field - Study Guide
3. Cryptography & VPNs - Study Guide
3. Wireshark Introduction - Study Guide

Wireshark Additional Resources 

Cheat Sheets : - https://www.comparitech.com/net-admin/wireshark-cheat-sheet/


Hindi - Youtube : - https://youtu.be/a-Fg7VVDf14


English - Youtube : -  https://youtu.be/4_7A8Ikp5Cc 


**Note:- eJPT Material are very good for cracking the eJPT exam but I share some additional resource for learning !!!**


----------------------------------------------------------------------------------------------------------------------------------------------
✅ 4.2.11 Test Cloud Storage


Test Objectives - Assess that the access control configuration for the storage services is properly in place.


How to Test

First identify the URL to access the data in the storage service, and then consider the following tests:

**read the unauthorized data**

**upload a new arbitrary file**


You may use curl for the tests with the following commands and see if unauthorized actions can be performed successfully.


To test the ability to read an object:

```
curl -X GET https://<cloud-storage-service>/<object>
```


To test the ability to upload a file:


```
curl -X PUT -d 'test' 'https://<cloud-storage-service>/test.txt'
```

Testing for Amazon S3 Bucket Misconfiguration

The Amazon S3 bucket URLs follow one of two formats, either virtual host style or path-style.


**Virtual Hosted Style Access**

```
https://bucket-name.s3.Region.amazonaws.com/key-name
```

In the following example, my-bucket is the bucket name, us-west-2 is the region, and puppy.png is the key-name:

```
https://my-bucket.s3.us-west-2.amazonaws.com/puppy.png
```

**Path-Style Access**

```
https://s3.Region.amazonaws.com/bucket-name/key-name
```

As above, in the following example, my-bucket is the bucket name, us-west-2 is the region, and puppy.png is the key-name:

```
https://s3.us-west-2.amazonaws.com/my-bucket/puppy.jpg
```


For some regions, the legacy global endpoint that does not specify a region-specific endpoint can be used. Its format is also either virtual hosted style or path-style.


**Virtual Hosted Style Access**

```
https://bucket-name.s3.amazonaws.com
```

**Path-Style Access**

```
https://s3.amazonaws.com/bucket-name
```


**Identify Bucket URL**

For black-box testing, S3 URLs can be found in the HTTP messages. The following example shows a bucket URL is sent in the img tag in a HTTP response.
```
...
<img src="https://my-bucket.s3.us-west-2.amazonaws.com/puppy.png">
...
```

**Testing with AWS-CLI**

In addition to testing with curl, you can also test with the AWS Command-line tool. In this case s3:// protocol is used.

**List**

The following command lists all the objects of the bucket when it is configured public.


```
aws s3 ls s3://<bucket-name>
```

**Upload**

The following is the command to upload a file

```
aws s3 cp arbitrary-file s3://bucket-name/path-to-save
```

This example shows the result when the upload has been successful.

```
aws s3 cp test.txt s3://bucket-name/test.txt
upload: ./test.txt to s3://bucket-name/test.txt
```

This example shows the result when the upload has failed.

```
aws s3 cp test.txt s3://bucket-name/test.txt
upload failed: ./test2.txt to s3://bucket-name/test2.txt An error occurred (AccessDenied) when calling the PutObject operation: Access Denied
```
**Remove**

The following is the command to remove an object

```
aws s3 rm s3://bucket-name/object-to-remove
```

**Tools**

AWS CLI - https://aws.amazon.com/cli/


Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 


I am just Sharing what I learn for help Other's !!!


#infosec #learn365 #owasp 






