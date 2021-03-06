# Functions Node.js - Samples for SAP Cloud Platform Functions

## Description
SAP Cloud Platform Functions provides a cloud-based serverless functions framework for the development of decoupled and resilient applications and integration flows (using SAP Cloud Integration) to support asynchronous communication principles.
Direct integration with SAP S/4HANA Business Event Handling allows efficient development of innovative and scaling extensions.

This repository provides documentation and samples of how to implement functions (Node.js) for SAP Cloud Platform Functions in the Cloud Foundry environment. Details on each sample application and the covered scenario are described in the table _List of content and sample projects_ below.

For more details of **SAP Cloud Platform Functions** take a look at [SAP Cloud Platform Functions on SAP Help Portal](https://help.sap.com/viewer/94fafb5bcf8f4c5cbdd0cdd8e358183c/Cloud/en-US/4968e80fc3984d9ca3fcc9a2ed2fc48e.html).

This repository provides samples of how to implement a function (Node.js) for SAP Cloud Platform Functions in the Cloud Foundry environment.

## List of Content and Sample Projects

|Sample/Content|Scenario|Scenario Description|
|---|---|---|
|[amqp-echo](./examples/amqp-echo)| Basic `AMQP 1.0` example | An echo function with messaging |
|[call-other-function](./examples/call-other-function)| Basic example | A function calls another function |
|[ebaas-forwarder](./examples/ebaas-forwarder) | Advanced example | A message from `Enterprise Messaging Service @SAP CP` triggers a function. It is forwarded and stored in `Enterprise Backend as a Service @SAP CP`  |
|[hello-amqp](./examples/hello-amqp) | Basic `AMQP 1.0` example | Whenever a producer function is executed, it sends a message, which is consumed by a another function |
|[hello-secret](./examples/hello-secret) | Basic example | A function extracts data from a secret |
|[qrcode-producer](./examples/qrcode-producer)| Basic example | A function produces the current timestamp as QR code |
|[slack-classify-image](./examples/slack-classify-image)| Advanced example, requires Slack integration | An image post in Slack triggers a function. The function classifies the image via `SAP Leonardo` |

## Requirements
To run the samples a [Functions Service @SAP CP](https://help.sap.com/viewer/94fafb5bcf8f4c5cbdd0cdd8e358183c/Cloud/en-US/3418355e1497473baf071e28294dde41.html) is required.

1. Install Node.js

   Download and install [Node.js](https://nodejs.org/en/download/)(includes npm).
   The Node.js version must be >= 8.12.x.
   
2. Install __faas-cli__

    Download the binary either from Nexus or from the [CP Tools Page](https://tools.hana.ondemand.com/#cloud).

3. Install __faas-sdk__

    Add the SAP NPM Registry to your npm configuration for all `@sap` scoped modules.
    ```bash
    npm config set "@sap:registry https://npm.sap.com"
    ```

    Installation or update:
    * Linux
        ```bash
        sudo npm install @sap/faas -g
        ````
    * Windows (as usual user)
        ```bash
        npm install @sap/faas -g
        ````

    Finally, run:
    ```bash
    faas-sdk version
    ```
    to test successful installation.

4. Install CloudFoundry command line tools (CF CLI)

    [Download and install the Cloud Foundry CLI](https://docs.cloudfoundry.org/cf-cli/install-go-cli.html).

    Run the command `cf login`, and [login to your Cloud Foundry environment](https://developers.sap.com/tutorials/hcp-cf-getting-started.html).

    Make sure your **Functions Service @SAP CP** [service](https://cli.cloudfoundry.org/en-US/cf/create-service.html) and [service key](https://cli.cloudfoundry.org/en-US/cf/create-service-key.html) exists.

    Further necessary configuration and settings are dependent on the specific sample and are documented there.

## Download and Installation

To download and install the samples just [clone](https://gist.github.com/derhuerst/1b15ff4652a867391f03) this repository using this command:
```bash
git clone https://github.com/SAP/cloud-function-nodejs-samples
```

For details on how to configure and run the samples please take a look into the README in the corresponding samples directory.

The file __faas.json__ in each sample directory is used as a manifest. It defines secrets, functions and triggers
for one single project.

## Support
This project is _as-is_ with no support, no changes being made.

## License
Copyright (c) 2019 SAP SE or an SAP affiliate company. All rights reserved. This file is licensed under the _SAP SAMPLE CODE LICENSE AGREEMENT, v1.0-071618_ except as noted otherwise in the [LICENSE file](./LICENSE).
