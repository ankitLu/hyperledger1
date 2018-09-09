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
          <li> <b> Install GO Programming Language </b> </li>
          <li> <b> Install Node.js Runtime and NPM </b> </li>
          <li> <b> Install Python </b> </li>
  
  
      </ol>
      
   </ol>

