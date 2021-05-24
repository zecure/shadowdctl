#!/bin/bash
set -e

source .env

if [ ! -d "$SHADOWD_ENV_LOCATION" ]; then
    mkdir -p "$SHADOWD_ENV_LOCATION"
    chown root:root "$SHADOWD_ENV_LOCATION"
    chmod 750 "$SHADOWD_ENV_LOCATION"
fi

export SHADOWD_ENV_DB_LOCATION="$SHADOWD_ENV_LOCATION/db"
if [ ! -f "$SHADOWD_ENV_DB_LOCATION" ]; then
    SHADOWD_DB_PASSWORD=`cat /dev/urandom | tr -dc 'a-zA-Z0-9' | head -c 32`
    echo "=================================================="
    echo "Database password: ${SHADOWD_DB_PASSWORD}"
    echo "=================================================="
    echo "SHADOWD_DB_PASSWORD=${SHADOWD_DB_PASSWORD}" >> "$SHADOWD_ENV_DB_LOCATION"
    echo "POSTGRES_PASSWORD=${SHADOWD_DB_PASSWORD}" >> "$SHADOWD_ENV_DB_LOCATION"
fi

docker-compose "$@"
