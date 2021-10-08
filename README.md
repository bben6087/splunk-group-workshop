# splunk-group-workshop

## Blake Bennett - Download and Installation
![Profile Image](images/54418954.jpg)
### How to Install
1. Head to https://www.splunk.com/ and click on the Free Splunk button in the top right hand corner ![Splunk Home](images/product_image.PNG) ![Free Splunk](images/free_splunk.PNG)
2. Fill out information to create an account or login if you have a pre-existng account. Once logged in click the download for the application version of Splunk Enterprise.
3. Once it is downloaded run the installation file and run through the setup wizard. When it asks you to create an account remember your credentials for later. (Note: This step can take some time when installing)
4. It will lauch a server that your computer hosts and it will ask you to login using the credentials you created in the installation. ![Splunk Enterprise Login](images/login.PNG)
5. Once logged in you will be directed to the homepage of the application and you have succesfully completed the installation of Splunk. ![Homepage](images/homepage.PNG)
### How to Add Apps to Splunk
1. Once at the main page click on "Find More Apps" in the side navigation bar and it will take you to a seperate page.
2. Once there you can filter through different apps and find an app that will enhance your usage of splunk.
3. When you have found an app you want to install you simply click the green install button and it will prompt you to enter your credentials.
4. Once you have entered in your credentials successfully the app will be added to Splunk Enterprise. ![App Install](images/app_install.PNG)
## Seth Bennett

## Logan Krohn - Plaso and Log2Timeline for Splunk
1. Go to https://plaso.readthedocs.io/en/latest/sources/user/Ubuntu-Packaged-Release.html and use the following commands in WSL to install the repository and Plaso for Ubuntu 20.04.
2. Find a disk image you want to use and use the command 'log2timeline.py plaso.dump name-of-disk-image'. If asked to choose a partition, select the partition with the most content. If asked to select a VSS(volume shadow snapshot), select -all.
3. After completion use the command 'psort.py -o l2tcsv -w timeline.csv plaso.dump' to sort the content and write the database into a .csv file which we will use later. 
4. In Splunk, go to settings and create a new index. Once done, go back to settings/Data Inputs/File and Directories and choose your .csv file to add to your index. 
5. Explore the index with the Search tool and the bar chart showing you the activity of the Image file in chronological order. 
 
## Zach Watson - Web Input for Splunk

## Credits
- https://www.splunk.com/
