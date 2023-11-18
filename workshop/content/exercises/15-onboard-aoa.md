Install the Aria Operations for Applications dashboard for Tanzu Application Platform (beta)

###### Prerequisites: 

* Before integrating a Kubernetes cluster with AOA you must have:

    * AOA Wavefront access with permissions to integrate Kubernetes clusters and view dashboards
    * A Kubernetes cluster with Tanzu Application Platform installed
 
###### To integrate with AOA:

Log in to your AOA instance, click the **INTEGRATIONS** tab, and then click **Kubernetes**.

Click **ADD AN INTEGRATION INSTANCE** on the next page.

* Fill out the Kubernetes Integration Setup page:

    * Select Kubernetes Cluster as the distribution type.
    * Type the cluster name in the Cluster Name text box.
    * Enable Logs.
    * Enable Metrics.
    * Configure authentication. If the token is not listed, verify that you have AOA Wavefront access.
    * Run the kubectl commands in the Deployment Script text box on the cluster that you want to onboard.

###### Set up metrics collection in a cluster

* Apply the included tap-metrics.yaml file to the onboarded cluster, which enables the collection of Tanzu Application Platform **CustomResource** metrics, by running:

```execute-1
kubectl apply -f $HOME/tap-metrics.yaml
```

##### Create the dashboard in AOA Wavefront

* Go to the AOA Wavefront home page and then click **Dashboards** > **Create Dashboard**.

* Click JSON in the upper right corner.

* Click Tree > Code and extract the downloaded content from tap-health-dashboard.json.

* Copy the content from tap-health-dashboard.json into the code block and then click ACCEPT.

* Click SAVE in the top right corner to save the dashboard.

* In the search text box, type the name of the cluster that you onboarded and select it from the list of available clusters.
