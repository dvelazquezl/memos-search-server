# Solr Configuracion and Setup for Ubuntu

# 1. Solr Setup
* Install **OpenJDK 17** (recommended by Apache to run Solr) with **sudo apt install openjdk-17-jdk**.
* Download **Apache Solr 9.6.1** (version used and tested in the project) from the official page -> https://solr.apache.org/downloads.html.
* Unzip the file to a safe folder with **tar xzf solr-9.6.1.tgz**.
* Go to the **bin** folder inside the solr folder and open Terminal there.
* Execute this **sudo ./install_solr_service.sh "../../solr-9.6.1.tgz"** in Terminal. (where "../../solr-9.6.1.tgz" is the path to your Zip file)
* Now Solr should be installed as a service in your system.

# 2. Solr Configuracion
* Open Terminal and execute **sudo -su solr /opt/solr/bin/solr create -c production**.
* Create the **configsets** folder with **sudo mkdir /var/solr/data/configsets**.
* Copy the **sunspot** folder from this repository with **sudo cp -r path-to-repo/sunspot /var/solr/data/configsets**. (edit path-to-repo with your current path)
* Execute **sudo nano /var/solr/data/production/core.properties** then add the following line at the end: **configSet=sunspot**.
* Restart the solr service from terminal with: **sudo service solr restart**.

## More Information
https://solr.apache.org/guide/solr/latest/getting-started/introduction.html