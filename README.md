# local-stack
Config and utils to manage runtime dependencies for local development

Components pre-configured as part of **local-stack** include:
* [MongoDB](https://www.mongodb.com/docs/manual/)
* [Mongo Express](https://github.com/mongo-express/mongo-express)
* Kafka
* [Redpanda Console for Kafka](https://redpanda.com/redpanda-console-kafka-ui)
* Redis
* Redis Insight 1.x
* [Azurite](https://learn.microsoft.com/en-us/azure/storage/common/storage-use-azurite?tabs=docker-hub) (optional, Microsoft's Azure Storage API emulator) 

## Redis
To configure TLS locally, use [gen-test-certs.sh](gen-test-certs.sh) to generate self-signed certificates.
The latest version of this script can be found in [Redis' repo](https://github.com/redis/redis/blob/unstable/utils/gen-test-certs.sh)

### Using RedisInsight to connect to a TLS-enabled Redis instance
<img src="resources/RedisInsight_TLS_config_01.png" width="75%" height="75%" alt="Basic config"/>

Notice that because RedisInsight is running inside the same container network as Redis, `redis` is used as the hostname instead of localhost.

<img src="resources/RedisInsight_TLS_config_02.png" width="75%" height="75%" alt="CA config"/>
<img src="resources/RedisInsight_TLS_config_03.png" width="75%" height="75%" alt="Client certificate config"/>

