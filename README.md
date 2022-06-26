
<img src="https://i.imgur.com/5YGcvup.png" />

# DennisHoyer's internal corporate infrastructure

@todo: introduction

## What does Serverless mean?

Serverless computing is a cloud computing execution model in which the cloud provider allocates machine resources on demand, taking care of the servers on behalf of their customers. "Serverless" is a misnomer in the sense that servers are still used by cloud service providers to execute code for developers. However, developers of serverless applications are not concerned with capacity planning, configuration, management, maintenance, fault tolerance, or scaling of containers, VMs, or physical servers. Serverless computing does not hold resources in volatile memory; computing is rather done in short bursts with the results persisted to storage. When an app is not in use, there are no computing resources allocated to the app. Pricing is based on the actual amount of resources consumed by an application.[1] It can be a form of utility computing.

Serverless computing can simplify the process of deploying code into production. Serverless code can be used in conjunction with code deployed in traditional styles, such as microservices or monoliths. Alternatively, applications can be written to be purely serverless and use no provisioned servers at all.[2] This should not be confused with computing or networking models that do not require an actual server to function, such as peer-to-peer (P2P).
## Docker Stacks


| Stack                    | Container                 | Host                                            | Exposed Port        |
| -------------------------- | --------------------------- | ------------------------------------------------- | --------------------- |
| <br />**NETWORK**      |                           |                                                 |                     |
|                          | **traefik**         | ```*```.ahrberg14.de                              | `80`<br />            |
|                          | **pihole**          | ```pihole```.ahrberg14.de                         | `81`              |
|                          |                           |                                                 |                     |
| <br />**ENVIRONMENT**  |                                                 |  |  |
|                          | **dashy**           | ```ahrberg14.de```                                | `1`               |
| <br />                       | **portainer**       | ```docker```.ahrberg14.de                         | `100`             |
| <br />                       | **verdaccio**<br />     | ```npm```.ahrberg14.de<br />```npm```.dennishoyer.com<br /> | `110`             |
| <br />                       | <br />                        |                                                 |                     |
| <br />**MONITORING**<br /> |                           |                                                 |                     |
|                          | **grafana**         | ```grafana```.ahrberg14.de                        | `200`             |
| <br />                       | **posthog**<br />       | ```posthog```.ahrberg14.de                        | `201`             |
|                          | **netdata**         | ```net```.ahrberg14.de                            | `202`             |
|                          | **prometheus**      | ```prometheus```.ahrberg14.de                     | `203`             |
|                          |                           |                                                 |                     |
| <br />**CRM**          |                           |                                                 |                     |
|                          | **Chatwood**        | ```chatwood```.ahrberg14.de                       | `300`             |
|                          | **BotPress**        | ```botpress```.ahrberg14.de                       | `301`             |
|                          |                           |                                                 |                     |
| <br />**DATA**         |                           |                                                 |                     |
|                          | **mariadb**         |                                                 | `3306`            |
|                          | **postgres**        |                                                 | `5432`            |
|                          | **redis**           |                                                 | `--`              |
|                          |                           |                                                 |                     |
| <br />**HOME<br />**<br />     |                           |                                                 |                     |
|                          | **homeassistant**<br /> | ```home```.ahrberg14.de                           | `800`             |
|                          | **nodered**         | ```nodered```.ahrberg14.de                        | `801`             |
|                          | **mosquitto**       | ```mqtt```.ahrberg14.de                           | `1883` <br />`1884` |
