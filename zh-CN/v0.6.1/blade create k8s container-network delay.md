# blade create network delay

# **Introduction**
Kubernetes Container network scenes, same as the network scenes of the underlying resources
# **Flags**

```
--local-port
	Ports for local service. Support for configuring multiple ports, separated by commas or connector representing ranges, for example: 80,8000-8080
--remote-port
	Ports for remote service. Support for configuring multiple ports, separated by commas or connector representing ranges, for example: 80,8000-8080
--exclude-port
	Exclude local ports. Support for configuring multiple ports, separated by commas or connector representing ranges, for example: 22,8000. This flag is invalid when --local-port or --remote-port is specified
--destination-ip
	destination ip. Support for using mask to specify the ip range such as 92.168.1.0/24 or comma separated multiple ips, for example 10.0.0.1,11.0.0.1.
--ignore-peer-port
	ignore excluding all ports communicating with this port, generally used when the ss command does not exist
--interface
	Network interface, for example, eth0
--exclude-ip
	Exclude ips. Support for using mask to specify the ip range such as 92.168.1.0/24 or comma separated multiple ips, for example 10.0.0.1,11.0.0.1
--force
	Forcibly overwrites the original rules
--time
	Delay time, ms
--offset
	Delay offset time, ms
--container-id
	Container id
--image-repo
	Image repository of the chaosblade-tool
--image-version
	Image version of the chaosblade-tool
--docker-endpoint
	Docker socket endpoint
--evict-count
	Count of affected resource
--evict-percent
	Percent of affected resource, integer value without %
--names
	Resource names, such as pod name. You must add namespace flag for it. Multiple parameters are separated directly by commas
--namespace
	Namespace, such as default, only one value can be specified
--labels
	Label selector, the relationship between values that are or
--evict-group
	Group key from labels
--container-ids
	Container ids
--container-names
	Container names
--timeout
	set timeout for experiment

```

# **Example**

````
# Access to nginx container port 80 is delayed by 3 seconds
blade create docker network delay --time 3000 --interface eth0 --local-port 80 --container-id 5239e26f6329
````

