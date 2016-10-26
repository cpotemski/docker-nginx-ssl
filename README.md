# docker + nginx + letsencrypt

This is a docker container setup that automaticly generates SSL certificates for other docker containers.


#### Template for a container

    test-container:
      image: example-image
      environment:
        - "VIRTUAL_HOST=example.com,sub.example.com"
        - "LETSENCRYPT_HOST=example.com"
        - "LETSENCRYPT_EMAIL=your_email@example.com"
      depends_on:
        - nginx-proxy
        - nginx-companion
