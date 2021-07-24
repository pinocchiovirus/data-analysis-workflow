[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=pinocchioVirus_sideProject&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=pinocchioVirus_sideProject)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=pinocchioVirus_sideProject&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=pinocchioVirus_sideProject)
[![Code Smells](https://sonarcloud.io/api/project_badges/measure?project=pinocchioVirus_sideProject&metric=code_smells)](https://sonarcloud.io/dashboard?id=pinocchioVirus_sideProject)
[![Duplicated Lines (%)](https://sonarcloud.io/api/project_badges/measure?project=pinocchioVirus_sideProject&metric=duplicated_lines_density)](https://sonarcloud.io/dashboard?id=pinocchioVirus_sideProject)
[![Bugs](https://sonarcloud.io/api/project_badges/measure?project=pinocchioVirus_sideProject&metric=bugs)](https://sonarcloud.io/dashboard?id=pinocchioVirus_sideProject)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=pinocchioVirus_sideProject&metric=security_rating)](https://sonarcloud.io/dashboard?id=pinocchioVirus_sideProject)
[![Vulnerabilities](https://sonarcloud.io/api/project_badges/measure?project=pinocchioVirus_sideProject&metric=vulnerabilities)](https://sonarcloud.io/dashboard?id=pinocchioVirus_sideProject)

# Dashboard using CI/CD and Containerization Methodology
Side Project to Automate the Proccess of Data Extraction, Transformation, Loading and importing it into DB, to Build a Dashboard for Covid-19 and Analyzing it using Google Data Studio with Our Automated Data.

### Tech Used in This Project:
- Databases (SQLlite3, PostgreSQL)
   - Storge, Backuup
- Google Data Studio (Dashboard) and Jupyter Notebook (Analysis)
- Github Actions (CI/CD) and SonarCloud (Code Quality and Code Security) 
- Python 3.8+ (Language)
   - All Packages Used are Found In : requirements.txt
- Sublime Text (Code Editor) and Jupyter-Notebook (Data Analysis and Engineering) 
- Containerization (Docker, Docker Compose)
   - Containerizing, Configuration of Multi-Containers
- Ubuntu 20.04+ (OS) 
   - Local Laptop, Docker Image

### You can run the project by running the following commands (Inside code/ Folder), after reading the requirements here:
Before you run the code, make sure to set your sql instance configurations if you want to connect to other DB service provider or LocalDB (Like PostgreSQL/MySQL/MSSQL) in the following file:
```python
code/configurations/SQL_Config.py
``` 
Then after adding your configurations (Or if you want to use SQLite3 as your storge db edit/add on the transferData.py file) and downloaded needed packages (requirements.txt), excute the code script to import data into the database (the dataset is scheduled to be automaticly downloaded and transfered to the database using github actions schedule for every 40min ksa/riyadh time and you can change in this file (.github/workflows/main-analysis.yml)). 

Also github actions are connected to sonarcloud for code security and code quality, and scheduled for every 45min which means after 5min from the code is pushed to the repo and makes checks to the whole project, if the code has faild on the SonarCloud (Quality Gate) it will not pushed to the next step on the pipline and this makes the proccess of catching errors more easy and fun!

### To run the project first, make sure to run the following command to install and save the data to the dataset folder , also make sure you are in the right path (cd code/) then run this command:
```python
python3 code/etl_data.py
```

### We have the dataset and we are ready now to import the data into our database, by running the following command:
```python
python3 code/transfer_data.py
```

### Finally, you can automate the proccess by running a shell script to automatically run both file codes and create sql file in case you have another database to import into it, without needing to take the same proccess to insert data and you just have to import into the database the generated sql file (make sure you make the shell file excutable by using this command: chmod +x converter.sh) by running the following command:
```python
./converter.sh
```

### Link To The Dashboard & Blog Post:
<table class="tg">
  <tr>
    <th class="tg-yw4l"><b>Name</b></th>
    <th class="tg-yw4l"><b>Description</b></th>
    <th class="tg-yw4l"><b>Link</b></th>
  </tr>
  <!-- Dashboard Links -->
  <tr>
    <td class="tg-yw4l">Covid Dashboard</td>
    <td class="tg-yw4l">Dashboard of Saudi Arabia Cases and vaccinations rates in real-time</td>
    <td class="tg-yw4l">Dashboard<a href="#">
      <p>#</p>
    </a></td>
  </tr>
  <!-- Blog Post Links -->
  <tr>
    <td class="tg-yw4l">Blog Post</td>
    <td class="tg-yw4l">Blog Post on How to Setup Automation ETL Proccess for Data Analysis</td>
    <td class="tg-yw4l">Blog<a href="#">
      <p>#</p>
    </a></td>
  </tr>
</table>
