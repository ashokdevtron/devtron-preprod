# Build Configuration

In this section, we will provide information on the `Build Configuration`.

Build configuration is used to create and push docker images in the container registry of your application. You will provide all the docker related information to build and push docker images on the `Build Configuration` page.

Only one docker image can be created for multi-git repository applications as explained in the [Git Repository](git-material.md) section.

For **build configuration**, you must provide information in the sections as given below:

* [Store Container Image](docker-build-configuration.md#store-container-image)
* [Build the Container Image](docker-build-configuration.md#build-the-container-image)
* [Advanced Options](docker-build-configuration.md#advanced-options)

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/creating-application/docker-build-configuration/build-configuration-latest1.jpg)

## Store Container Image

The following fields are provided on the **Store Container Image** section:

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/creating-application/docker-build-configuration/store-container-registry.jpg)

| Field                    | Description                                                                                                                                                                                                                                                   |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Container Registry**   | Select the container registry from the drop-down list or you can click **Add Container Registry**. This registry will be used to [store docker images](../../../global-configurations/container-registries.md).                                               |
| **Container Repository** | Enter the name of your container repository, preferably in the format `username/repo-name`. The repository that you specify here will store a collection of related docker images. Whenever an image is added here, it will be stored with a new tag version. |

**If you are using docker hub account, you need to enter the repository name along with your username. For example - If my username is&#x20;**_**kartik579**_**&#x20;and repo name is&#x20;**_**devtron-trial**_**, then enter kartik579/devtron-trial instead of only devtron-trial.**

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/creating-application/docker-build-configuration/docker-configuration-docker-hub.jpg)

## Build the Container Image

In order to deploy the application, we must build the container images to configure a fully operational container environment.

You can choose one of the following options to build your container image:

* **I have a Dockerfile**
* **Create Dockerfile**
* **Build without Dockerfile**

### Build Docker Image when you have a Dockerfile

A `Dockerfile` is a text document that contains all the commands which you can call on the command line to build an image.

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/creating-application/docker-build-configuration/i-have-a-dockerfile.jpg)

| Field                                       | Description                                                                                                                                                      |
| ------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Select repository containing Dockerfile** | Select the Git checkout path of your repository. This repository is the same which you defined on the [Git Repository](git-material.md) section.                 |
| **Dockerfile Path (Relative)**              | Enter a relative file path where your docker file is located in Git repository. Ensure that the dockerfile is available on this path. This is a mandatory field. |

### Build Docker Image by creating Dockerfile

With the option **Create Dockerfile**, you can create a `Dockerfile` from the available templates. You can edit any selected Dockerfile template as per your build configuration requirements.

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/creating-application/docker-build-configuration/create-dockerfile.jpg)

| Field         | Description                                                                                                                                                                                                                                                                                                                    |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Language**  | <p>Select the programming language (e.g., <code>Java</code>, <code>Go</code>, <code>Python</code>, <code>Node</code> etc.) from the drop-down list you want to create a dockerfile as per compatibility to your system.<br><strong>Note</strong> We will be adding other programming languages in the future releases.<br></p> |
| **Framework** | <p>Select the framework (e.g., <code>Maven</code>, <code>Gradle</code> etc.) of the selected programming language.<br><strong>Note</strong> We will be adding other frameworks in the future releases.<br></p>                                                                                                                 |

### Build Docker Image without Dockerfile

With the option **Build without Dockerfile**, you can use Buildpacks to automatically build the image for your preferred language and framework.

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/creating-application/docker-build-configuration/build-without-dockerfile.jpg)

