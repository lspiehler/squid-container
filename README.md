## Start container
docker compose up -d

## Stop container
docker compose down

## Watch logs
docker logs -f --tail 50 squid

## Allow lists are located in /var/docker/squid-container/config/lists/
Edit SharedInfra to allow additional domains from the SharedInfra VPC
Add CDNs to the "cdn" list
Add globally allowed domains to the "global_allow" list
Add certificate related domains (CRL/OCSP services) to the "pki" list

## Reload config
docker exec -it squid squid -k reconfigure

## Clear cache and logs
rm -Rf /var/docker/squid-container/logs/*
rm -Rf /var/docker/squid-container/cache/*