# IIIF Luomus server

This is our IIIF compliant server build using [Cantaloupe](https://cantaloupe-project.github.io/).

## Local Development

There is a docker-compose file that will spin up an instance of minio as well as the IIIF server. The cantaloupe instance is configured to mostly track the production configuration which uses S3 for both the source and derivative cache. To start just run: `docker-compose up`.

If you make changes to the Dockerfile, you will need to run `docker-compose build`.

## Openshift

Deploy the config files in the `openshift` folder
(replace the password in cantaloupe-secrets.yaml file).
After adding configs, add a public route.
To update image login with `oc` and then in the docker file run command
`oc start-build cantaloupe --from-dir=./ --follow`

