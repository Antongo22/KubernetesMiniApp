<h1>KubernetesMiniApp</h1>

<p>This project demonstrates how to deploy a FastAPI application using Docker and Minikube. Follow the instructions below to set it up on your local machine.</p>

<h2>Prerequisites</h2>

<p>Make sure you have the following tools installed:</p>
<ul>
    <li><a href="https://www.docker.com/get-started">Docker</a></li>
    <li><a href="https://minikube.sigs.k8s.io/docs/start/">Minikube</a></li>
    <li><a href="https://kubernetes.io/docs/tasks/tools/install-kubectl/">kubectl</a></li>
</ul>

<h2>Getting Started</h2>

<h3>Step 1: Start Minikube</h3>
<p>Open your terminal and run the following command to start Minikube:</p>
<pre><code>minikube start</code></pre>

<h3>Step 2: Build the Docker Image</h3>
<p>Next, build the Docker image for your FastAPI application by navigating to the project directory and running:</p>
<pre><code>docker build -t myfastapiapp .</code></pre>

<h3>Step 3: Load the Image into Minikube</h3>
<p>Load the built Docker image into Minikube with the following command:</p>
<pre><code>minikube image load myfastapiapp:latest</code></pre>

<h3>Step 4: Verify the Image</h3>
<p>To ensure that the image is loaded correctly, run:</p>
<pre><code>minikube ssh -- docker images | grep myfastapiapp</code></pre>

<h3>Step 5: Apply Kubernetes Configurations</h3>
<p>Apply the service and deployment configurations by running:</p>
<pre><code>kubectl apply -f service.yaml</code></pre>
<pre><code>kubectl apply -f deployment.yaml</code></pre>

<h3>Step 6: Check Pod Status</h3>
<p>Check that your pods are running correctly:</p>
<pre><code>kubectl get pods</code></pre>

<h3>Step 7: Get Minikube IP</h3>
<p>Retrieve the Minikube IP address:</p>
<pre><code>minikube ip</code></pre>

<h3>Step 8: Access the Application</h3>
<p>You can access your FastAPI application by navigating to:</p>
<pre><code>http://&lt;minikube_ip&gt;:30001/</code></pre>
<p>Replace <code>&lt;minikube_ip&gt;</code> with the actual IP address you retrieved in the previous step.</p>

<h3>Optional Configuration</h3>
<p>If you wish to change ports or configurations, you can modify the <code>service.yaml</code> and <code>deployment.yaml</code> files as needed.</p>
