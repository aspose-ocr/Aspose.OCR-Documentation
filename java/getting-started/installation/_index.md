---
weight: 20
date: "2022-09-16"
author: "Vladimir Lapin"
type: docs
url: /java/installation/
title: Installation
description: Adding Aspose.OCR for Java package to your project.
keywords:
- install
- update
- Maven
- package
- download
---

**Aspose.OCR for Java** APIs are hosted on the Maven repository or can be installed from the [local package](https://releases.aspose.com/ocr/java/).

## Installing Aspose.OCR for Java from Maven Repository

1. [Download](https://maven.apache.org/download.cgi) and [install](https://maven.apache.org/install.html) Apache Maven.
2. Run the following command to create a project:

```bash
mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false
```

{{% alert color="primary" %}} 
To use GPU-accelerated version, make sure your GPU [supports](/ocr/java/installation/gpu/) CUDA and has NVIDIA CUDA Toolkit.
{{% /alert %}} 

3. Specify Aspose Maven Repository location in your Maven **pom.xml**:

```xml
<repositories>
    <repository>
        <id>AsposeJavaAPI</id>
        <name>Aspose Java API</name>
        <url>https://releases.aspose.com/java/repo/</url>
    </repository>
</repositories>
```

4. Define Aspose.OCR for Java API dependency in your **pom.xml**:

Standard (CPU-based) version:

```xml
<dependencies>
    <dependency>
        <groupId>com.aspose</groupId>
        <artifactId>aspose-ocr</artifactId>
        <version>22.5</version>
    </dependency>
</dependencies>
```

GPU-accelerated version:

```xml
<dependencies>
    <dependency>
        <groupId>com.aspose</groupId>
        <artifactId>aspose-ocr-gpu</artifactId>
        <version>20.11</version>
    </dependency>
</dependencies>
```

## Installing Aspose.OCR for Java local package

1. [Download](https://releases.aspose.com/ocr/java/) Aspose.OCR for Java package (ZIP archive).
2. Extract the package to your development machine.
3. JAR files and the configuration are located in **/com/aspose/aspose-ocr/[version]** (for CPU-based version) or **/com/aspose/aspose-ocr-gpu/[version]** (for GPU-accelerated version).
