# Apache Tomcat Installation And Setup In AWS EC2 Redhat Instance.
<h3> Prerequisite </h3>
<ul>
<li> 	AWS Acccount. </li>
<li> Create Redhat EC2 T2.micro Instance. </li>
<li> Create Security Group and open Tomcat ports or Required ports.
	<ul>
		<li>  	8080 ..etc </li>
	</ul>
	</li>
<li>  Attach Security Group to EC2 Instance. </li> 
<li>  Install java openJDK 1.8+ </li>
</ul>
<h1> Install Java JDK 1.8+ </h1>
# install Java JDK 1.8+ as a pre-requisit for tomcat to run.
<dl> <dd> sudo hostnamectl set-hostname tomcat </dd>
<dd> cd /opt </dd>
<dd> sudo yum install git wget -y </dd>
<dd> sudo yum install java-1.8.0-openjdk-devel -y </dd>
# install wget unzip packages.
<dd> sudo yum install wget unzip -y </dd>
</dl>


<h1> Install Tomcat version 10.1.7 </h1>
<h3> Download and extract the tomcat server </h3>
<dl> sudo wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.1.7/bin/apache-tomcat-10.1.7.tar.gz
<dd> sudo tar -xvf apache-tomcat-10.1.7.tar.gz </dd>
<dd> sudo rm -rf apache-tomcat-10.1.7.tar.gz </dd>
### rename tomcat for good naming convention </dd>
<dd> sudo mv apache-tomcat-10.1.7 tomcat10 </dd>
### assign executable permissions to the tomcat home directory </dd>
<dd> sudo chmod 777 -R /opt/tomcat10 </dd>
<dd> sudo chown ec2-user -R /opt/tomcat10 </dd>
### start tomcat </dd>
<dd> sh /opt/tomcat10/bin/startup.sh </dd>
# create a soft link to start and stop tomcat </dd>
# This will enable us to manage tomcat as a service </dd>
<dd> sudo ln -s /opt/tomcat10/bin/startup.sh /usr/bin/starttomcat </dd>
<dd> sudo ln -s /opt/tomcat10/bin/shutdown.sh /usr/bin/stoptomcat </dd>
<dd> starttomcat </dd>
<dd> sudo su - ec2-user </dd> </dl>
