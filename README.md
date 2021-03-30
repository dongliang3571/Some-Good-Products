# Some-Good-Products

### Jenkins

CICD pipeline

https://www.cloudbees.com/blog/scaling-jenkins-slaves

https://www.cloudbees.com/blog/setting-jenkins-ec2-slaves


**Best practice for # of executors in a Node**

https://support.cloudbees.com/hc/en-us/articles/115002654991-Remoting-Best-Practices


#### Pipeline: Basic Steps

- `catchError` - https://www.jenkins.io/doc/pipeline/steps/workflow-basic-steps/#catcherror-catch-error-and-set-build-result-to-failure

If the body throws an exception, it marks the build as a failure, but continue to run statements within a `stage`. But it will fail the stage and not continue next stages

### SaltStack

Configuration management

https://www.youtube.com/watch?v=z6jUo17iwIA

### Nomad

A simple and flexible workload orchestrator to deploy and manage containers 

https://learn.hashicorp.com/tutorials/nomad/get-started-install?in=nomad/get-started

https://www.youtube.com/watch?v=xl58mjMJjrg

### Consul

**Service mesh**

- Service Discovery
- Service Configuration
- Service segmentation

### Fabio

Http/TCP load balancing

### Terraform

Infrastructure provisioning

### LocalStack 

https://github.com/localstack/localstack

Local version of AWS

Example of a docker-compose file:

```yml
localstack:
    image: localstack/localstack:0.12.8
    ports:
      - "4566:4566"
      - "4571:4571"
      - "9000:9000"
    environment:
        - SERVICES=sqs,s3
        - DEFAULT_REGION=us-east-1
        - DEBUG=1
        - DATA_DIR=/tmp/localstack/data
        - START_WEB=1
        - PORT_WEB_UI=9000
        - DOCKER_HOST=unix:///var/run/docker.sock
        - HOSTNAME_EXTERNAL=localstack
    volumes:
      - ${TMPDIR:-/tmp/localstack}:/tmp/localstack
```

- `HOSTNAME_EXTERNAL`: Name of the host to expose the services externally (default: localhost). This host is used, e.g., when returning **queue** URLs from the SQS service to the client.
