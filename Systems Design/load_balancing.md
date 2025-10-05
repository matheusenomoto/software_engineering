# Load Balancing

## Round Robin

Distributes requests sequentially across the group of servers, one by one. Simple and predictable.

![load_balancing_round_robin](../img/load_balancing_round_robin.png)

## Weighted Round Robin

Servers with higher capacity (weight) receive a proportionally larger number of requests. Here, Server A gets more traffic.

![load_balancing_weighted_round_robin](../img/load_balancing_weighted_round_robin.png)

## Least Connections

Directs new requests to the server with the fewest active connections. The numbers simulate the current connection count.

![load_balancing_least_connections](../img/load_balancing_least_connections.png)

## IP Hash

The client's IP address is used to determine which server receives the request. This ensures a user consistently connects to the same server.

![load_balancing_ip_hash](../img/load_balancing_ip_hash.png)

## Least Response Time

Sends requests to the server that is currently responding the fastest (lowest latency). Server C is consistently the fastest here.

![load_balancing_least_response_time](../img/load_balancing_least_response_time.png)

## Adaptive (Health Check)

Distributes traffic based on various server health metrics. Here, Server B periodically fails and the load balancer redirects traffic away from it.

![load_balancing_adaptative_health_check](../img/load_balancing_adaptative_health_check.png)
