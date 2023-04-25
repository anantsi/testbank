# Insecure Bank

[ERROR] TU 36: 
Suppressible assertion failed at translationunit.cpp:1938: Primary SF /var/lib/jenkins/.m2/repository/org/springframework/spring-webmvc/4.2.3.RELEASE/spring-webmvc-4.2.3.RELEASE.jar of binary TU 36 doesn't appear in its emit invocation's referenced files

This failure can be suppressed by setting the environment variable
COVERITY_SUPPRESS_ASSERT to 1938, in which case this program will
attempt to recover and proceed despite the failure if it happens again.
Regardless, please report the failure to software-integrity-support@synopsys.com

call stack backtrace:
cov-internal-emit-java-webapp linux64 2022.12.0
  0x8183e0
  0x81a570
  0x52b8bd
  0x46499d
  0x479c28
  0x47e155
  0x47fe13
  0x873b4f
  0x446202
libc.so.6 linux64 2022.12.0
  0x29d90

## Building

```
sudo apt install -y openjdk-11-jdk
sudo apt install -y maven
```

Now clone this repository.

```
cd insecure-bank
mvn clean package
```

## Running

```
sudo apt install -y docker.io
sudo docker build -t wildfly .
sudo docker run --rm -it -p 8080:8080 wildfly
```

You can then access the bank application here: http://localhost:8080/

## Login credentials

See the file [src/main/resources/db/dataload.sql](src/main/resources/db/dataload.sql) for all example accounts. Here is one:

- username: john@example.com
- password: test

##
:warning: This application is for educational purposes only and while running this application your device will be vulnerable to attack. It is recommended to  disconnect from the Internet while using this program.
