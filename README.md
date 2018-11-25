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

## Google App Engine
<i><a href="https://cloud.google.com/appengine/">App Engine</a> is a powerful platform to build apps and scale automatically.</i>
<ol>
  <li>In the Compute Section of the console select App Engine and then select your language (example Python)</li>
  <li>Select region</li>
  <li>Follow the App Engine Quick Start tutorial (Python)
    <ul>
      <li>In the gcloud console in the browser clone the <a href="https://github.com/GoogleCloudPlatform/python-docs-samples">Python GCP Repo</a> and cd into python-docs-samples/appengine/standard_python37/hello_world</li>
      <li>Create an isolated Python environment to test
          <pre>
          <code>
          virtualenv --python python3 \
          ~/envs/hello_world
          </pre>
          </code>
      </li>
      <li>Activate the new virtual environment
        <pre>
        <code>
        source \
        ~/envs/hello_world/bin/activate
        </code>
        </pre>
      </li>
      <li> Pip install all dependencies
        <pre>
        <code>
        pip install -r requirements.txt
        </code>
        </pre>
      </li>
      <li> Run app using Flask development server
        <pre>
        <code>
        python main.py
        </code>
        </pre>
      </li>
      <li>Deploy App
        <pre>
        <code>
        gcloud app deploy app.yaml --project \
        gcp-lynda-course
        </code>
        </pre>
      </li>
    </ul>
  </li>
</ol>

## Google Cloud Storage
<i><a href="https://cloud.google.com/storage/">Cloud Storage</a> is a unified object storage for developers and enterprises</i>
<ol>
  <li>In the Storage Section of the console select Storage</li>
  <li>Click create bucket and set a storage class</li>
  <li>Test with <a href="https://developers.google.com/apis-explorer/#p/storage/v1/">Cloud Storage JSON API Explorer</a></li>
</ol>

## Google Cloud SQL
<i><a href="https://cloud.google.com/sql/">Cloud SQL</a> is a fully-managed database service that makes it easy to set up, maintain, manage, and administer your relational PostgreSQL and MySQL databases in the cloud</i>
<ol>
  <li>In the Storage Section of the console select SQL</li>
  <li>Create instance and select either MySQL or PostgreSQL</li>
  <li>Select 2nd Generation (Recommended) or 1st Generation (Legacy)</li>
  <li>Set Instance ID and password and then create</li>
</ol>

