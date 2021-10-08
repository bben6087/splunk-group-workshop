# splunk-group-workshop
##  The Team
| <img src="images/54418954.jpg" alt="Blake Bennett" style="width: 150px; height: 150px;"> | <img src="images/me.png" alt="Seth Bennett" style="width: 150px; height: 150px;"> |<img src="" alt="Logan Krohn" style="width: 150px; height: 150px;"> | <img src="" alt="Zach Watson" style="width: 150px; height: 150px;"> |
|------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|-----------------------------------------------------------------------|---------------------------------------------------------------------|
| Blake Bennett | Seth Bennett | Logan Krohn | Zach Watson |

---

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
## Seth Bennett - Local System Monitoring
### Setting up File Directory Monitoring
1. Starting from the Splunk Dashboard First click "Settings" in the top right then click "Add Data"
    - ![Pic1](images/Seth_Bennett/DataInput1.png)
2. From this point proceed to click the "Monitor" Button in the bottom section of the page
    - ![Pic1](images/Seth_Bennett/DataInput2.png)
3. From this point you must select what source of data you would like to use I will will be using File & Directories in the example.
    - From Here Enter the exact File or Directory you would  like to monitor the files in and click next
    *I would recomend Being as specific as possible, the amount of information can be quite verbose*
    - ![Pic1](images/Seth_Bennett/DataInput3.png)
4.  Next, you will be have several options, one of which is index, you may use one of the default indexes but I suggest Creating a new index for the specific job as seen in the pictures below and then click next
    - ![Pic1](images/Seth_Bennett/DataInput4.png)
    - ![Pic1](images/Seth_Bennett/DataInput5.png)
    - ![Pic1](images/Seth_Bennett/DataInput6.png)
5. From here you should be met with this page confirming the information you have given and you may click submit
    - ![Pic1](images/Seth_Bennett/DataInput7.png)
6. You have now successfully linked the monitor to your specified file or directory
### Searching your index
1. Starting from the Splunk Dashboard First click "Settings" in the top right then click "Monitor"
    - ![Pic2](images/Seth_Bennett/SearchIndex1.png)
2. Once on the Monitor page click the "Run a Search" button in the top navbar
    - ![Pic2](images/Seth_Bennett/SearchIndex2.png)
3. Now that you are ready to search your index, you may search by source, index, or both. Below are the syntaxs for the two options
    - source="YourFullDirectoryPath\\*"
    - index="YourIndexName"
    - ![Pic2](images/Seth_Bennett/SearchIndex3.png)
---

## Logan Krohn - Plaso and Log2Timeline for Splunk
<img src="images/Logan.JPG" alt="logan" style="width: 240px; height: 200px;">
![Logan Image](images/Logan.JPG)
1. Go to https://plaso.readthedocs.io/en/latest/sources/user/Ubuntu-Packaged-Release.html and use the following commands in WSL to install the repository and Plaso for Ubuntu 20.04. ![Plaso Image](images/Plaso.png)
2. Find a disk image you want to use and use the command 'log2timeline.py plaso.dump name-of-disk-image'. If asked to choose a partition, select the partition with the most content. If asked to select a VSS(volume shadow snapshot), select -all.![Dump Image](images/Dump.png)
4. After completion use the command 'psort.py -o l2tcsv -w timeline.csv plaso.dump' to sort the content and write the database into a .csv file which we will use later.![Psort Image](images/Psort.png)
5. In Splunk, go to settings and create a new index. Once done, go back to settings/Data Inputs/File and Directories and choose your .csv file to add to your index. ![Data Image](images/Data.png)
7. Explore the index with the Search tool and the bar chart showing you the activity of the Image file in chronological order. ![Index Image](images/Index.png)
 
## Zach Watson - Web Input for Splunk

## Credits
- https://www.splunk.com/
