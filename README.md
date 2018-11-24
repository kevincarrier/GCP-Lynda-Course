# Google Cloud Platform Course on Lynda
Lynda Course: https://www.lynda.com/Google-Cloud-Platform-tutorials/Google-Cloud-Platform-Essential-Training/540539-2.html

Google Cloud Tools: https://cloud.google.com/docs/overview/developer-and-admin-tools

## Install Cloud SDK
<ol>
  <li>Go to https://cloud.google.com/sdk/docs/ and install the latest version of Cloud SDK.</li>
  <li>If you do not have a version of Python 2 that is 2.7.9 or later install Python 2.</li>
  <li>Once completely installed a gcloud init command will be run and you will need to sign in with your google account</li>
  <li>Some useful gcloud commands
    <ul>
      <li>gcloud init <my-project></li>
      <li>gcloud --version</li>
      <li>gcloud info --show-log</li>
      <li>gcloud auth login</li>
      <li>gcloud config set project <my-project-id></li>
    </ul>
  </li>
</ol>

## Google Compute Engine
<i><a href="https://cloud.google.com/compute/">Compute Engine</a> is a cloud-hosted virtual machine</i>
<ol>
  <li>In the Compute Section of the console select Compute Engine and then Create</li>
  <li>Keep all defaults and then create</li>
  <li>Once set up connect via SSH by selecting the Open in Browser Window in the Connect column</li>
  <li>Setup a snapshot by selecting snapsnot and then selecting the instance.</li>
</ol>
<i><a href="https://cloud.google.com/marketplace/">Cloud Launcher/Marketplace</a> is a preconfigured cloud-hosted virtual machine with applications</i>
<ol>
  <li>Select Marketplace and then select WordPress</li>
  <li>Select Launch on Compute Engine</li>
  <li>Keep defaults and Deploy</li>
  <li>Now you can view the Wordpress Public and Admin Page</li>
</ol>


  
