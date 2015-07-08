# xltv-vagrantdemo
Demo of XLTV along with Jenkins in a vagrant image.

This demo box uses XL TestView 1.2.0 CE with Jenkins.

#To use this image do the following:

1. clone this repository
2. cd to directory where you cloned this repository
3. run vagrant up
4. run vagrant ssh
5. run ifconfig to get your IP

To access XLTV use http://your-image-ip:6516
To access Jenkins use http://your-image-ip:8080

#To import test results in XLTV
1. Go to Import on the navigation in XLTV
2. Enter "XLTV Server"
3. Choose Project and enter Test Spec name
4. Enter /home/test-samples as the import path
5. Enter */**.xml as the file string to import

#To kick off the test job in Jenkins:
1. In XLTV, create a test specification which you want to push the jenkins output to
2. In Jenkins, click on the job name and click configure
3. Add a 'Post Build Step'
4. Choose your Test Specicificaiton
5. Enter */**.xml in the include field
5. Build job and look at console for the [XL TestView] messages.

PowerPoint training document is included in this repository.

<b>Please note:</b>  The job will push results using a simple phpunit test which Jenkins runs during the build and exports to jUnit format.  The build will fail.  You will see the push output in the build console as well as some results added to the test spec in XLTV that you choose to push to.