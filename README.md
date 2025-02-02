<div align="center">
    <img src="https://raw.githubusercontent.com/ddosify/ddosify/master/assets/ddosify-logo-db.svg#gh-dark-mode-only" alt="Ddosify logo dark" width="336px" /><br />
    <img src="https://raw.githubusercontent.com/ddosify/ddosify/master/assets/ddosify-logo-wb.svg#gh-light-mode-only" alt="Ddosify logo light" width="336px" /><br />
</div>

<h1 align="center">Effortless Kubernetes Monitoring and Performance Testing</h1>

<p align="center">
    <a href="https://github.com/ddosify/ddosify/releases" target="_blank"><img src="https://img.shields.io/github/v/release/ddosify/ddosify?style=for-the-badge&logo=github&color=orange" alt="ddosify latest version" /></a>&nbsp;
    <a href="https://github.com/ddosify/ddosify/actions/workflows/test.yml" target="_blank"><img src="https://img.shields.io/github/actions/workflow/status/ddosify/ddosify/test.yml?branch=master&style=for-the-badge&logo=github" alt="ddosify build result" /></a>&nbsp;
    <a href="https://pkg.go.dev/go.ddosify.com/ddosify" target="_blank"><img src="https://img.shields.io/github/go-mod/go-version/ddosify/ddosify?style=for-the-badge&logo=go" alt="golang version" /></a>&nbsp;
    <a href="https://github.com/ddosify/ddosify/blob/master/LICENSE" target="_blank"><img src="https://img.shields.io/badge/LICENSE-AGPL--3.0-orange?style=for-the-badge&logo=none" alt="ddosify license" /></a>
    <a href="https://discord.gg/9KdnrSUZQg" target="_blank"><img src="https://img.shields.io/discord/898523141788287017?style=for-the-badge&logo=discord&label=DISCORD" alt="ddosify discord server" /></a>
    <a href="https://hub.docker.com/r/ddosify/ddosify" target="_blank"><img src="https://img.shields.io/docker/v/ddosify/ddosify?style=for-the-badge&logo=docker&label=docker&sort=semver" alt="ddosify docker image" /></a>
</p>

<p align="center">
<img src="assets/ddosify_service_map.png" alt="Ddosify Kubernetes Monitoring Service Map" />
<i>Ddosify automatically generates Service Map of your K8s cluster without code instrumentation or sidecars. So you can easily find the bottlenecks in your system. Red lines indicate the high latency between services.</i>
</p>

<h2 align="center">
    <a href="https://demo.ddosify.com/" target="_blank">Live Demo</a> •
    <a href="https://docs.ddosify.com/" target="_blank">Documentation</a> •
    <a href="https://docs.ddosify.com/ddosify/deployment" target="_blank">Deployment</a> •
    <a href="https://discord.gg/9KdnrSUZQg" target="_blank">Discord</a>
</h2>

## What is Ddosify?