| Field                                 | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Select repository containing code** | Select your code repository. This repository is the same which you defined on the [Git Repository](git-material.md) section.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Project Path (Relative)**           | In case of monorepo, specify the path of the project from your Git repository.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Language**                          | <p>Select the programming language (e.g., <code>Java</code>, <code>Go</code>, <code>Python</code>, <code>Node</code>, <code>Ruby</code>, <code>PHP</code> etc.) from the drop-down list you want to build your container image as per the compatibility to your system.<br><strong>Note</strong>: We will be adding other programming languages in the future releases.<br></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Version**                           | Select a language version from the drop-down list. If you do not find the version you need, then you can update the language version in `Build Env Arguments`. You can also select **Autodetect** in case if you want `Builder` to detect version by itself or its default version.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Select a builder**                  | <p>A builder is an image that contains a set of buildpacks which provide your app's dependencies, a stack, and the OS layer for your app image. Select a buildpack provider from the following options:</p><ul><li><strong>Heroku</strong>: It compiles your deployed code and creates a slug, which is a compressed and pre-packaged copy of your app and also the runtime which is optimized for distribution to the dyno (Linux containers) manager. <a href="https://devcenter.heroku.com/articles/buildpacks">Learn more</a>.</li></ul><ul><li><strong>GCR</strong>: GCR builder is a general purpose builder that creates container images designed to run on most platforms (e.g. Kubernetes / Anthos, Knative / Cloud Run, Container OS, etc.). It auto-detects the language of your source code, and can also build functions compatible with the Google Cloud Function Framework. <a href="https://github.com/GoogleCloudPlatform/buildpacks">Learn more</a>.</li></ul><ul><li><strong>Paketo</strong>: Paketo buildpacks provide production-ready buildpacks for the most popular languages and frameworks to easily build your apps. Based on your application needs, you can select from <code>Full</code>, <code>Base</code> and <code>Tiny</code>. <a href="https://paketo.io/docs/">Learn more</a>.</li></ul> |

#### Build Env Arguments

You can add Key/Value pair by clicking **Add argument**.

| Field     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Key**   | <p>Define the key parameter as per your selected language and builder. E.g., By default <code>GOOGLE_RUNTIME_VERSION</code> for GCR buildpack.<br><strong>Note</strong>: If you want to define <code>env arguments</code> for <code>PHP</code> and <code>Ruby</code> languages after selecting <code>Heroku</code> builder, please make sure to refer respective <a href="https://devcenter.heroku.com/articles/ruby-support">Heroku Ruby Support</a> and <a href="https://devcenter.heroku.com/articles/php-support">Heroku PHP Support</a> documentation for runtime information.<br></p> |
| **Value** | Define the value for the specified key. E.g. Version no.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |

**Note** This fields are optional. If required, it can be overridden at [CI step](../deploying-application/triggering-ci.md).

## Advanced Options

### Set Target Platform for the build

Using this option, you can build images for a specific or multiple **architectures and operating systems (target platforms)**. You can select the target platform from the drop-down list or can type to select a customized target platform.

![Select target platform from drop-down](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/creating-application/docker-build-configuration/set-target-platform.jpg)

![Select custom target platform](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/creating-application/docker-build-configuration/set-target-platform-2.jpg)

Before selecting a customized target platform, please ensure that the architecture and the operating system are supported by the `registry type` you are using, otherwise build will fail. Devtron uses BuildX to build images for multiple target Platforms, which requires higher CI worker resources. To allocate more resources, you can increase value of the following parameters in the `devtron-cm` configmap in `devtroncd` namespace.

* LIMIT\_CI\_CPU
* REQ\_CI\_CPU
* REQ\_CI\_MEM
* LIMIT\_CI\_MEM

To edit the `devtron-cm` configmap in `devtroncd` namespace:

```
kubectl edit configmap devtron-cm -n devtroncd 
```

If target platform is not set, Devtron will build image for architecture and operating system of the k8s node on which CI is running.

The Target Platform feature might not work in minikube & microk8s clusters as of now.

### Docker Build Arguments

It is is a collapsed view including the following parameters:

* Key
* Value

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/creating-application/docker-build-configuration/docker-build-arguments.jpg)

These fields will contain the key parameter and the value for the specified key for your [docker build](https://docs.docker.com/engine/reference/commandline/build/#options). This field is Optional. If required, this can be overridden at [CI step](../deploying-application/triggering-ci.md).

Click **Save Configuration**.
