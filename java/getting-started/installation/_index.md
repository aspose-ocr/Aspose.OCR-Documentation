---
title: Installation
type: docs
weight: 40
url: /java/installation/
---

## **Installing Aspose.OCR for Java from Maven Repository**

Aspose hosts all Java APIs on the [Maven repository](https://repository.aspose.com/webapp/#/artifacts/browse/tree/General/repo/com/aspose). You can easily use [Aspose.OCR for Java](https://repository.aspose.com/webapp/#/artifacts/browse/tree/General/repo/com/aspose/aspose-ocr) API directly in your Maven Projects with simple configurations.

### **Installing Aspose.OCR for Java from Maven Repository**
 
First, [download Maven](https://maven.apache.org/download.cgi) and follow the [installation instructions](https://maven.apache.org/install.html).

Then run command to create project

`mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart `
`-DarchetypeVersion=1.4 -DinteractiveMode=false`

Notice: If you want to use **GPU version** you have to make sure does your GPU supports **CUDA** and install CUDA 10.1
Installation guide for CUDA you can find by link [CUDA install](https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/index.html)

### **Specify Maven Repository Configuration**

First, you need to specify Aspose Maven Repository configuration/location in your Maven pom.xml as follows:

Copy 

```java
<repositories>
    <repository>
        <id>AsposeJavaAPI</id>
        <name>Aspose Java API</name>
        <url>http://repository.aspose.com/repo/</url>
    </repository>
</repositories>
```

Define Aspose.OCR for Java API Dependency
Then define Aspose.OCR for Java API dependency in your **pom.xml** as follows:

Copy 

```java
<dependencies>
    <dependency>
        <groupId>com.aspose</groupId>
        <artifactId>aspose-ocr</artifactId>
        <version>22.5</version>
    </dependency>
</dependencies>
```
or 

```java
<dependencies>
    <dependency>
        <groupId>com.aspose</groupId>
        <artifactId>aspose-ocr-gpu</artifactId>
        <version>20.11</version>
    </dependency>
</dependencies>
```

After performing the above steps, Aspose.OCR for Java dependency will finally be defined in your Maven Project.


## **Installing Aspose.OCR for Java from local package**

 - download jar files from https://downloads.aspose.com/ocr/java

 - create aspose-ocr-[version].pom file with next content (aspose-ocr--gpu-[version].pom)

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd" xmlns="http://maven.apache.org/POM/4.0.0"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 <modelVersion>4.0.0</modelVersion>
 <groupId>com.aspose</groupId>
 <artifactId>aspose-ocr</artifactId>
        // for gpu version
        // <artifactId>aspose-ocr-gpu</artifactId>
 <version>[version]</version>
 <name>ocr</name>
 <properties>
    <project.displayName>Aspose.OCR for Java</project.displayName>
                // <project.displayName>Aspose.OCR.GPU for Java</project.displayName>
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
 </properties>
 <dependencies>
    <dependency>
                  // for cpu version
        <groupId>org.bytedeco</groupId>
        <artifactId>onnxruntime-platform</artifactId>
        <version>1.11.0</version> 
                  // for gpu version
                  // <groupId>com.microsoft.onnxruntime</groupId>
        // <artifactId>onnxruntime_gpu</artifactId>
        // <version>1.3.1</version>
    </dependency>  
 </dependencies>
 <organization>
    <name>Aspose</name>
    <url>https://products.aspose.com/ocr/java</url>
 </organization>
 <description>Aspose.OCR for Java</description>
</project>
```

put jar files and pom file into `C:/Users/[Name]/.m2/repository/com/aspose/aspose-ocr/20.11` (specify version)
or `C:/Users/[Name]/.m2/repository/com/aspose/aspose-ocr-gpu/20.11` (specify version)

don't specify Maven Repository in your project pom file, write only `<dependencies>`

## **Technical Support**

Aspose provides unlimited free technical support for all its products. The support is available to all users, including evaluation.

If you need help with Aspose.OCR, consider the following:

- The main avenue for support is the [Aspose.Forums](https://forum.aspose.com/). Post your question in the [Aspose.OCR Support Forum](https://forum.aspose.com/c/ocr) and it will be answered within a few hours.
- Please note, Aspose does not provide technical support over the phone. Phone support is only available for sales and purchase questions.
- When expecting a reply in the forums, please allow for time zone differences.

If you have an issue with Aspose.OCR, follow these simple steps to make sure it is resolved in the most efficient way:

- Make sure you use the latest Aspose.OCR version before reporting the issue.
- Have a look through the forums, this documentation, and API Reference before reporting the issue; maybe your question was already answered.
- When reporting an issue, please include the original document and possibly a fragment of your code that causes the problem. If you need to attach multiple files, zip them into one. It is safe to attach your documents in Aspose.Forums if the thread is marked/created as Private since only you and Aspose developers will have access to the attached files.
- Please try to report one issue per thread. If you have another issue, report it in a separate thread.
