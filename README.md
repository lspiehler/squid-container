## Start container
docker compose up -d

## Stop container
docker compose down

## Watch logs
docker logs -f squid

## Reload config
docker exec -it squid squid -k reconfigure

## Clear cache and logs
rm -Rf /var/docker/squid-container/logs/*
rm -Rf /var/docker/squid-container/cache/*