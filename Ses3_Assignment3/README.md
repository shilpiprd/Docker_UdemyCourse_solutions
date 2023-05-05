TasK:
_________

1. Ever since docker engine 1.11 we can have multiple containers on a created network that repsond to the same DNS address. 
2. Create a new virtual network (default bridge driver) (call it whatever you want). 
3. Create 2 containers from `elasticsearch:2` image. 
4. Research and use `—network-alias search` when creating them to give them an additional DNS name to respond to. 
5. Run `apline nslookup search` with `—net` to see the 2 containers list for the same DNS name. : returns a list of the DNS addresses for the name search.
6. Run `centos curl -s search:9200` with `—net` multiple times until you see both ‘name’ fields show.


Some additional points to keep: 
_______
- Understand how DNS records might work, like what an alias record is or how to create one.
- DNS RoundRobin: You can have 2 differnet hosts with DNS aliases  that respond to the same
- DNS round robin: you can have 2 differnt host with DNS aliases that respond to the same DNS name.  Ex: google.com, obviously they’ve got more than 1 server . So, there are multiple IP addresses beghind the DNS server that you’re using.
