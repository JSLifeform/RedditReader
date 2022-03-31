# RedditReader/Visualizer Readme

### Introduction

Thank you for viewing the Reddit Reader/Visualizer! This project is aimed at analyzing comments in Reddit threads, looking at outliers. It focuses on comment/account creation times, total Reddit Karma, comment Karma, etc. It is in its infancy but an ideal end goal would be to detect trends in comments that could point towards potential bot/troll accounts.

The project is currently boken into 2 .ipynb files - Reddit and RedditVisualizer. The Reddit file logs into the Reddit API and scrapes information from top comments in https://reddit.com/r/politics/hot. This file may soon be converted into a .py file, so as to be allowed to run by the Windows Task Scheduler. The data is then logged into 2 out files, out.csv and cumulativeout.csv. 

This .csv files are processed by RedditVisualizer. The data is looked at in a variety of different ways. These are changing dynamically as I attempt different ways to look at the data, in order to find patterns I consider suspicious or interesting. To be frank, there is no clear hypothesis and/or conclusion to this project - it is more of a playground. I will continue to add functionality and more structure as I get a chance to use more data within my project.

### Installation

This project was written in Python 3.9. It is highly recommended that this project is run within Jupyter Notebook. The quick installation process within Conda/Notebook is below:

    1) Download the repository from https://github.com/JSLifeform/RedditReader

    2) Open Anaconda Prompt

    3) Navigate to repository directory

    4) Run "conda env create -f environment.yml" to install environment RedditReader

    5) Run 'python -m ipykernel install --user --name RedditReader --display-name "Python (RedditReader)"' to install the environment into Jupyter Notebook (please note single hashes(') are used to denote the required command - command ends with a ")

If you are unable to install the dependencies via the above method, the required dependencies are listed in environment.yml. Most of the dependencies come native or with the below installed dependencies. The only dependencies needed to be installed(WARNING! I have not been able to verify this. I highly recommend the dependencies are installed via environment.yml):

    matplotlib
    praw
    numpy
    pandas

### Getting Started

Once you have the environment created, you must put the Reddit login credentials into "logstuff.env" in the main folder. The structure of the logfile is mimicked in "samplelogstuff.env". It is possible to create your own logfile with this information by following this link: https://www.geeksforgeeks.org/how-to-get-client_id-and-client_secret-for-python-reddit-api-registration/. You can paste the information into "samplelogstuff.env" and then rename the file to "logstuff.env" for simplicity's sake.

After you have your login credentials, you can open the .ipynb files in Jupyter Notebook (or whatever .ipynb file editor you prefer) and run them! The project already contains .csv files for RedditVisualizer.ipynb to read, so it is unnecessary to run Reddit.ipynb. If you prefer current data, you must first let Reddit.ipynb complete before you can run RedditVisualizer.ipynb.


### How the project works

Data is scraped off the Reddit API from the top 25 threads in https://reddit.com/r/politics/hot. That data is stored into .csv files for RedditVisualizer.ipynb to use. Currently, it is only using "out.csv". Cumulative data is also set up to be stored into "cumulativeout.csv" for further functionality; but it is not currently used within the project.

Any errors received banned/shadowbanned accounts are logged into bannedaccounts.txt with some relevant information. It is possible this logfile will be renamed and include more robust information in the future.



### Code Louisville Requirements

Requirements completed out of each section:

Category 1: Python Programming Basics:
    - Create a dictionary or list, populate it with several values, retrieve at least one value, and use it in your program.

Category 2: Utilize External Data:
    - Read data from an external file, such as text, JSON, CSV, etc, and use that data in your application.
    - Connect to an external/3rd party API and read data into your app

Category 3: Data Display
    - Visualize data in a graph, chart, or other visual representation of data.
    - Use a Jupyter notebook to document your data analysis 
    - Use Plotly or Matplotlib to create charts/graphs of data


Category 4: Best Practices
    - Implement a log that records errors, invalid inputs, or other important events and writes them to a text file.
    - The program should utilize a virtual environment and document library dependencies in a requirements.txt file.
    - Source data should not be modified/changed - clean data should be stored separately.


### Project Future

The immediate future of this project is refactor a few things. Reddit needs to be a .py files so it is easily run be by a Task Manager. BannedAccounts.txt can be refactored into a more informative, robust logfile. Code can be refactored into loops which can be reused. Code can be set to loop through the Reddit API function to pull all comments, instead of just the top level comments. Login credentials will be added to RedditVisualizer, to allow it API functionality within that particular file(instead of relying on Reddit.ipynb for all data collection. This would allow me to perform higher level analysis on commenters I single out from initial data collection).

After that, I need collect data consistently over a longer time period within cumulativeout.csv, and see what interesting trends emerge. I hope from there I can make a more informative decision on how to maniuplate any future data in order to come to more concrete conclusions.

### Thanks!

Thank you very much to thre creators of Reddit for giving me the (poop)show to perform my work on. Thank you to the intrepid creators of the Public Reddit API Wrapper (PRAW) for making sense out of the automated Reddit documentation. Thank you to all my classmates for the help, emotional support, banter, and their overall contribution to make my (and everyone else in class's) lives better. An extra special shoutout to our mentors Moses Wynn and Will Tirone(for the second time! You savage!) for taking the time out of their busy lives in order to coddle those of us needing the help. I cannot thank you two enough in a public text file, and can never convey the respect and appreciation I have for your sacrifices. Double extra shoutout to the furry felines of theirs that created our class it's own personal r/eyebleach section.

Thanks to Code Louisville for all it has done to support prospective programmers like myself throughout the years. It has provided a pivotal role in the careers of hundreds of students over the years. I hope it is able to continue fulfilling it's Life's Mission for many years to come.


