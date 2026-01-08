# Greenhouse World Creation

## Prerequistes
In order to install and use the NVIDIA Isaac Sim assets, it is necessary that Isaac Sim is fully installed on said computer and be able to run via the **./isaac-sim.sh** command from the terminal.

## 1. NVIDIA Isaac Sim Assets Installation
The NVIDIA Isaac Sim Assets came in a pack of three and can be downloaded from https://docs.isaacsim.omniverse.nvidia.com/latest/installation/download.html. The Warehouse creator also uses part of these assets to generate warehouses. The first task is to set up the asset packs. Isaac Sim Local Assets Packs are available to be used locally and in an air-gapped environment. For 4.5.0, the total assets are split into three packs. All three packs are required for local use.
1. Download all three packs of Isaac Sim Assets from the Latest Release section.
2. Unzip the packages to a folder. All three asset packs are required, and they need to be combined into a single root folder (e.g., home/isaacsim_assets/Assets/Isaac/4.5). This root folder (~/isaacsim_assets/Assets/Isaac/4.5) must contain both the NVIDIA and Isaac folders.
3. Edit the /home/username/isaacsim/apps/isaacsim.exp.base.kit file and add the settings below:

<pre> [settings] 
  persistent.isaac.asset_root.default = "/home/&lt;username&gt;/isaacsim_assets/Assets/Isaac/4.5" 
  exts."isaacsim.asset.browser".folders = [ 
    "/home/&lt;username&gt;/isaacsim_assets/Assets/Isaac/4.5/Isaac/Robots",
    "/home/&lt;username&gt;/isaacsim_assets/Assets/Isaac/4.5/Isaac/People",
    "/home/&lt;username&gt;/isaacsim_assets/Assets/Isaac/4.5/Isaac/IsaacLab",
    "/home/&lt;username&gt;/isaacsim_assets/Assets/Isaac/4.5/Isaac/Props",
    "/home/&lt;username&gt;/isaacsim_assets/Assets/Isaac/4.5/Isaac/Environments",
    "/home/&lt;username&gt;/isaacsim_assets/Assets/Isaac/4.5/Isaac/Materials",
    "/home/&lt;username&gt;/isaacsim_assets/Assets/Isaac/4.5/Isaac/Samples",
    "/home/&lt;username&gt;/isaacsim_assets/Assets/Isaac/4.5/Isaac/Sensors",
  ]</pre>

  The screenshot below shows the final file after adding the settings.
  
  ![Screenshot from 2025-06-02 10-28-59](https://github.com/user-attachments/assets/da9b8ba5-9927-417f-9085-afbcff39afff)

  4. Run Isaac Sim with the flag below to use the local assets. It is neccessary to do this first time of loading the assets, subsequently, there will be no need.
     <pre>./isaac-sim.sh --/persistent/isaac/asset_root/default="/home/<username>/isaacsim_assets/Assets/Isaac/4.5"</pre>
In the Isaac Sim app, to verify access to the assets, go to the Isaac Sim Assets Browser tab. Then click the “Gear” icon and select Check Default Assets Root Path.
![Screenshot from 2025-06-02 10-31-01](https://github.com/user-attachments/assets/1137c852-932b-4404-9c5b-bf4d9df2eb9f)

## 2. Loading an Already Created World

A .usd file can easily be loaded on Isaac Sim by navigating to the file option in the menu bar or using the file browser window. Navigate to the location of the usd file and right-click to open.

![image](https://github.com/user-attachments/assets/f923315c-bc12-4692-9fe4-09adb536b006)

## 3. NVIDIA Isaac Sim Warehouse Extension Building

The Warehouse Creator (https://docs.omniverse.nvidia.com/digital-twins/latest/warehouse-ext.html, https://docs.omniverse.nvidia.com/isaacsim/latest/features/warehouse_logistics/ext_omni_warehouse_creator.html ) is an extension for KIT-based apps (like Omniverse USD Composer) that allows users to quickly get started with building Warehouse Digital Twins in an automated way. It supports procedurally generating full warehouse scenes, as well as customized generation based on layouts and assets that you want in the scene.

**Installing and Enabling the Extension**

The extension can be installed/enabled by
1. Navigating to **Window > Extensions Manager** from the top-level menu
2. Search for Warehouse Creator in the text field of the Extension Manager window to reveal the Omni.warehouse_creator result.
3. Click the toggle to enable the extension.

![Screenshot from 2025-06-02 10-08-24](https://github.com/user-attachments/assets/db0ce1d1-4913-4ea9-b58e-fffba02a7138)

**Using the Warehouse Extension**

Start by navigating to **Tools > Modular Warehouse Creator**. Verify that you see:
In the Instructions tab, there is a brief description on how to use it.

![Screenshot from 2025-06-02 10-12-00](https://github.com/user-attachments/assets/ab8faa4a-9865-4fab-a276-0380cc25ad62)

![Screenshot from 2025-06-02 10-13-12](https://github.com/user-attachments/assets/d654fffb-b6df-4190-97a1-afc7dfd21e46)

**Challenges with the Warehouse Extension**

The warehouse uses assets from the NVIDIA Isaac Sim to automatically generate warehouse structures, though this can also be done manually; the extension makes things easier. Due to the automation process, the extension requires a good amount of GPU memory to properly render assets. With the current setup of 4 GB of GPU memory, the device runs out of memory, as shown in the screenshot below.

![Screenshot from 2025-06-02 11-44-58](https://github.com/user-attachments/assets/5e370905-b656-4aad-bc96-d3e1498a140e)

## 4. Creating a Greenhouse from the Asset

The NVIDIA Isaac Sim assets contain lots of modular and full assets that can be utilized to create any building structure. The structure of the final output depends on the developer's creativity and the required output. The assets are categorized into environments, people, props, samples, robots, etc

![image](https://github.com/user-attachments/assets/53537b43-7fd4-4b3c-ae31-f3bf4e08cc69)

A greenhouse can be constructed using the following procedures:
1. Click on the **Isaac Sim Assets** from the folders bar and select **Samples**
   
![image](https://github.com/user-attachments/assets/31a0d188-e1f3-4cf6-b319-64b84607b8f4)

3. Scroll through the list to see available assets. Assets with the name format "SM_WarehouseEnd_A1_01" can be selected; there are also other variants, such as the middle piece and the opposite end.
4. After selecting an asset, it can be added as a reference to the existing scene or opened as an individual file, as highlighted by the opened context window. To examine an asset, open it as an individual file, and add it to the current world, load it as a reference

![image](https://github.com/user-attachments/assets/c4a3d57b-e837-4eed-ab0f-abf96690c75e)

Loaded assets will be displayed on the main screen and can be edited or modified as required.

![image](https://github.com/user-attachments/assets/c97839b1-a9d0-4056-b810-068538cf2afe)

### Challenges with using the Warehouse Assets

The warehouse uses assets from the NVIDIA Isaac Sim to automatically generate warehouse structures, though this can also be done manually; the extension makes things easier. Due to the automation process, the extension requires a good amount of GPU memory to properly render assets. With the current setup of 4 GB of GPU memory, the device runs out of memory, as shown in the screenshot below.

![Screenshot from 2025-06-02 11-44-58](https://github.com/user-attachments/assets/5b6ad3dc-8244-4403-9e0c-aac08467c8d7)

### Possible Solutions

1. Cloud Deployment
   
   Isaac Sim is offered as a container that runs locally or on NVIDIA RTX-equipped Amazon Web Services (AWS), Microsoft Azure, Google Cloud Platform (GCP), Tencent Cloud, or Alibaba Cloud with the ability to stream the application directly to your desktop. This cloud-based delivery provides the latest RTX graphics and performance to any desktop system without requiring local NVIDIA RTX GPUs.

The Isaac Automator (https://github.com/isaac-sim/IsaacAutomator ) is an advanced tool that helps to automate a custom Isaac Sim deployment to public clouds. This tool allows you to access Isaac Sim instances via SSH, a web-based VNC client, and remote desktop clients. AWS, Azure, GCP, and Alibaba Cloud are supported.

The link above provides a tool to help automate the cloud deployment of Isaac Sim on various cloud platforms.

2. Hardware Upgrade
   
   NVIDIA Isaac Sim functions optimally on a computer specifically built for custom configurations. Reading through previous documentations and reviews, a laptop that can provide optimum performance is the Alienware 18 Area-51 Laptop (https://www.dell.com/en-us/shop/dell-laptops/alienware-18-area-51-gaming-laptop/spd/alienware-area-51-aa18250-gaming-laptop#offers-anchor )

## 5. Setting up Isaac Sim on the Cloud Using Isaac Automator

Isaac Automator allows a quick deployment of Isaac Sim and Isaac Lab to the public clouds (AWS, GCP, Azure, and Alibaba Cloud are currently supported).

The result is a fully configured remote-desktop cloud workstation, which can be used for development and testing of the robotic applications within minutes and on a budget. Isaac Automator supports varierty of GPU instances and stop-start functionality to save on cloud costs, provides tools to aid the workflow (uploading and downloading data, autorun, deployment management, etc).


   ## Installation

### Installing Docker

`docker` should be present on your system. Visit <https://docs.docker.com/engine/install/> for installation instructions.

### Obtaining NGC API Key

**NGC API Key** allows you to download docker images from <https://ngc.nvidia.com/>. Please prepare one or obtain it at <https://ngc.nvidia.com/setup/api-key>.

### Building the Container

Please enter the following command in the project root directory to build the container:

#### Linux/MacOS

```sh
./build
```

#### Windows

```sh
docker build --platform linux/x86_64 -t isa .
```

This will build the Isaac Automator container and tag it as `isa`.

## Usage

### Running the Automator Commands

#### Linux/MacOS

On Linux and MacOS there are two ways to run the automator commands:

1. First enter the automator container and then run the command inside the container:

```sh
# enter the automator container
./run
# inside container:
./somecommand
```

2. Simply prepend the command with `./run` like so:

```sh
./run ./somecommand <parameters>
```

for example:

```sh
./run ./deploy-aws
./run ./destroy my-deployment
```

#### Windows

On Windows, you can run the automator commands by entering the container first and then running the command inside the container like so:

(enter the automator container)

```sh
docker run --platform linux/x86_64 -it --rm -v .:/app isa bash
```

(run the command inside the container)

```sh
./somecommand
```

### Deploying Isaac Sim

#### AWS

<details>
  <a name="#aws-permissions"></a>
  <summary>Enabling Access Permissions</summary>

  You need _AmazonEC2FullAccess_ permissions enabled for your AWS user. You can enable those in [Identity and Access Management (IAM) Section](https://console.aws.amazon.com/iamv2/home#/home) in AWS console like so:

  1. Go to <https://console.aws.amazon.com/iamv2/home#/home>
  2. Click "Access Management" \> "Users" in the left menu
  3. Search for your user name
  4. Under "Permissions" tab click "Add permissions"
  5. Choose "Attach existing policies directly"
  6. Search for _AmazonEC2FullAccess_, check the box next to it, click "Next"
  7. Click "Add permissions"
</details>

<details>
  <a name="#aws-access-creds"></a>
  <summary>Getting Access Credentials</summary>
  You will need _AWS Access Key_ and _AWS Secret Key_ for an existing account. You can obtain those in <a href="https://console.aws.amazon.com/iamv2/home#/home">Identity and Access Management (IAM) Section</a> in the AWS console.
</details>

If you have completed the above steps or already have your permissions and credentials set up, run the following command in the project root directory:

```sh
# enter the automator container
./run
# inside container:
./deploy-aws
```

Tip: Run `./deploy-aws --help` to see more options.

##### Using Temporary Credentials

If you are using temporary credentials that may expire and prevent you from deleting the deployment or stopping/starting the instance (e.g. from `aws sts assume-role`), you can manually edit the `/app/state/<deployment-name>/.tfvars` file in the Automator container like so:

```sh
# inside container:
nano /app/state/<deployment_name>/.tfvars
```

Then set the `aws_access_key_id`, `aws_secret_key` and `aws_session_token` variables to the new ones.

#### GCP

```sh
# enter the automator container
./run
# inside container:
./deploy-gcp
```

Tip: Run `./deploy-gcp --help` to see more options.

#### Azure

If You Have Single Subscription:

```sh
# enter the automator container
./run
# inside container:
./deploy-azure
```

If You Have Multiple Subscriptions:

```sh
 # enter the automator container
./run

# inside container:
az login # login
az account show --output table # list subscriptions
az account set --subscription "<subscription_name>"
./deploy-azure --no-login
```

Tip: Run `./deploy-azure --help` to see more options.

#### Alibaba Cloud

<details>
  <a name="#alicloud-access-creds"></a>
  <summary>Getting Access Credentials</summary>
  You will need <i>Access Key</i> and <i>Secret Key</i> for an existing AliCloud account. You can obtain those in <a href="https://usercenter.console.aliyun.com/#/manage/ak">AccessKey Management</a> section in the Alibaba Cloud console.
</details>

Once you have prepared the access credentials, run the following command in the project root directory:

```sh
# enter the automator container
./run
# inside container:
./deploy-alicloud
```

Tip: Run `./deploy-alicloud --help` to see more options.

GPU-accelerated instances with NVIDIA A100, A10 and T4 GPUs are supported. You can find the complete list of instance types, availability and pricing at <https://www.alibabacloud.com/help/en/ecs/user-guide/gpu-accelerated-compute-optimized-and-vgpu-accelerated-instance-families-1>. Please note that vGPU instances are not supported.

### Connecting to Deployed Instances

Deployed Isaac Sim instances can be accessed via:

- SSH
- noVNC (browser-based VNC client)
- NoMachine (remote desktop client)

Look for the connection instructions at the end of the deploymnt command output. Additionally, this info is saved in `state/<deployment-name>/info.txt` file.

You can view available arguments with `--help` switch for the start scripts, in most cases you wouldn't need to change the defaults.

Tip: You can use `./connect <deployment-name>` helper command to connect to the deployed instance via ssh.

### Running Applications

To use installed applications, connect to the deployed instance using noVNC or NoMachine. You can find the connection instructions at the end of the deployment command output. Additionally, this info is saved in `state/<deployment-name>/info.txt` file.

#### Isaac Sim

Isaac Sim will be automatically started when cloud VM is deployed. Alternatively you can click "Isaac Sim" icon on the desktop or run the following command in the terminal on the deployed instance or launch it from the terminal as follows:

```sh
~/isaacsim.sh
```

To get a shell inside Isaac Sim container, click "Isaac Sim Shell" icon on the desktop. Alternatively you can run the following command in the terminal on the deployed instance:

```sh
~/isaacsim-shell.sh
```

### Autorun Script

By default, Isaac Sim will be started when the cloud VM is deployed.

If you want to launch a custom application or script on startup, you can modify the [`uploads/autorun.sh`](uploads/autorun.sh) script (on your local machine). It will either be uploaded to the cloud VM automatically or you can upload it manually using the `./upload` command.

Every time the cloud VM is deployed or started from a stopped state, the `autorun.sh` script will be executed.

This functionality can be useful for running batch jobs, generating data on startup or preparing the environment for the user.

### Mapped Folders

The following folders are mapped to the running Isaac Sim container by default (container paths may be different for specific applications):

- `/home/ubuntu/uploads` (host) --> `/uploads` (container) - user data uploaded to the deployment with `./upload` command or automatically from local `uploads/` folder
- `/home/ubuntu/results` (host) --> `/results` (container) - results of the applications run on the deployment, can be downloaded from the deployed machine with `./download` command
- `/home/ubuntu/workspace` (host) --> `/workspace` (container) - workspace folder, can be used to exchange data between the host and the container.

### Pausing and Resuming

You can stop and re-start instances to save on cloud costs. To do so, run the following commands:

```sh
# enter the automator container
./run
# inside container:
./stop <deployment-name>
./start <deployment-name>
```

### Uploading Data

You can upload user data from `uploads/` folder (in the project root) to the deployment by running the following command:

```sh
# enter the automator container
./run
# inside container:
./upload <deployment-name>
```

Data will be uploaded to `/home/ubuntu/uploads` directory by default to all deployed instances. You can change this by passing `--remote-dir` argument to the command. Run `./upload --help` to see more options.

### Downloading Data

You can download user data to `results/` folder (in the project root) from deployed instances by running the following command:

```sh
# enter the automator container
./run
# inside container:
./download <deployment-name>
```

Data will be downloaded from `/home/ubuntu/results` directory by default. You can change this by passing `--remote-dir` argument to the command. Run `./download --help` to see more options.

### Repairing

If for some reason the deployment cloud resouces or software configuration get corrupted, you can attempt to repair the deployment by running the following command:

```sh
# run both terraform and ansible
./repair <deployment-name>
# just run terraform to try fixing the cloud resources
./repair <deployment-name> --no-ansible
# just run ansible to try fixing the software configuration
./repair <deployment-name> --no-terraform
```

### Destroying

To destroy a deployment, run the following command:

```sh
# enter the automator container
./run
# inside container:
./destroy <deployment-name>
```

You will be prompted to enter the deployment name to destroy.

*Please note that information about the deployed cloud resources is stored in `state/` directory. Do not delete this directory ever.*




  

