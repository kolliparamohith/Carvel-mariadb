# Mariadb Package

MariaDB is an open source, community-developed SQL database server that is widely in use around the world due to its enterprise features, flexibility, and collaboration with leading tech firms.

## Configuration Reference

You can configure the following:

### MariaDB common parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|image.pullPolicy|MariaDB image pull policy|string|IfNotPresent|
|auth.database|Name for a custom database to create|string|my_database|
|auth.password|Password for the new user. Ignored if existing secret is provided|string|"KjMfdzcjkp3K"|
|auth.replicationPassword|MariaDB replication user password. Ignored if existing secret is provided|string|"zTqmtcf7CqLc"|
|auth.rootPassword|Password for the root user. Ignored if existing secret is provided|string|"PHVHdqzrMb9s"|

### MariaDB Primary parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|primary.podSecurityContext.fsGroup|Group ID for the mounted volumes' filesystem|integer|1001|
|primary.containerSecurityContext.runAsUser|User ID for the MariaDB primary container|integer|1001|
|primary.containerSecurityContext.runAsNonRoot|Set Controller container's Security Context runAsNonRoot|string|true|
|primary.resources.limits|The resources limits for MariaDB primary containers|string|{}|
|primary.resources.requests|The requested resources for MariaDB primary containers|string|{}|
|primary.livenessProbe.failureThreshold|Initial delay seconds for livenessProbe|integer|120|
|primary.livenessProbe.periodSeconds|Period seconds for livenessProbe|integer|10|
|primary.livenessProbe.timeoutSeconds|Timeout seconds for livenessProbe|integer|1|
|primary.livenessProbe.failureThreshold|Failure threshold for livenessProbe|integer|3|
|primary.livenessProbe.successThreshold|Success threshold for livenessProbe|integer|1|
|primary.readinessProbe.initialDelaySeconds|Initial delay seconds for readinessProbe|integer|30|
|primary.readinessProbe.periodSeconds|Period seconds for readinessProbe|integer|10|
|primary.readinessProbe.timeoutSeconds|Timeout seconds for readinessProbe|integer|1|
|primary.readinessProbe.failureThreshold|Failure threshold for readinessProbe|integer|3|
|primary.readinessProbe.successThreshold|Success threshold for readinessProbe|integer|1|
|primary.persistence.size|MariaDB primary persistent volume size|integer|8Gi|
|primary.service.type|MariaDB Primary Kubernetes service type|string|LoadBalancer|
|primary.service.ports.mysql|MariaDB Primary Kubernetes service port|integer|80|
|primary.service.ports.metrics|MariaDB Primary Kubernetes service port|integer|9104|
|primary.revisionHistoryLimit|Maximum number of revisions that will be maintained in the StatefulSet|integer|10|
|mysql.containerport|Mysql container Port|integer|3306|
|initContainers.enabled|initConatiners enabled|string|true|
|securityContext.runAsUser|security context run As user|integer|0|
|weight|value of weight|integer|1|
|serviceAccount.automountServiceAccountToken|service Account of AutoMountServiceToken|string|false|
|Secret.mariadbrootPassword|the secret of mariadb root Password|string|"mypassword"|

### MariaDB Secondary parameters

|Parameter|Description|Type|Deafult|
|---------|-----------|----|-------|
|secondary.replicaCount|Number of MariaDB secondary replicas|integer|1|

### Metrics parameters

|Parameter|Description|Type|Deafult|
|---------|-----------|----|-------|
|metrics.enabled|Start a side-car prometheus exporter|string|true|
|metrics.resources.limits|The resources limits for MariaDB prometheus exporter containers|string|{}|
|metrics.resources.requests|The requested resources for MariaDB prometheus exporter containers|string|{}|
|metrics.containerport|Metrics container port|integer|9104|
|metrics.livenessProbe.initialDelaySeconds|Initial delay seconds for livenessProbe|integer|120|
|metrics.livenessProbe.periodSeconds|Period seconds for livenessProbe|integer|10|
|metrics.livenessProbe.timeoutSeconds|Timeout seconds for livenessProbe|integer|1|
|metrics.livenessProbe.failureThreshold|Failure threshold for livenessProbe|integer|3|
|metrics.livenessProbe.successThreshold|Success threshold for livenessProbe|integer|1|
|metrics.readinessProbe.initialDelaySeconds|Initial delay seconds for readinessProbe|integer|30|
|metrics.readinessProbe.periodSeconds|Period seconds for readinessProbe|integer|10|
|metrics.readinessProbe.timeoutSeconds|Timeout seconds for readinessProbe|integer|1|
|metrics.readinessProbe.failureThreshold|Failure threshold for readinessProbe|integer|3|
|metrics.readinessProbe.successThreshold|Success threshold for readinessProbe|integer|1|
