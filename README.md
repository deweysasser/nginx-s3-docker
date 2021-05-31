ARCHIVED
========

This project is no longer maintained.  

You should almost certainly just use S3's ability to serve a static website.

---


nginx-s3-docker
===============

NGINX running against and S3 bucket mounted with S3FS


Usage
-----

     docker run -it -p 8082:80  --privileged=true -e AWS_BUCKET=my-bucket -e AWSACCESSKEYID=MYKEY -e MYSECRET -e nginx-s3

Environment
-----------

* SUBDIR -- subdirectory of the bucket from which to serve files


Security Notes
--------------

Currently, NGINX runs *as root* in the container.  This is bad.  It's
working around an issue with the www-data user not being able to read
from and s3fs mounted bucket.  It works, but this needs to be fixed.
