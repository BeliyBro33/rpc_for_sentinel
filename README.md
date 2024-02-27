Script for selecting the best RPC for a sentinel node .

This requires curl, jq and bc packages so make sure you have them:  
apt install curl jq bc -y (debian/ubuntu)  (default on script) 
dnf install curl jq bc -y (fedora/alma/rhel) 


The script also adds values to the config file:
sed -i "s#^rpc_addresses.*#$new_line#" "${HOME}"/.sentinelnode/config.toml

Deletes a file :
rm -f .sentinelnode/data.db

Restarts and displays logs: 
docker restart dvpn-node-sin
docker logs -f -n 100 dvpn-node-sin
