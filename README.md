# xltv-vagrantdemo
Demo of XLTV along with Jenkins in a vagrant image

To use this image do the following:

1. clone this repository
2. cd to directory where you cloned this repository
3. run vagrant up
4. run vagrant ssh
5. run ifconfig to get your IP

To access XLTV use http://your-image-ip:6516
To access Jenkins use http://your-image-ip:8080

To kick off the test job in Jenkins:
1. In XLTV, create a test specification which you want to push the jenkins output to
2. In Jenkins, click on the job name and click configure
3. Add a 'Post Build Step'
4. Choose your Test Specicificaiton
5. Enter */**.xml in the include field
5. Build job and look at console for the [XL TestView] messages.

While showing the 'import' funciton you can import test results in XLTV from /home/test-samples directory of this image.

Please note:  The job will not actually push the results because there are no results in this Jenkins job.  You will be able to tell that it's working because it will note <b>[XL TestView] Uploading test run data to 'http://your-image-ip:6516'</b>
