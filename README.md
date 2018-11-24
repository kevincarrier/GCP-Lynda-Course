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

## Google Kubernetes Container Engine
<i><a href="https://cloud.google.com/kubernetes-engine/">Kubernetes Engine</a> is a managed, production-ready environment for deploying containerized applications.</i>
<ol>
  <li>In the Compute Section of the console select Kubernetes Engine and then Create</li>
  <li>Keep all defaults and then create</li>
  <li>Follow the Create a Guestbook with Redis and PHP tutorial
    <ul>
      <li>In the gcloud console in the browser clone the <a href="https://github.com/kubernetes/examples">Kubernetes Repo</a> and cd into guestbook</li>
        <li>Setup gcloud and kubernetes credentials
          <pre>
          <code>
          gcloud container clusters \
          get-credentials <cluster-name> \
          --zone <cluster-zone>
          </code>
          </pre>
        </li>
        <li>Deploy the master controller
          <pre>
          <code>
          kubectl create -f \
          redis-master-deployment.yaml
          </pre>
          </code>
        </li>
        <li>Verify the redis master pod is running
          <pre>
          <code>
          kubectl get pods 
          </pre>
          </code>
        </li>
        <li>Create the redis master service
          <pre>
          <code>
          kubectl create -f \
          redis-master-service.yaml
          </pre>
          </code>
        </li>
        <li>Verify the service created successfully
          <pre>
          <code>
          kubectl get service
          </pre>
          </code>
        </li>
        <li>Deploy a slave controller
          <pre>
          <code>
          kubectl create -f \
          redis-slave-deployment.yaml
          </pre>
          </code>
        </li>
        <li>Create the redis salve service
          <pre>
          <code>
          kubectl create -f \
          redis-slave-service.yaml
          </pre>
          </code>
        </li>
        <li>Verify the service created successfully
          <pre>
          <code>
          kubectl get service
          </pre>
          </code>
        </li>
        <li>Create the guestbook frontend
        <pre>
          <code>
          kubectl create -f \
          frontend-deployment.yaml;
          <br/>
          sed -i -e 's/NodePort/LoadBalancer/g' \
          frontend-service.yaml;
          <br/>
          kubectl create -f \
          frontend-service.yaml;
          </pre>
          </code>
        </li>
        <li>List all fo the services and look for the front end. Wait for it to go an extranl IP and then visit the running site.
        kubectl get services --watch
        </li>
      </li> 
    </ul>
  </li>
</ol>


