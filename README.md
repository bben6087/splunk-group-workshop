# splunk-group-workshop
## GitHub Pages
- https://bben6087.github.io/splunk-group-workshop/
##  The Team
| <img src="images/54418954.jpg" alt="Blake Bennett" style="width: 150px; height: 150px;"> | <img src="images/me.png" alt="Seth Bennett" style="width: 150px; height: 150px;"> |<img src="images/Logan.JPG" alt="Logan Krohn" style="width: 150px; height: 150px;"> | <img src="images/zach.PNG" alt="Zach Watson" style="width: 150px; height: 150px;"> |
|------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|-----------------------------------------------------------------------|---------------------------------------------------------------------|
| Blake Bennett | Seth Bennett | Logan Krohn | Zach Watson |

---

## Blake Bennett - Download, Install, Add Apps, and Monitoring Console
### How to Install
1. Head to https://www.splunk.com/ and click on the Free Splunk button in the top right hand corner ![Splunk Home](images/product_image.PNG) ![Free Splunk](images/free_splunk.PNG)
2. Fill out information to create an account or login if you have a pre-existng account. Once logged in click the download for the application version of Splunk Enterprise.
3. Once it is downloaded run the installation file and run through the setup wizard. When it asks you to create an account remember your credentials for later. (Note: This step can take some time when installing)
4. It will lauch a server that your computer hosts and it will ask you to login using the credentials you created in the installation. ![Splunk Enterprise Login](images/login.PNG)
5. Once logged in you will be directed to the homepage of the application and you have succesfully completed the installation of Splunk. ![Homepage](images/homepage.PNG)
### How to Add Apps to Splunk
1. Once at the main page click on "Find More Apps" in the side navigation bar and it will take you to a seperate page. This allows for the use of additional inside of Splunk making it a more versatile application which is neat!
2. Once there you can filter through different apps and find an app that will enhance your usage of splunk.
3. When you have found an app you want to install you simply click the green install button and it will prompt you to enter your credentials.
4. Once you have entered in your credentials successfully the app will be added to Splunk Enterprise. ![App Install](images/app_install.PNG)
### Monitoring Console
1. From the Splunk Dashboard Overview go to settings and click on "Monitoring Console"
![SettingsToMonitor](images/settings.PNG)
2. This monitoring lets you see when the PC was used at what time and what process are running
3. Click on the graphs or percentages for additional information regarding your machine and processes
![Graphs](images/graph.PNG)
4. Here on this page you can dive into an even deeper look into what is running on your machine from RAM, to CPU, to even Input/Output processes which is cool.
![Monitoring](images/monitoringoverview.PNG)
![Additional Info](images/additionalinformation.PNG)
![IO](images/IO.PNG)
### What does installing additional apps and the monitoring console this have to do with Digital Forensics?
- Splunk is made for machine monitoring so you can monitor changes in your employees keystrokes, mouse usage, browsing, and file changes, etc. This allows companies to make sure employees are working or are not making malicous changes to company files without the comapny knowing. It tracks every change on the machine to every minute process. On top of that having a tool that allows the installation of additional apps that expand the capabilities of Splunk is a great feature. Which is what I covered. Having additional applications that expand Splunk allows for many configurations and versatility depending on your own personal or company needs. All in all the ability to add addtional apps for Digital Forensics and being able to monitor PC activity is a a great tool for Digital Investigators.
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
1. Go to https://plaso.readthedocs.io/en/latest/sources/user/Ubuntu-Packaged-Release.html and use the following commands in WSL to install the repository and Plaso for Ubuntu 20.04. ![Plaso Image](images/Plaso.png)
2. Find a disk image you want to use and use the command 'log2timeline.py plaso.dump name-of-disk-image'. If asked to choose a partition, select the partition with the most content. If asked to select a VSS(volume shadow snapshot), select -all.![Dump Image](images/Dump.png)
4. After completion use the command 'psort.py -o l2tcsv -w timeline.csv plaso.dump' to sort the content and write the database into a .csv file which we will use later.![Psort Image](images/Psort.png)
5. In Splunk, go to settings and create a new index. Once done, go back to settings/Data Inputs/File and Directories and choose your .csv file to add to your index. ![Data Image](images/Data.png)
7. Explore the index with the Search tool and the bar chart showing you the activity of the Image file in chronological order. ![Index Image](images/Index.png)
 
## Zach Watson - Web Input for Splunk
### Using Website Input for Splunk

1. In the Splunk Dashboard, click on "Website Input" on the left of the screen. ![Dashboard](images/1.png)
2. Click the "New Input" tab, in which you will start the process to create the web scraper. Enter the website you want to use in the URL section. Then, enter the interval that the web input will update. Click the "Next" button. ![New Input](images/2.png)
3. Skip "Enter Credentials" by clicking "Next". On the "CSS Selector" tab, a preview of your website will show up on the bottom half of the page. ![CSS1](images/3.png)
4. In the website preview, click the element that you want to record. For this example, I clicked the titles of the articles. ![CSS2](images/4.png)
5. Skip "Customize Output" and "Define Input Settings" by clicking "Next" twice. Enter the title of your input. The bottom text box fills automatically according to the title you put in. Click "Next" to finalize your web input. ![Save](images/5.png)
6. Click the "Overview" tab. This is where you can see all of your current and previous web inputs. ![Overview](images/6.png)
7. Click on your web input. A Search should pop up with the data that the web input gathered. ![Search](images/7.png)

## Credits
- https://www.splunk.com/
- [File and Directory monitoring](https://docs.splunk.com/Documentation/Splunk/8.2.2/Data/MonitorfilesanddirectorieswithSplunkWeb)
- For additional training for Splunk and various tools: https://www.splunk.com/en_us/training.html?sort=Newest
- https://www.splunk.com/en_us/blog/tips-and-tricks/using-splunk-for-computer-forensics-2.html
- Plaso Log2timeline in WSL2: https://www.youtube.com/watch?v=g9V6OUCe12k&t=892s
- Looking at .cvs files in Splunk: https://www.youtube.com/watch?v=fKoAB6n_ivs&t=14s
- Splunk table: https://docs.splunk.com/Documentation/DashApp/0.9.0/DashApp/chartsTable
- Website input for Splunk: https://splunkbase.splunk.com/app/1818/