Ddosify is an [open-source](https://github.com/ddosify/ddosify) **Kubernetes Monitoring** and **Performance Testing** platform.


### 🔎 Kubernetes Monitoring

- **Automatic Service Map Creation:** Ddosify automatically creates a **service map** of your cluster without code instrumentation or sidecars. So you can easily find the bottlenecks in your system.
- **Performance Insights:** It helps you spot issues like services taking too long to respond or slow SQL queries.
- **Real-Time Metrics:** The platform tracks and displays live data on your cluster instances CPU, memory, disk, and network usage.
- **Ease of Use:** You don't need to change any code, restart services, or add extra components (like sidecars) to get these insights, thanks to the eBPF technology.
- **Alerts for Anomalies:** If something unusual, like a sudden increase in CPU usage, happens in your Kubernetes (K8s) cluster, Ddosify immediately sends alerts to your Slack.

<p align="center">
<img src="assets/ddosify_metrics.png" alt="Ddosify Kubernetes Monitoring Metrics" />
<i>Ddosify tracks and displays live data on your cluster instances CPU, memory, disk, and network usage.</i>
</p>

### 🔨 Performance Testing

- **Multi-Location Based:** Generate load/performance tests from over 25 countries worldwide. Its available on [Ddosify Cloud](https://app.ddosify.com/).
- **Easy Scenario Builder:** Create test scenarios easily without writing any code.
- **Seamless Integration with Kubernetes Monitoring:** Performance testing is natively integrated with Kubernetes monitoring for a unified experience.
- **Postman Integration:** Import tests directly from Postman, making it convenient for those already using Postman for API development and testing.

<p align="center">
<img src="assets/ddosify_performance_testing.png" alt="Ddosify Kubernetes Monitoring Metrics" />
<i>Ddosify Performance Testing generates load from worldwide with no-code scenario builder.</i>
</p>

## Ddosify Stack

Ddosify Stack consists of 4 parts:

- [Ddosify Engine](#rocket-ddosify-engine)
- [Ddosify eBPF Agent (Alaz)](#-ddosify-ebpf-agent-alaz)
- [Ddosify Self-Hosted](#-ddosify-self-hosted)
- [Ddosify Cloud](#%EF%B8%8F-ddosify-cloud)


<p align="center"> 
<img src="https://imagedelivery.net/jnIqn6NB1gbMLXIvlYKo5A/3f995c37-10fb-4b37-c74f-db1685d0df00/public" alt="Ddosify Stack" />
</p>

### :rocket: Ddosify Engine

[Ddosify Engine](https://github.com/ddosify/ddosify) is the load engine, written in Golang. It's a CLI load-testing tool. Ddosify Self-Hosted and Ddosify Cloud use it under the hood for load generation. It is fully open-source and can be used on the CLI as a standalone tool. It has ~8K Github Stars. Ddosify Engine is available via [Docker](https://hub.docker.com/r/ddosify/ddosify), [Docker Extension](https://hub.docker.com/extensions/ddosify/ddosify-docker-extension), [Homebrew Tap](https://github.com/ddosify/ddosify#homebrew-tap-macos-and-linux), and downloadable pre-compiled binaries from the [releases page](https://github.com/ddosify/ddosify/releases/latest) for macOS, Linux, and Windows.

Check out the [Engine Docs](https://github.com/ddosify/ddosify/tree/master/engine_docs) page for more information and usage.

### 🐝 Ddosify eBPF Agent (Alaz)
[Alaz](https://github.com/ddosify/alaz) is an open-source Ddosify eBPF agent that can inspect and collect Kubernetes (K8s) service traffic without the need for code instrumentation, sidecars, or service restarts. Alaz is deployed as a DaemonSet on your Kubernetes cluster. It collects metrics and sends them to Ddosify Cloud or Ddosify Self-Hosted. It is also Prometheus compatible, so that you can use it as a standalone tool.

Check out the [Alaz](https://github.com/ddosify/alaz) repository for more information and usage.

### 🏠 Ddosify Self-Hosted

[Ddosify Self-Hosted](https://github.com/ddosify/ddosify/tree/master/selfhosted) features a web-based user interface, **Performance Testing**, and **Kubernetes Monitoring** capabilities. You can add your servers as Load Engines to the platform for distributed performance testing. While it shares many of the same functionalities as Ddosify Cloud, the Self-Hosted version is designed to be deployed within your infrastructure for enhanced control and customization. 

It has two versions: Community Edition (CE) and Enterprise Edition (EE). You can see the differences in the below [comparison table](#comparison-of-ddosify-cloud-self-hosted-ee-self-hosted-ce).

Check out our [Github Page](https://github.com/ddosify/ddosify/tree/master/selfhosted) for more information and usage.


#### Quick Start

```bash
curl -sSL https://raw.githubusercontent.com/ddosify/ddosify/master/selfhosted/install.sh | bash
```
<p align="center">
    <a href="https://aws.amazon.com/marketplace/pp/prodview-mwvnujtgjedjy" target="_blank"><img src="https://img.shields.io/badge/Available_on_aws_marketplace-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white" height="40" alt="Available on aws marketplace" /></a>&nbsp;
</p>

### ☁️ Ddosify Cloud

[Ddosify Cloud](https://app.ddosify.com/) features a SaaS, web-based user interface, multi-location-based **Performance Testing**, and **Kubernetes Monitoring**. Anyone can test the performance of backend endpoints, monitor Kubernetes Clusters, and find the bottlenecks in the system. It has a simple/no code UI, insightful charts, service maps, and more features. 

With Ddosify Cloud, you can generate traffic to your endpoints from 25+ countries without code or scripting. 

With [Latency Testing](https://docs.ddosify.com/ddosify/latency-testing), you can test the latency of your endpoints from 60+ cities worldwide.

Check out [Ddosify Cloud](https://app.ddosify.com/) to find the performance issues on your system instantly.

### Comparison of Ddosify Cloud, Self-Hosted EE, Self-Hosted CE
<p align="center">
<img src="assets/ddosify_comparison.png" alt="Ddosify versus" />

*CE: Community Edition, EE: Enterprise Edition*
</p>

## Kubernetes Monitoring Features

#### ✅ Service Map
Easily get insights about what is going on in your cluster. You do not have to change your code or add sidecars anymore. <a href="https://docs.ddosify.com/ddosify/kubernetes-monitoring/service-map" target="_blank">More →</a>
<p align="left">
<img src="assets/ddosify_service_map_detail.png" alt="Ddosify - Service Map Feature" />
</p>

#### ✅  Detailed Insights
Inspect incoming, outgoing traffic, SQL queries, golden signals, HTTP 5xx status codes, Top Latencies and RPS, and more. <a href="https://docs.ddosify.com/ddosify/kubernetes-monitoring/service-map" target="_blank">More →</a>
<p align="left">
<img src="assets/ddosify_service_summary.png" alt="Ddosify - Detailed Insights Feature" />
</p>

#### ✅  Metrics Dashboard
The Metric Dashboard provides a straightforward way to observe Node Metrics. Ddosify observes CPU, Memory, Disk, and Network usage of your nodes. You can also create alerts on these metrics. <a href="https://docs.ddosify.com/ddosify/kubernetes-monitoring/metrics" target="_blank">More →</a>

<p align="left">
<img src="assets/ddosify_metrics_detailed.png" alt="Ddosify - Metrics Dashboard Feature" />
</p>

#### ✅  Find Bottlenecks 
Start a load test and monitor your system all within the same UI. You do not need to correlate the load test results with the monitoring data and switch between different tools.

You will see the outgoing requests, response times and status codes on the load test **Summary** tab. 
<p align="left">
<img src="assets/ddosify_load_test.png" alt="Ddosify - Find Bottlenecks Feature" />
</p>

You will see the incoming requests to your K8s cluster, service-to-service traffic, RPS, latencies, SQL queries, and more on the **Monitoring** tab. So you can easily correlate the load test results with the monitoring data without switching between different tools.
<p align="left">
<img src="assets/ddosify_load_test_monitoring.png" alt="Ddosify - Find Bottlenecks Feature" />
</p>

## Performance Testing Features
#### ✅  Parametrization
Use built-in random data generators. <a href="https://docs.ddosify.com/ddosify/performance-testing/parametrization" target="_blank">More →</a>
<p align="left">
<img src="https://imagedelivery.net/jnIqn6NB1gbMLXIvlYKo5A/4dc3f294-6319-4c2b-a56b-c359276d5e00/public" alt="Ddosify - Parametrization Feature" />
</p>


#### ✅  CSV Data Import
Import test data from CSV and use it in the scenario. <a href="https://docs.ddosify.com/ddosify/performance-testing/test-data-import" target="_blank">More →</a>
<p align="left">
<img src="https://imagedelivery.net/jnIqn6NB1gbMLXIvlYKo5A/6c769b68-e046-440d-137c-b20dd3518300/public" alt="Ddosify - Test Data Feature" />
</p>

#### ✅  Environments
Store constant values as environment variables. <a href="https://docs.ddosify.com/ddosify/performance-testing/environment-variables" target="_blank">More →</a>
<p align="left">
<img src="https://imagedelivery.net/jnIqn6NB1gbMLXIvlYKo5A/78c45dca-03de-4cbf-0edc-fb2b8a2e6600/public" alt="Ddosify - Environment Feature" />
</p>

#### ✅  Correlation
Extract variables from earlier phases and pass them on to the following ones. <a href="https://docs.ddosify.com/ddosify/performance-testing/correlation" target="_blank">More →</a>
<p align="left">
<img src="https://imagedelivery.net/jnIqn6NB1gbMLXIvlYKo5A/7ac98b0f-043b-494f-3c17-7a5436e81400/public" alt="Ddosify - Correlation Feature" />
</p>

#### ✅  Assertion
Verify that the response matches your expectations. <a href="https://docs.ddosify.com/ddosify/performance-testing/assertion" target="_blank">More →</a>
<p align="left">
<img src="https://imagedelivery.net/jnIqn6NB1gbMLXIvlYKo5A/f2f0df70-8e2b-4308-ca6a-4259274d0400/public" alt="Ddosify - Assertion Feature" />
</p>

#### ✅  Debugging
Analyze request and response data before starting the load test. <a href="https://docs.ddosify.com/ddosify/performance-testing/debugging" target="_blank">More →</a>
<p align="left">
<img src="https://imagedelivery.net/jnIqn6NB1gbMLXIvlYKo5A/82322e21-2e3a-4284-9643-1c8dacda2400/public" alt="Ddosify - Debugging Feature" />
</p>

#### ✅  Postman Import
Import Postman collections with ease and transform them into load testing scenarios. <a href="https://docs.ddosify.com/ddosify/performance-testing/postman-import" target="_blank">More →</a>
<p align="left">
<img src="https://imagedelivery.net/jnIqn6NB1gbMLXIvlYKo5A/873bf1e3-07a0-427c-8f32-0791d1728900/public" alt="Ddosify - Postman Import Feature" />
</p>


## About This Repository

This repository includes the source code for the Ddosify Engine. You can access Docker Images for the Ddosify Engine and Self Hosted on <a href="https://hub.docker.com/u/ddosify" target="_blank">Docker Hub</a>. Since Ddosify is a Verified Publisher on Docker Hub, you do not have any pull limits.

The [Engine Docs](https://github.com/ddosify/ddosify/tree/master/engine_docs) folder provides information on the installation, usage, and features of the Ddosify Engine. The [Self-Hosted](https://github.com/ddosify/ddosify/tree/master/selfhosted) folder contains installation instructions for the Self-Hosted version. [Ddosify eBPF agent (Alaz)](https://github.com/ddosify/alaz) has its own repository. 

To learn about the **Performance Testing** usage of both Self-Hosted and Cloud versions, please refer to the [this documentation](https://docs.ddosify.com/ddosify/performance-testing/test-suite). For the **Kubernetes Monitoring** usage, please refer to the [this documentation](https://docs.ddosify.com/ddosify/kubernetes-monitoring).

## Communication

You can join our [Discord Server](https://discord.gg/9KdnrSUZQg) for issues, feature requests, feedbacks or anything else. 

## Disclaimer

Ddosify is created for testing the performance of web applications. Users must be the owner of the target system. Using it for harmful purposes is extremely forbidden. Ddosify team & company is not responsible for its’ usages and consequences.

## License

Licensed under the AGPLv3: https://www.gnu.org/licenses/agpl-3.0.html
