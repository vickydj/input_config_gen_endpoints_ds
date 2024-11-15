# Rest handler to generate confs

## Overview

    This app sits on deployment servers, receives payload from the SH app <app-name here>.
  
    The python program decodes the payload and generates inputs.conf and serverclass.conf
  
    Checks for existing app/conf files and adds only new updates. Duplicates are ignored.

## To do
1. Create another handler to send phoning phone list to SH/ or log them and read from the dashboard app.


To modify the below 
==============


For more information about creating custom REST handlers in Splunk Enterprise, see [Extend the Splunk Enterprise REST API with custom endpoints](https://dev.splunk.com/enterprise/docs/developapps/customrestendpoints) in the _Splunk Enterprise Developer Guide_.

## Installation

Install the hello-world app to run the example custom REST handler scripts in your Splunk Enterprise instance.
1. Clone this repository onto your local machine.
2. Copy the `splunk-examples-custom-endpoints-master/hello-world` directory into `$SPLUNK_HOME/etc/apps`.
3. Restart Splunk Enterprise.

## App contents

The hello-world app for Splunk Enterprise contains the following two example custom REST handlers:

| Script             	| Handler type                         	|
|--------------------	|-------------------------------------------	|
| `hello_templates.py` 	| Extensible Administration Interface (EAI) 	|
| `hello_world.py`     	| Script interface                                    	|

When you call the endpoints for these two handlers, they both return the following payload:

```
{"text":"Hello world!"}
```

To test these custom REST handlers on the backend management port of your Splunk Enterprise installation, go to the following URLs:
* `hello_templates`- [https://localhost:8089/servicesNS/-/hello-world/hello-templates/say-hello-templates](https://localhost:8089/servicesNS/-/hello-world/hello-templates/say-hello-templates)
* `hello_world`- [https://localhost:8089/servicesNS/-/hello-world/say-hello](https://localhost:8089/servicesNS/-/hello-world/say-hello)

## Support

This project is community-supported. Post any questions or comments to this repository.

Discuss custom REST endpoints in the #appdev channel in the splunk-usergroups Slack workspace.

You can also post questions about custom REST endpoints on [Splunk Answers](https://answers.splunk.com/index.html) using the `REST Endpoint Examples` or `restmap.conf` tags.
