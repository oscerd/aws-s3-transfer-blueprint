camel-aws s3: Demonstrates how to use the camel-aws s3 component
======================================================
Summary: This quickstart demonstrates how to use the camel-aws s3 component in Camel in order to upload files to transfer files to a local destination 

What is it?
-----------

This quick start shows how to use Apache Camel, and its OSGi integration to use the OSGi config admin and transfer files from an S3 Bucket.

This quick start combines use of the Camel File component, which reads files and uses the Camel AWS s3 component to consume files from an S3 Bucket.

System requirements
-------------------

Before building and running this quick start you need:

* Maven 3.3.1 or higher
* JDK 1.8
* JBoss Fuse 7

Build and Deploy the Quickstart
-------------------------

1. Change your working directory to `camel-aws-s3-transfer` directory.
* Run `mvn clean install` to build the quickstart.
* Start JBoss Fuse 7 by running bin/fuse (on Linux) or bin\fuse.bat (on Windows).
* Create the following configuration file in the etc/ directory of your Red Hat JBoss Fuse installation:

  InstallDir/etc/org.jboss.fuse.quickstarts.camel.aws.s3.cfg
  Edit the org.jboss.fuse.quickstarts.camel.aws.s3.cfg file with a text editor and add the following contents:

  accessKey=`accessKey`
  secretKey=`secretKey`
  region=`region`
  bucket=`bucket`

* In the JBoss Fuse console, enter the following commands:

        feature:install camel-aws
        bundle:install -s mvn:org.jboss.fuse.quickstarts/camel-aws-s3-transfer/7.0.0.fuse-000151

* Fuse should give you an id when the bundle is deployed

* You can check that everything is ok by issuing  the command:

        bundle:list
   your bundle should be present at the end of the list


Use the bundle
---------------------

To use the application be sure to have deployed the quickstart in Fuse as described above. 

1. As soon as the Camel route has been started, you will see a directory `/tmp/out` on your machine.
3. Use `log:display` to check out the business logging.
4. In `/tmp/out` you should see the files from the bucket

Undeploy the Archive
--------------------

To stop and undeploy the bundle in Fuse:

1. Enter `bundle:list` command to retrieve your bundle id
2. To stop and uninstall the bundle enter

        bundle:uninstall <id>
