# Load Balancing

## Round Robin

Distributes requests sequentially across the group of servers, one by one. Simple and predictable.

<img width="836" height="315" alt="load_balancing_round_robin" src="https://github.com/user-attachments/assets/de03770e-8d5e-461e-a754-9b60c53e9b84" />

## Weighted Round Robin

Servers with higher capacity (weight) receive a proportionally larger number of requests. Here, Server A gets more traffic.

<img width="990" height="292" alt="load_balancing_weighted_round_robin" src="https://github.com/user-attachments/assets/e41937aa-c98f-49a8-8f1a-6af7cd509a3e" />

## Least Connections

Directs new requests to the server with the fewest active connections. The numbers simulate the current connection count.

<img width="1032" height="315" alt="load_balancing_least_connections" src="https://github.com/user-attachments/assets/f6c2632d-4239-47cc-b302-f2ba53af3c34" />

## IP Hash

The client's IP address is used to determine which server receives the request. This ensures a user consistently connects to the same server.

<img width="1005" height="320" alt="load_balancing_ip_hash" src="https://github.com/user-attachments/assets/4411f028-bbba-4d21-96c0-cfbb695427fd" />

## Least Response Time

Sends requests to the server that is currently responding the fastest (lowest latency). Server C is consistently the fastest here.

<img width="1030" height="315" alt="load_balancing_least_response_time" src="https://github.com/user-attachments/assets/dae911b5-8eff-483b-905c-73170c749625" />

## Adaptive (Health Check)

Distributes traffic based on various server health metrics. Here, Server B periodically fails and the load balancer redirects traffic away from it.

<img width="836" height="315" alt="load_balancing_adaptative_health_check" src="https://github.com/user-attachments/assets/f38959bf-d436-44dc-a540-6e0eba0e6026" />

