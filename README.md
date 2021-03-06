# Spring Cloud Alibaba

[![CircleCI](https://circleci.com/gh/spring-cloud-incubator/spring-cloud-alibaba/tree/master.svg?style=svg)](https://circleci.com/gh/spring-cloud-incubator/spring-cloud-alibaba/tree/master)
[![Maven Central](https://img.shields.io/maven-central/v/org.springframework.cloud/spring-cloud-alibaba-dependencies.svg?label=Maven%20Central)](https://search.maven.org/search?q=g:org.springframework.cloud%20AND%20a:spring-cloud-alibaba-dependencies)
[![Codecov](https://codecov.io/gh/spring-cloud-incubator/spring-cloud-alibaba/branch/master/graph/badge.svg)](https://codecov.io/gh/spring-cloud-incubator/spring-cloud-alibaba)
[![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)

A project maintained by Alibaba.

See the [中文文档](https://github.com/spring-cloud-incubator/spring-cloud-alibaba/blob/master/README-zh.md) for Chinese readme.

Spring Cloud Alibaba provides a one-stop solution for distributed application development. It contains all the components required to develop distributed applications, making it easy for you to develop your applications using Spring Cloud.

With Spring Cloud Alibaba, you only need to add some annotations and a small amount of configurations to connect Spring Cloud applications to the distributed solutions of Alibaba, and build a distributed application system with Alibaba middleware.


## Features

* **Flow control and service degradation**：Flow control for HTTP services is supported by default. You can also customize flow control and service degradation rules using annotations. The rules can be changed dynamically.
* **Service registration and discovery**：Service can be registered and clients can discover the instances using Spring-managed beans, auto integration Ribbon.
* **Distributed configuration**：support for externalized configuration in a distributed system, auto refresh when configuration changes.
* **Event-driven**：support for building highly scalable event-driven microservices connected with shared messaging systems.
* **Alibaba Cloud Object Storage**：massive, secure, low-cost, and highly reliable cloud storage services. Support for storing and accessing any type of data in any application, anytime, anywhere.
For more features, please refer to [Roadmap](https://github.com/spring-cloud-incubator/spring-cloud-alibaba/blob/master/Roadmap.md).

## Components

**[Sentinel](https://github.com/alibaba/Sentinel)**: Sentinel takes "traffic flow" as the breakthrough point, and provides solutions in areas such as flow control, concurrency, circuit breaking, and load protection to protect service stability.

**[Nacos](https://github.com/alibaba/Nacos)**: an easy-to-use dynamic service discovery, configuration and service management platform for building cloud native applications.

**[RocketMQ](https://rocketmq.apache.org/)**：a distributed messaging and streaming platform with low latency, high performance and reliability, trillion-level capacity and flexible scalability.

**[Alibaba Cloud ACM](https://www.aliyun.com/product/acm)**：an application configuration center that enables you to centralize the management of application configurations, and accomplish real-time configuration push in a distributed environment.

**[Alibaba Cloud OSS](https://www.aliyun.com/product/oss)**: An encrypted and secure cloud storage service which stores, processes and accesses massive amounts of data from anywhere in the world.

For more features please refer to [Roadmap](https://github.com/spring-cloud-incubator/spring-cloud-alibaba/blob/master/Roadmap.md).

## How to build

* **master branch**: Corresponds to Spring Boot 2.x. JDK 1.8 or later versions are supported.
* **1.x branch**: Corresponds to Spring Boot 1.x, JDK 1.7 or later versions are supported.

Spring Cloud uses Maven for most build-related activities, and you should be able to get off the ground quite quickly by cloning the project you are interested in and typing:

	./mvnw install


## How to Use

### Add maven dependency
Version 0.2.1.RELEASE is compatible with the Spring Cloud Finchley. Version 0.1.1.RELEASE is compatible with the Spring Cloud Edgware.

These artifacts are available from Maven Central and Spring Release repository via BOM:

	<dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>org.springframework.cloud</groupId>
                <artifactId>spring-cloud-alibaba-dependencies</artifactId>
                <version>0.2.1.RELEASE</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>

add the module in  `dependencies`.

If you want to use the latest BUILD-SNAPSHOT version, add `Spring Snapshot Repository` in  pom.xml , **Attention: BUILD-SNAPSHOT may be updated in any time**

	<repositories>
        <repository>
            <id>spring-snapshot</id>
            <name>Spring Snapshot Repository</name>
            <url>https://repo.spring.io/snapshot</url>
            <snapshots>
                <enabled>true</enabled>
            </snapshots>
        </repository>
    </repositories>


### Reference Doc

[Contents](https://github.com/spring-cloud-incubator/spring-cloud-alibaba/blob/master/spring-cloud-alibaba-docs/src/main/asciidoc-zh/spring-cloud-alibaba.adoc)

[Nacos Config](https://github.com/spring-cloud-incubator/spring-cloud-alibaba/blob/master/spring-cloud-alibaba-docs/src/main/asciidoc-zh/nacos-config.adoc)

[Nacos Discovery](https://github.com/spring-cloud-incubator/spring-cloud-alibaba/blob/master/spring-cloud-alibaba-docs/src/main/asciidoc-zh/nacos-discovery.adoc)

[ACM](https://github.com/spring-cloud-incubator/spring-cloud-alibaba/blob/master/spring-cloud-alibaba-docs/src/main/asciidoc-zh/acm.adoc)


## Examples

A `spring-cloud-alibaba-examples` module is included in our project for you to get started with Spring Cloud Alibaba quickly. It contains an example, and you can refer to the readme file in the example project for a quick walkthrough.

Examples：

[Sentinel Example](https://github.com/spring-cloud-incubator/spring-cloud-alibaba/tree/master/spring-cloud-alibaba-examples/sentinel-example/sentinel-core-example/readme.md)

[Nacos Config Example](https://github.com/spring-cloud-incubator/spring-cloud-alibaba/blob/master/spring-cloud-alibaba-examples/nacos-example/nacos-config-example/readme.md)

[Nacos Discovery Example](https://github.com/spring-cloud-incubator/spring-cloud-alibaba/blob/master/spring-cloud-alibaba-examples/nacos-example/nacos-discovery-example/readme.md)

[RocketMQ Example](https://github.com/spring-cloud-incubator/spring-cloud-alibaba/blob/master/spring-cloud-alibaba-examples/rocketmq-example/readme.md)

[Alibaba Cloud OSS Example](https://github.com/spring-cloud-incubator/spring-cloud-alibaba/blob/master/spring-cloud-alibaba-examples/oss-example/readme.md)

## Version control guidelines
The version number of the project is in the form of x.x.x, where x is a number, starting from 0, and is not limited to the range 0~9. When the project is in the incubator phase, the first version number is fixed to 0, that is, the version number is 0.x.x.

As the interfaces and annotations of Spring Boot 1 and Spring Boot 2 have been changed significantly in the Actuator module, and spring-cloud-commons is also changed quite a lot from 1.x.x to 2.0.0, we maintain two different branches to support Spring Boot 1 and Spring Boot 2:
* 0.1.x for Spring Boot 1
* 0.2.x for Spring Boot 2

During the incubation period, the version management of the project will follow these rules：
* Functional updates will be reflected in the 3rd number of the version, for example, the next version of 0.1.0 will be 0.1.1.


## Contact Us
Mailing list is recommended for discussing almost anything related to spring-cloud-alibaba. 

spring-cloud-alibaba@googlegroups.com:You can ask questions here if you encounter any problem when using or developing spring-cloud-alibaba.
