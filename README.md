# VICINITY Docker Services

The VICINITY Docker Services is a pre-prepared docker recipe that runs the services of the [Gateway API](https://github.com/vicinityh2020/vicinity-gateway-api) and the [Agent](https://github.com/vicinityh2020/vicinity-agent) core components from VICINTIY. The goal of this recipe is to leverage the deployment work required by third-part users who will only need to setup these services with their credentials.

## Quick start

To quickly deploy the VICINITY services offert by this docker recipe download this repository and move into the downloaded directory

````
sudo git clone https://github.com/vicinityh2020/docker-services
cd docker-services
````
Afterwards configure the adapters configuration file '/config/agent/config-1.json' with your credentials from the [VICINITY Neighbourhood Manager](https://vicinity.bavenir.eu/#!/login), and **do not** modify the file '/config/agent/service-config.json'. In case some tuning is required by the gateway there is no need to modify the gateway config file '/config/config/GatewayConfig.xml', however if required modify this file as well.

Next run the docker compose file in the root directory using 
````
docker-compose up -d
````
Or using the following version if you want to print the log of the containers in the terminal
````
docker-compose up
````

When the services must be stop just execute 
````
docker-compose down
````



## Configuring Agent

Before running the services the agent must be configured, to achieve this goal just open file '/config/agent/config-1.json':

````
{
  "credentials": {
    "agent-id": "XX",
    "password": "XX"
  },
  "adapters": [
    {
      "adapter-id": "XX-adapter",
      "active-discovery": "true"
    }
  ]
}
````

Fill the *agent-id* and the *password* using your credentials from the neighbourhood manager in the section access point. If you do not have any access point create a new one before.


