# Vostok

*A complete microservice toolkit for .NET developers.*

Vostok has everything .NET developers need to create distributes systems. It provides intra-cluster communication between microservices and collects their logs, metrics, and distributes traces out of the box.

## How it works



![](blueprint.png)

## Features

**Feature complete.** Vostok has everything to create, monitor and troubleshoot microservices. No other tools or libraries are required.

**Sanely pre-configured.** Vostok has ready to use templates for your .NET Core and .NET Web API applications as well as Docker files for complementary services. Zero configuration is required to get started.

**Fast by design.** Vostok is benchmarked and optimized for performance and throughput. No expensive hardware is required. Commodity servers are just fine for complementary services.

## Getting started

### Run a sample Vostok-enabled application

Run an all-in-one Vostok bundle with Docker. It includes *[Airlock Gate](https://github.com/vostok/airlock.gate)*, *Kafka*, all *[Airlock Consumers](https://github.com/vostok/airlock.consumer)*, *Graphite*, *Grafana*, *RabbitMQ*, *Elasticsearch*, *Logstash*, *Kibana*, *Cassandra*, and *[Contrails](https://github.com/vostok/contrails)*.

```sh
docker run vostok/spaceport
```

Get a [sample application](https://github.com/vostok/sample). It contains several Vostok-enabled microservices which send logs, metrics, and traces to *Airlock Gate* via their *[Airlock Clients](https://github.com/vostok/airlock.client)*.

```sh
git clone https://github.com/vostok/sample.git && \
cd sample && \
dotnet run
```

Navigate to the sample application in your web browser. Then have a look at *Kibana* for logs, *Grafana* for metrics, and *Contrails* for traces:

```sh
open http://localhost:5000 && \
open http://localhost:5100 && \
open http://localhost:5200 && \
open http://localhost:5300     
```

### Create your first Vostok-enabled application

Run the all-in-one Vostok bundle, as described above, or setup a [stand-alone Vostok installation](#).

Install *[Launchpad](https://github.com/vostok/launchpad)*, a CLI tool for Vostok. On Windows, download this [MSI package](#).

On Ubuntu, use Aptitude:

```sh
apt-get install vostok
```

On macOS, use Homebrew:

```sh
brew install vostok
```

Create and run a .NET Core microservice with Vostok instrumentation:

```sh
vostok create --name "vostok-one-app" --output "." && \
dotnet run
```

Navigate to the microservice in your web browser. Then have a look at *Kibana* for logs, *Grafana* for metrics, and *Contrails* for traces:

```sh
open http://localhost:33333 && \
open http://localhost:5100 && \
open http://localhost:5200 && \
open http://localhost:5300     
```