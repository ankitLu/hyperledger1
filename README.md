# hyperledger1
Creating a first hyperledger fabric network through Amazon AWS

<ol> <li><b> create an AWS account </b> </li>
  <p> I created an AWS student account through www.awseducate.com </p>
  <p> Through your workbench, go to AWS console and create an EC2 instance</p>
  <p> Go to Services-> ec2-> launchinstance-> Ubuntu Server 16.04 LTS (HVM), SSD Volume Type-> m4large </p>
  <p> Add tag->basicnetwork, Create a new key-pair, Download key pair and click launch instance </p>
  
  <li><b> Connecting to the instance </b> </li>
  <p> Once the instance has started, you can connect it through Putty</p>
  <p> Before connecting, convert the .pem file (key pair) into .ppk file using PuttyGen. This step is required because Putty requires a .ppk file and cannot connect using .pem file </p>
  <p> Now add .ppk file to Putty, and connect to the IP of the running AWS instance </p>
  
  <li><b> Creating first network - installing prerequisites </b> </li>
      <ol> <li> <b> Install cURL </b> </li> 
                    <p> Type on the terminal cURL command to check if its installed or run cURL --version. If it is not installed                           you can install it through below command </p>
  <p> sudo apt-get install curl </p>
  <li> <b> Install Docker and Docker Compose </b> </li>
  <p> I followed this article: https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04 </p>
    and <p> https://www.digitalocean.com/community/tutorials/how-to-install-docker-compose-on-ubuntu-18-04 </p>
  <li> <b> Install GO Programming Language </b> </li>
          <p> Run the command sudo curl -O https://storage.googleapis.com/golang/go1.9.1.linux-amd64.tar.gz </p>
          <p> Easy article explanation here https://medium.com/@patdhlk/how-to-install-go-1-9-1-on-ubuntu-16-04-ee64c073cd79 </p>
          <p> Don't forget to set the path. Run command export PATH=$PATH:$GOPATH/bin </p>
          <li> <b> Install Node.js Runtime and NPM </b> </li>
           <p> https://websiteforstudents.com/install-the-latest-node-js-and-nmp-packages-on-ubuntu-16-04-18-04-lts/ </p>
          <li> <b> Install Python </b> </li>
          <p> Retrieve the Python version 2.7, which is goof for running Fabric Node.js SDK, by using command sudo apt-get install python </p>
          <p> You can also check python version by command "python --version" </p>
          <p> You are essentially done for installing the prerequisites. You can refer to detailed installation article here 
          https://hyperledger-fabric.readthedocs.io/en/latest/prereqs.html </p>
          </ol>
  <li> <b> Installing Sample Binaries and Docker Images </b> </li>
  <p> Once you are ready, and in the directory into which you will install the Fabric Samples and binaries, go ahead and execute the following command:
curl -sSL http://bit.ly/2ysbOFE | bash -s 1.2.0 </p>
<p> then, curl -sSL http://bit.ly/2ysbOFE | bash -s <fabric> <fabric-ca> <thirdparty>
  curl -sSL http://bit.ly/2ysbOFE | bash -s 1.2.0 1.2.0 0.4.10 </p>
  <p> I faced an issue of Docker permission denied while trying to connect to the Docker daemon socket </p>
  <p> I solved the issue with command sudo usermod -a -G docker $USER . Don't forget to completely log out of your account and log back in (if in doubt, reboot!):</p>
  <p> Detailed solution at: https://techoverflow.net/2017/03/01/solving-docker-permission-denied-while-trying-to-connect-to-the-docker-daemon-socket/ </p>
  <li> <b> Running first network </b> </li>
  <p> cd fabric-samples/first-network </p>
  <p> Ready to give it a go. Run the command: ./byfn.sh generate </p>
  <p> This command generates all the certificates. And after this, bring up the network </p>
  <p> ./byfn.sh up </p>
  <p>  If you’d like to run through this tutorial with node chaincode, pass the following command instead:

<i> we use the -l flag to specify the chaincode language </i>
<i> forgoing the -l flag will default to Golang </i>

./byfn.sh up -l node </p>
<p> Bring down the network with the command ./byfn.sh down </p>
  

