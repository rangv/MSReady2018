# DAI-DP308 Take it to the Edge!  (IoT Edge, AI, Machine Learning and Cognitive Services )

Azure IoT Edge is an Internet of Things (IoT) service that builds on top of IoT Hub. This service is meant for customers who want to analyze data on devices, a.k.a. "at the edge", instead of in the cloud. By moving parts of your workload to the edge, your devices can spend less time sending messages to the cloud and react more quickly to changes in status.

Azure IoT Edge moves cloud analytics and custom business logic to devices so that your organization can focus on business insights instead of data management. Enable your solution to truly scale by configuring your IoT software, deploying it to devices via standard containers, and monitoring it all from the cloud.

<iframe src="https://channel9.msdn.com/Shows/Internet-of-Things-Show/Kubernetes-integration-with-Azure-IoT-Edge/player" width="480" height="270" allowFullScreen frameBorder="0"></iframe>

## Standup Edge enabled VM on Azure

For this workshop you will standup Data Science Ubuntu VM and this VM will be the IoT Edge Device.

Go to [Github Project](
https://github.com/Azure/DataScienceVM/tree/master/Extensions/Iot
) and click **Deploy To Azure**. This will install a Data Science VM which is IoT Edge enabled.

![VM Deployment](images/vmdeployment.png)

Fill out the above form and click **Purchase**. For this workshop create a new IoT Hub for each VM you create.

Once the deployment is completed go to the resource group created and you will see a VM and IoT Hub have been created.

Click on the VM deployed and copy the public IP of the VM

![publicip](images/ssh.png)

SSH into the VM using Cloud Shell

![Cloud Shell](images/cloudshell.png)

You will SSH into the VM from here

![SSH Prompt](images/sshprompt.png)

SSH into VM

![SSH into VM](images/sshintovm.png)

Go to /home/"user"/IotEdge

![Script](images/iotedge.png)

Run

```code
$ bash edge_configure.sh
```

![Device Login](images/devicelogin.png)

You will bbe prompted to open a browser and device login. Enter the code provided in the browser and when prompted to login enter your user and password.

After login is complete in the cloud shell if you have multiple subscriptions make sure your subscription is set to the one where your VM is deployed. Otherwise use the following command and set the subscription where the VM is deployed.

```code
az login
az account set -s "subscription id"
## To set the correct one
```

Make sure VM is configured to be edge device

Run

```code
iotedge list
```

![IoTEdge List](images/iotedgelist.png)

Check that your device is paired with Iot Hub

![IoTEdge List](images/iothubedge.png)

![IoTEdge List](images/deviceconnected.png)
