# tcp-udp-routing
Simple example demonstrating how to route traffic to specific upstreams based on the client_ip address.


Based on the $remote_addr of the CLIENT, Stream Context will dynamically route the request to one of the two upstreams. 
If the request originates from localhost, i.e. map is able to identify a match on 127.0.0.1, it will print the port of the server you have been routed to - 2011, in this example. 

If the request originates from anywhere else, map directive will use the default upstream, in our case it will be routed to upstream listening on port 2012 -



Run from the NGINX Instance box:
nc -w 1 127.0.0.1 2007

expected output - 2011


Run from your local computer:
nc -w 1 <ip_nginx_instance> 2007

expected output - 2012


