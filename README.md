# ns8-quay

This is a module for container registry [Project Quay](https://www.projectquay.io/).

## Configure

Let's assume that the quay instance is named `quay1`.

Required parameters:
- host: host name of the quay server

Optional parameters:
- contact_site
- logo_url
- title
- description
- superuser

Example:

    api-cli run module/quay1/configure-module --data '{"host": "quay.gs.nethserver.net"}'

The above command will:
- start and configure the quay instance with Let's encrypt certificate

Send a test HTTP request to the quay backend service:

    curl https://quay.gs.nethserver.net

## Uninstall

To uninstall the instance:

    remove-module --no-preserve quay1

## Testing

Test the module using the `test-module.sh` script:


    ./test-module.sh <NODE_ADDR> ghcr.io/nethserver/quay:latest

The tests are made using [Robot Framework](https://robotframework.org/)
