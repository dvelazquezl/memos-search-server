# Solr Configuracion and Setup

# 1. Solr Setup
* Install **OpenJDK 17** (recommended by Apache to run Solr) with **sudo apt install openjdk-17-jdk**.
* Download **Apache Solr 9.6.1** (version used and tested in the project) from the official page -> https://solr.apache.org/downloads.html.
* Unzip the file to a safe folder to run it. E.g like /home.
* Go to the **bin** folder inside the solr folder and open Terminal there.
* Execute this **sudo ./install_solr_service.sh "../../solr-9.6.1.tgz"** in Terminal. (where "../../solr-9.6.1.tgz" is the path to our Zip file)
* Now Solr should be installed as a service in your system.

# 2. Solr Configuracion
* Open Terminal and execute **sudo -su solr /opt/solr-9.6.1/bin/solr create -c "production"**.
* Copy the **sunspot** folder from this repository to **var\solr\data\configsets** (if the **configsets** folder does not exit, create it).
* Open the **core.properties** file located at **var\solr\data\production** and add the following line: **configSet=sunspot**.
* Restart the solr service from terminal with: **sudo service solr restart**.