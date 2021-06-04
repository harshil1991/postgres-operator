---
title: CRD Reference
draft: false
weight: 100
---

Packages:

- [postgres-operator.crunchydata.com/v1beta1](#postgres-operatorcrunchydatacomv1beta1)

# postgres-operator.crunchydata.com/v1beta1

Resource Types:

- [PostgresCluster](#postgrescluster)




## PostgresCluster
<sup><sup>[↩ Parent](#postgres-operatorcrunchydatacomv1beta1 )</sup></sup>






PostgresCluster is the Schema for the postgresclusters API

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
      <td><b>apiVersion</b></td>
      <td>string</td>
      <td>postgres-operator.crunchydata.com/v1beta1</td>
      <td>true</td>
      </tr>
      <tr>
      <td><b>kind</b></td>
      <td>string</td>
      <td>PostgresCluster</td>
      <td>true</td>
      </tr>
      <tr>
      <td><b><a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.20/#objectmeta-v1-meta">metadata</a></b></td>
      <td>object</td>
      <td>Refer to the Kubernetes API documentation for the fields of the `metadata` field.</td>
      <td>true</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspec">spec</a></b></td>
        <td>object</td>
        <td>PostgresClusterSpec defines the desired state of PostgresCluster</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterstatus">status</a></b></td>
        <td>object</td>
        <td>PostgresClusterStatus defines the observed state of PostgresCluster</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec
<sup><sup>[↩ Parent](#postgrescluster)</sup></sup>



PostgresClusterSpec defines the desired state of PostgresCluster

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspeccustomreplicationtlssecret">customReplicationTLSSecret</a></b></td>
        <td>object</td>
        <td>The secret containing the replication client certificates and keys for secure connections to the PostgreSQL server. It will need to contain the client TLS certificate, TLS key and the Certificate Authority certificate with the data keys set to tls.crt, tls.key and ca.crt, respectively. NOTE: If CustomReplicationClientTLSSecret is provided, CustomTLSSecret MUST be provided and the ca.crt provided must be the same.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspeccustomtlssecret">customTLSSecret</a></b></td>
        <td>object</td>
        <td>The secret containing the Certificates and Keys to encrypt PostgreSQL traffic will need to contain the server TLS certificate, TLS key and the Certificate Authority certificate with the data keys set to tls.crt, tls.key and ca.crt, respectively. It will then be mounted as a volume projection to the '/pgconf/tls' directory. For more information on Kubernetes secret projections, please see https://k8s.io/docs/concepts/configuration/secret/#projection-of-secret-keys-to-specific-paths NOTE: If CustomTLSSecret is provided, CustomReplicationClientTLSSecret MUST be provided and the ca.crt provided must be the same.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecmetadata">metadata</a></b></td>
        <td>object</td>
        <td>Metadata contains metadata for PostgresCluster resources</td>
        <td>false</td>
      </tr><tr>
        <td><b>openshift</b></td>
        <td>boolean</td>
        <td>Whether or not the PostgreSQL cluster is being deployed to an OpenShift envioronment</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecpatroni">patroni</a></b></td>
        <td>object</td>
        <td></td>
        <td>false</td>
      </tr><tr>
        <td><b>port</b></td>
        <td>integer</td>
        <td>The port on which PostgreSQL should listen.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxy">proxy</a></b></td>
        <td>object</td>
        <td>The specification of a proxy that connects to PostgreSQL.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchive">archive</a></b></td>
        <td>object</td>
        <td>PostgreSQL archive configuration</td>
        <td>true</td>
      </tr><tr>
        <td><b>image</b></td>
        <td>string</td>
        <td>The image name to use for PostgreSQL containers</td>
        <td>true</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindex">instances</a></b></td>
        <td>[]object</td>
        <td></td>
        <td>true</td>
      </tr><tr>
        <td><b>postgresVersion</b></td>
        <td>integer</td>
        <td>The major version of PostgreSQL installed in the PostgreSQL container</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.customReplicationTLSSecret
<sup><sup>[↩ Parent](#postgresclusterspec)</sup></sup>



The secret containing the replication client certificates and keys for secure connections to the PostgreSQL server. It will need to contain the client TLS certificate, TLS key and the Certificate Authority certificate with the data keys set to tls.crt, tls.key and ca.crt, respectively. NOTE: If CustomReplicationClientTLSSecret is provided, CustomTLSSecret MUST be provided and the ca.crt provided must be the same.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspeccustomreplicationtlssecretitemsindex">items</a></b></td>
        <td>[]object</td>
        <td>If unspecified, each key-value pair in the Data field of the referenced Secret will be projected into the volume as a file whose name is the key and content is the value. If specified, the listed keys will be projected into the specified paths, and unlisted keys will not be present. If a key is specified which is not present in the Secret, the volume setup will error unless it is marked optional. Paths must be relative and may not contain the '..' path or start with '..'.</td>
        <td>false</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>Name of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#names TODO: Add other useful fields. apiVersion, kind, uid?</td>
        <td>false</td>
      </tr><tr>
        <td><b>optional</b></td>
        <td>boolean</td>
        <td>Specify whether the Secret or its key must be defined</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.customReplicationTLSSecret.items[index]
<sup><sup>[↩ Parent](#postgresclusterspeccustomreplicationtlssecret)</sup></sup>



Maps a string key to a path within a volume.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>mode</b></td>
        <td>integer</td>
        <td>Optional: mode bits used to set permissions on this file. Must be an octal value between 0000 and 0777 or a decimal value between 0 and 511. YAML accepts both octal and decimal values, JSON requires decimal values for mode bits. If not specified, the volume defaultMode will be used. This might be in conflict with other options that affect the file mode, like fsGroup, and the result can be other mode bits set.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The key to project.</td>
        <td>true</td>
      </tr><tr>
        <td><b>path</b></td>
        <td>string</td>
        <td>The relative path of the file to map the key to. May not be an absolute path. May not contain the path element '..'. May not start with the string '..'.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.customTLSSecret
<sup><sup>[↩ Parent](#postgresclusterspec)</sup></sup>



The secret containing the Certificates and Keys to encrypt PostgreSQL traffic will need to contain the server TLS certificate, TLS key and the Certificate Authority certificate with the data keys set to tls.crt, tls.key and ca.crt, respectively. It will then be mounted as a volume projection to the '/pgconf/tls' directory. For more information on Kubernetes secret projections, please see https://k8s.io/docs/concepts/configuration/secret/#projection-of-secret-keys-to-specific-paths NOTE: If CustomTLSSecret is provided, CustomReplicationClientTLSSecret MUST be provided and the ca.crt provided must be the same.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspeccustomtlssecretitemsindex">items</a></b></td>
        <td>[]object</td>
        <td>If unspecified, each key-value pair in the Data field of the referenced Secret will be projected into the volume as a file whose name is the key and content is the value. If specified, the listed keys will be projected into the specified paths, and unlisted keys will not be present. If a key is specified which is not present in the Secret, the volume setup will error unless it is marked optional. Paths must be relative and may not contain the '..' path or start with '..'.</td>
        <td>false</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>Name of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#names TODO: Add other useful fields. apiVersion, kind, uid?</td>
        <td>false</td>
      </tr><tr>
        <td><b>optional</b></td>
        <td>boolean</td>
        <td>Specify whether the Secret or its key must be defined</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.customTLSSecret.items[index]
<sup><sup>[↩ Parent](#postgresclusterspeccustomtlssecret)</sup></sup>



Maps a string key to a path within a volume.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>mode</b></td>
        <td>integer</td>
        <td>Optional: mode bits used to set permissions on this file. Must be an octal value between 0000 and 0777 or a decimal value between 0 and 511. YAML accepts both octal and decimal values, JSON requires decimal values for mode bits. If not specified, the volume defaultMode will be used. This might be in conflict with other options that affect the file mode, like fsGroup, and the result can be other mode bits set.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The key to project.</td>
        <td>true</td>
      </tr><tr>
        <td><b>path</b></td>
        <td>string</td>
        <td>The relative path of the file to map the key to. May not be an absolute path. May not contain the path element '..'. May not start with the string '..'.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.metadata
<sup><sup>[↩ Parent](#postgresclusterspec)</sup></sup>



Metadata contains metadata for PostgresCluster resources

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>annotations</b></td>
        <td>map[string]string</td>
        <td></td>
        <td>false</td>
      </tr><tr>
        <td><b>labels</b></td>
        <td>map[string]string</td>
        <td></td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.patroni
<sup><sup>[↩ Parent](#postgresclusterspec)</sup></sup>





<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>dynamicConfiguration</b></td>
        <td>object</td>
        <td></td>
        <td>false</td>
      </tr><tr>
        <td><b>leaderLeaseDurationSeconds</b></td>
        <td>integer</td>
        <td>TTL of the cluster leader lock. "Think of it as the length of time before initiation of the automatic failover process."</td>
        <td>false</td>
      </tr><tr>
        <td><b>port</b></td>
        <td>integer</td>
        <td>The port on which Patroni should listen.</td>
        <td>false</td>
      </tr><tr>
        <td><b>syncPeriodSeconds</b></td>
        <td>integer</td>
        <td>The interval for refreshing the leader lock and applying dynamicConfiguration. Must be less than leaderLeaseDurationSeconds.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy
<sup><sup>[↩ Parent](#postgresclusterspec)</sup></sup>



The specification of a proxy that connects to PostgreSQL.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncer">pgBouncer</a></b></td>
        <td>object</td>
        <td>Defines a PgBouncer proxy and connection pooler.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer
<sup><sup>[↩ Parent](#postgresclusterspecproxy)</sup></sup>



Defines a PgBouncer proxy and connection pooler.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinity">affinity</a></b></td>
        <td>object</td>
        <td>Scheduling constraints of a PgBouncer pod. Changing this value causes PgBouncer to restart. More info: https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncerconfig">config</a></b></td>
        <td>object</td>
        <td>Configuration settings for the PgBouncer process. Changes to any of these values will be automatically reloaded without validation. Be careful, as you may put PgBouncer into an unusable state. More info: https://www.pgbouncer.org/usage.html#reload</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncercustomtlssecret">customTLSSecret</a></b></td>
        <td>object</td>
        <td>A secret projection containing a certificate and key with which to encrypt connections to PgBouncer. The "tls.crt", "tls.key", and "ca.crt" paths must be PEM-encoded certificates and keys. Changing this value causes PgBouncer to restart. More info: https://kubernetes.io/docs/concepts/configuration/secret/#projection-of-secret-keys-to-specific-paths</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncermetadata">metadata</a></b></td>
        <td>object</td>
        <td>Metadata contains metadata for PostgresCluster resources</td>
        <td>false</td>
      </tr><tr>
        <td><b>port</b></td>
        <td>integer</td>
        <td>Port on which PgBouncer should listen for client connections. Changing this value causes PgBouncer to restart.</td>
        <td>false</td>
      </tr><tr>
        <td><b>replicas</b></td>
        <td>integer</td>
        <td>Number of desired PgBouncer pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncerresources">resources</a></b></td>
        <td>object</td>
        <td>Compute resources of a PgBouncer container. Changing this value causes PgBouncer to restart. More info: https://kubernetes.io/docs/concepts/configuration/manage-resources-containers</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncertolerationsindex">tolerations</a></b></td>
        <td>[]object</td>
        <td>Tolerations of a PgBouncer pod. Changing this value causes PgBouncer to restart. More info: https://kubernetes.io/docs/concepts/scheduling-eviction/taint-and-toleration</td>
        <td>false</td>
      </tr><tr>
        <td><b>image</b></td>
        <td>string</td>
        <td>Name of a container image that can run PgBouncer 1.15 or newer. Changing this value causes PgBouncer to restart. More info: https://kubernetes.io/docs/concepts/containers/images</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncer)</sup></sup>



Scheduling constraints of a PgBouncer pod. Changing this value causes PgBouncer to restart. More info: https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitynodeaffinity">nodeAffinity</a></b></td>
        <td>object</td>
        <td>Describes node affinity scheduling rules for the pod.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodaffinity">podAffinity</a></b></td>
        <td>object</td>
        <td>Describes pod affinity scheduling rules (e.g. co-locate this pod in the same node, zone, etc. as some other pod(s)).</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodantiaffinity">podAntiAffinity</a></b></td>
        <td>object</td>
        <td>Describes pod anti-affinity scheduling rules (e.g. avoid putting this pod in the same node, zone, etc. as some other pod(s)).</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.nodeAffinity
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinity)</sup></sup>



Describes node affinity scheduling rules for the pod.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindex">preferredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>The scheduler will prefer to schedule pods to nodes that satisfy the affinity expressions specified by this field, but it may choose a node that violates one or more of the expressions. The node that is most preferred is the one with the greatest sum of weights, i.e. for each node that meets all of the scheduling requirements (resource request, requiredDuringScheduling affinity expressions, etc.), compute a sum by iterating through the elements of this field and adding "weight" to the sum if the node matches the corresponding matchExpressions; the node(s) with the highest sum are the most preferred.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitynodeaffinityrequiredduringschedulingignoredduringexecution">requiredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>object</td>
        <td>If the affinity requirements specified by this field are not met at scheduling time, the pod will not be scheduled onto the node. If the affinity requirements specified by this field cease to be met at some point during pod execution (e.g. due to an update), the system may or may not try to eventually evict the pod from its node.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitynodeaffinity)</sup></sup>



An empty preferred scheduling term matches all objects with implicit weight 0 (i.e. it's a no-op). A null preferred scheduling term matches no objects (i.e. is also a no-op).

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreference">preference</a></b></td>
        <td>object</td>
        <td>A node selector term, associated with the corresponding weight.</td>
        <td>true</td>
      </tr><tr>
        <td><b>weight</b></td>
        <td>integer</td>
        <td>Weight associated with matching the corresponding nodeSelectorTerm, in the range 1-100.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].preference
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindex)</sup></sup>



A node selector term, associated with the corresponding weight.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreferencematchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>A list of node selector requirements by node's labels.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreferencematchfieldsindex">matchFields</a></b></td>
        <td>[]object</td>
        <td>A list of node selector requirements by node's fields.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].preference.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreference)</sup></sup>



A node selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. If the operator is Gt or Lt, the values array must have a single element, which will be interpreted as an integer. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>Represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist. Gt, and Lt.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].preference.matchFields[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreference)</sup></sup>



A node selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. If the operator is Gt or Lt, the values array must have a single element, which will be interpreted as an integer. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>Represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist. Gt, and Lt.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitynodeaffinity)</sup></sup>



If the affinity requirements specified by this field are not met at scheduling time, the pod will not be scheduled onto the node. If the affinity requirements specified by this field cease to be met at some point during pod execution (e.g. due to an update), the system may or may not try to eventually evict the pod from its node.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindex">nodeSelectorTerms</a></b></td>
        <td>[]object</td>
        <td>Required. A list of node selector terms. The terms are ORed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitynodeaffinityrequiredduringschedulingignoredduringexecution)</sup></sup>



A null or empty node selector term matches no objects. The requirements of them are ANDed. The TopologySelectorTerm type implements a subset of the NodeSelectorTerm.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindexmatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>A list of node selector requirements by node's labels.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindexmatchfieldsindex">matchFields</a></b></td>
        <td>[]object</td>
        <td>A list of node selector requirements by node's fields.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[index].matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindex)</sup></sup>



A node selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. If the operator is Gt or Lt, the values array must have a single element, which will be interpreted as an integer. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>Represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist. Gt, and Lt.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[index].matchFields[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindex)</sup></sup>



A node selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. If the operator is Gt or Lt, the values array must have a single element, which will be interpreted as an integer. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>Represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist. Gt, and Lt.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAffinity
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinity)</sup></sup>



Describes pod affinity scheduling rules (e.g. co-locate this pod in the same node, zone, etc. as some other pod(s)).

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodaffinitypreferredduringschedulingignoredduringexecutionindex">preferredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>The scheduler will prefer to schedule pods to nodes that satisfy the affinity expressions specified by this field, but it may choose a node that violates one or more of the expressions. The node that is most preferred is the one with the greatest sum of weights, i.e. for each node that meets all of the scheduling requirements (resource request, requiredDuringScheduling affinity expressions, etc.), compute a sum by iterating through the elements of this field and adding "weight" to the sum if the node has pods which matches the corresponding podAffinityTerm; the node(s) with the highest sum are the most preferred.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodaffinityrequiredduringschedulingignoredduringexecutionindex">requiredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>If the affinity requirements specified by this field are not met at scheduling time, the pod will not be scheduled onto the node. If the affinity requirements specified by this field cease to be met at some point during pod execution (e.g. due to a pod label update), the system may or may not try to eventually evict the pod from its node. When there are multiple elements, the lists of nodes corresponding to each podAffinityTerm are intersected, i.e. all terms must be satisfied.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAffinity.preferredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodaffinity)</sup></sup>



The weights of all of the matched WeightedPodAffinityTerm fields are added per-node to find the most preferred node(s)

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinityterm">podAffinityTerm</a></b></td>
        <td>object</td>
        <td>Required. A pod affinity term, associated with the corresponding weight.</td>
        <td>true</td>
      </tr><tr>
        <td><b>weight</b></td>
        <td>integer</td>
        <td>weight associated with matching the corresponding podAffinityTerm, in the range 1-100.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodaffinitypreferredduringschedulingignoredduringexecutionindex)</sup></sup>



Required. A pod affinity term, associated with the corresponding weight.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselector">labelSelector</a></b></td>
        <td>object</td>
        <td>A label query over a set of resources, in this case pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>namespaces</b></td>
        <td>[]string</td>
        <td>namespaces specifies which namespaces the labelSelector applies to (matches against); null or empty list means "this pod's namespace"</td>
        <td>false</td>
      </tr><tr>
        <td><b>topologyKey</b></td>
        <td>string</td>
        <td>This pod should be co-located (affinity) or not co-located (anti-affinity) with the pods matching the labelSelector in the specified namespaces, where co-located is defined as running on a node whose value of the label with key topologyKey matches that of any node on which any of the selected pods is running. Empty topologyKey is not allowed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm.labelSelector
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinityterm)</sup></sup>



A label query over a set of resources, in this case pods.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm.labelSelector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAffinity.requiredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodaffinity)</sup></sup>



Defines a set of pods (namely those matching the labelSelector relative to the given namespace(s)) that this pod should be co-located (affinity) or not co-located (anti-affinity) with, where co-located is defined as running on a node whose value of the label with key <topologyKey> matches that of any node on which a pod of the set of pods is running

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodaffinityrequiredduringschedulingignoredduringexecutionindexlabelselector">labelSelector</a></b></td>
        <td>object</td>
        <td>A label query over a set of resources, in this case pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>namespaces</b></td>
        <td>[]string</td>
        <td>namespaces specifies which namespaces the labelSelector applies to (matches against); null or empty list means "this pod's namespace"</td>
        <td>false</td>
      </tr><tr>
        <td><b>topologyKey</b></td>
        <td>string</td>
        <td>This pod should be co-located (affinity) or not co-located (anti-affinity) with the pods matching the labelSelector in the specified namespaces, where co-located is defined as running on a node whose value of the label with key topologyKey matches that of any node on which any of the selected pods is running. Empty topologyKey is not allowed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAffinity.requiredDuringSchedulingIgnoredDuringExecution[index].labelSelector
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodaffinityrequiredduringschedulingignoredduringexecutionindex)</sup></sup>



A label query over a set of resources, in this case pods.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodaffinityrequiredduringschedulingignoredduringexecutionindexlabelselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAffinity.requiredDuringSchedulingIgnoredDuringExecution[index].labelSelector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodaffinityrequiredduringschedulingignoredduringexecutionindexlabelselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAntiAffinity
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinity)</sup></sup>



Describes pod anti-affinity scheduling rules (e.g. avoid putting this pod in the same node, zone, etc. as some other pod(s)).

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindex">preferredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>The scheduler will prefer to schedule pods to nodes that satisfy the anti-affinity expressions specified by this field, but it may choose a node that violates one or more of the expressions. The node that is most preferred is the one with the greatest sum of weights, i.e. for each node that meets all of the scheduling requirements (resource request, requiredDuringScheduling anti-affinity expressions, etc.), compute a sum by iterating through the elements of this field and adding "weight" to the sum if the node has pods which matches the corresponding podAffinityTerm; the node(s) with the highest sum are the most preferred.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindex">requiredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>If the anti-affinity requirements specified by this field are not met at scheduling time, the pod will not be scheduled onto the node. If the anti-affinity requirements specified by this field cease to be met at some point during pod execution (e.g. due to a pod label update), the system may or may not try to eventually evict the pod from its node. When there are multiple elements, the lists of nodes corresponding to each podAffinityTerm are intersected, i.e. all terms must be satisfied.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodantiaffinity)</sup></sup>



The weights of all of the matched WeightedPodAffinityTerm fields are added per-node to find the most preferred node(s)

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinityterm">podAffinityTerm</a></b></td>
        <td>object</td>
        <td>Required. A pod affinity term, associated with the corresponding weight.</td>
        <td>true</td>
      </tr><tr>
        <td><b>weight</b></td>
        <td>integer</td>
        <td>weight associated with matching the corresponding podAffinityTerm, in the range 1-100.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindex)</sup></sup>



Required. A pod affinity term, associated with the corresponding weight.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselector">labelSelector</a></b></td>
        <td>object</td>
        <td>A label query over a set of resources, in this case pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>namespaces</b></td>
        <td>[]string</td>
        <td>namespaces specifies which namespaces the labelSelector applies to (matches against); null or empty list means "this pod's namespace"</td>
        <td>false</td>
      </tr><tr>
        <td><b>topologyKey</b></td>
        <td>string</td>
        <td>This pod should be co-located (affinity) or not co-located (anti-affinity) with the pods matching the labelSelector in the specified namespaces, where co-located is defined as running on a node whose value of the label with key topologyKey matches that of any node on which any of the selected pods is running. Empty topologyKey is not allowed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm.labelSelector
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinityterm)</sup></sup>



A label query over a set of resources, in this case pods.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm.labelSelector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAntiAffinity.requiredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodantiaffinity)</sup></sup>



Defines a set of pods (namely those matching the labelSelector relative to the given namespace(s)) that this pod should be co-located (affinity) or not co-located (anti-affinity) with, where co-located is defined as running on a node whose value of the label with key <topologyKey> matches that of any node on which a pod of the set of pods is running

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindexlabelselector">labelSelector</a></b></td>
        <td>object</td>
        <td>A label query over a set of resources, in this case pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>namespaces</b></td>
        <td>[]string</td>
        <td>namespaces specifies which namespaces the labelSelector applies to (matches against); null or empty list means "this pod's namespace"</td>
        <td>false</td>
      </tr><tr>
        <td><b>topologyKey</b></td>
        <td>string</td>
        <td>This pod should be co-located (affinity) or not co-located (anti-affinity) with the pods matching the labelSelector in the specified namespaces, where co-located is defined as running on a node whose value of the label with key topologyKey matches that of any node on which any of the selected pods is running. Empty topologyKey is not allowed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAntiAffinity.requiredDuringSchedulingIgnoredDuringExecution[index].labelSelector
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindex)</sup></sup>



A label query over a set of resources, in this case pods.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbounceraffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindexlabelselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.affinity.podAntiAffinity.requiredDuringSchedulingIgnoredDuringExecution[index].labelSelector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbounceraffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindexlabelselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.config
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncer)</sup></sup>



Configuration settings for the PgBouncer process. Changes to any of these values will be automatically reloaded without validation. Be careful, as you may put PgBouncer into an unusable state. More info: https://www.pgbouncer.org/usage.html#reload

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>databases</b></td>
        <td>map[string]string</td>
        <td>PgBouncer database definitions. The key is the database requested by a client while the value is a libpq-styled connection string. The special key "*" acts as a fallback. When this field is empty, PgBouncer is configured with a single "*" entry that connects to the primary PostgreSQL instance. More info: https://www.pgbouncer.org/config.html#section-databases</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncerconfigfilesindex">files</a></b></td>
        <td>[]object</td>
        <td>Files to mount under "/etc/pgbouncer". When specified, settings in the "pgbouncer.ini" file are loaded before all others. From there, other files may be included by absolute path. Changing these references causes PgBouncer to restart, but changes to the file contents are automatically reloaded. More info: https://www.pgbouncer.org/config.html#include-directive</td>
        <td>false</td>
      </tr><tr>
        <td><b>global</b></td>
        <td>map[string]string</td>
        <td>Settings that apply to the entire PgBouncer process. More info: https://www.pgbouncer.org/config.html</td>
        <td>false</td>
      </tr><tr>
        <td><b>users</b></td>
        <td>map[string]string</td>
        <td>Connection settings specific to particular users. More info: https://www.pgbouncer.org/config.html#section-users</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.config.files[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncerconfig)</sup></sup>



Projection that may be projected along with other supported volume types

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncerconfigfilesindexconfigmap">configMap</a></b></td>
        <td>object</td>
        <td>information about the configMap data to project</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncerconfigfilesindexdownwardapi">downwardAPI</a></b></td>
        <td>object</td>
        <td>information about the downwardAPI data to project</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncerconfigfilesindexsecret">secret</a></b></td>
        <td>object</td>
        <td>information about the secret data to project</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncerconfigfilesindexserviceaccounttoken">serviceAccountToken</a></b></td>
        <td>object</td>
        <td>information about the serviceAccountToken data to project</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.config.files[index].configMap
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncerconfigfilesindex)</sup></sup>



information about the configMap data to project

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncerconfigfilesindexconfigmapitemsindex">items</a></b></td>
        <td>[]object</td>
        <td>If unspecified, each key-value pair in the Data field of the referenced ConfigMap will be projected into the volume as a file whose name is the key and content is the value. If specified, the listed keys will be projected into the specified paths, and unlisted keys will not be present. If a key is specified which is not present in the ConfigMap, the volume setup will error unless it is marked optional. Paths must be relative and may not contain the '..' path or start with '..'.</td>
        <td>false</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>Name of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#names TODO: Add other useful fields. apiVersion, kind, uid?</td>
        <td>false</td>
      </tr><tr>
        <td><b>optional</b></td>
        <td>boolean</td>
        <td>Specify whether the ConfigMap or its keys must be defined</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.config.files[index].configMap.items[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncerconfigfilesindexconfigmap)</sup></sup>



Maps a string key to a path within a volume.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>mode</b></td>
        <td>integer</td>
        <td>Optional: mode bits used to set permissions on this file. Must be an octal value between 0000 and 0777 or a decimal value between 0 and 511. YAML accepts both octal and decimal values, JSON requires decimal values for mode bits. If not specified, the volume defaultMode will be used. This might be in conflict with other options that affect the file mode, like fsGroup, and the result can be other mode bits set.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The key to project.</td>
        <td>true</td>
      </tr><tr>
        <td><b>path</b></td>
        <td>string</td>
        <td>The relative path of the file to map the key to. May not be an absolute path. May not contain the path element '..'. May not start with the string '..'.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.config.files[index].downwardAPI
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncerconfigfilesindex)</sup></sup>



information about the downwardAPI data to project

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncerconfigfilesindexdownwardapiitemsindex">items</a></b></td>
        <td>[]object</td>
        <td>Items is a list of DownwardAPIVolume file</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.config.files[index].downwardAPI.items[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncerconfigfilesindexdownwardapi)</sup></sup>



DownwardAPIVolumeFile represents information to create the file containing the pod field

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncerconfigfilesindexdownwardapiitemsindexfieldref">fieldRef</a></b></td>
        <td>object</td>
        <td>Required: Selects a field of the pod: only annotations, labels, name and namespace are supported.</td>
        <td>false</td>
      </tr><tr>
        <td><b>mode</b></td>
        <td>integer</td>
        <td>Optional: mode bits used to set permissions on this file, must be an octal value between 0000 and 0777 or a decimal value between 0 and 511. YAML accepts both octal and decimal values, JSON requires decimal values for mode bits. If not specified, the volume defaultMode will be used. This might be in conflict with other options that affect the file mode, like fsGroup, and the result can be other mode bits set.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncerconfigfilesindexdownwardapiitemsindexresourcefieldref">resourceFieldRef</a></b></td>
        <td>object</td>
        <td>Selects a resource of the container: only resources limits and requests (limits.cpu, limits.memory, requests.cpu and requests.memory) are currently supported.</td>
        <td>false</td>
      </tr><tr>
        <td><b>path</b></td>
        <td>string</td>
        <td>Required: Path is  the relative path name of the file to be created. Must not be absolute or contain the '..' path. Must be utf-8 encoded. The first item of the relative path must not start with '..'</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.config.files[index].downwardAPI.items[index].fieldRef
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncerconfigfilesindexdownwardapiitemsindex)</sup></sup>



Required: Selects a field of the pod: only annotations, labels, name and namespace are supported.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>apiVersion</b></td>
        <td>string</td>
        <td>Version of the schema the FieldPath is written in terms of, defaults to "v1".</td>
        <td>false</td>
      </tr><tr>
        <td><b>fieldPath</b></td>
        <td>string</td>
        <td>Path of the field to select in the specified API version.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.config.files[index].downwardAPI.items[index].resourceFieldRef
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncerconfigfilesindexdownwardapiitemsindex)</sup></sup>



Selects a resource of the container: only resources limits and requests (limits.cpu, limits.memory, requests.cpu and requests.memory) are currently supported.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>containerName</b></td>
        <td>string</td>
        <td>Container name: required for volumes, optional for env vars</td>
        <td>false</td>
      </tr><tr>
        <td><b>divisor</b></td>
        <td>int or string</td>
        <td>Specifies the output format of the exposed resources, defaults to "1"</td>
        <td>false</td>
      </tr><tr>
        <td><b>resource</b></td>
        <td>string</td>
        <td>Required: resource to select</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.config.files[index].secret
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncerconfigfilesindex)</sup></sup>



information about the secret data to project

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncerconfigfilesindexsecretitemsindex">items</a></b></td>
        <td>[]object</td>
        <td>If unspecified, each key-value pair in the Data field of the referenced Secret will be projected into the volume as a file whose name is the key and content is the value. If specified, the listed keys will be projected into the specified paths, and unlisted keys will not be present. If a key is specified which is not present in the Secret, the volume setup will error unless it is marked optional. Paths must be relative and may not contain the '..' path or start with '..'.</td>
        <td>false</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>Name of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#names TODO: Add other useful fields. apiVersion, kind, uid?</td>
        <td>false</td>
      </tr><tr>
        <td><b>optional</b></td>
        <td>boolean</td>
        <td>Specify whether the Secret or its key must be defined</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.config.files[index].secret.items[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncerconfigfilesindexsecret)</sup></sup>



Maps a string key to a path within a volume.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>mode</b></td>
        <td>integer</td>
        <td>Optional: mode bits used to set permissions on this file. Must be an octal value between 0000 and 0777 or a decimal value between 0 and 511. YAML accepts both octal and decimal values, JSON requires decimal values for mode bits. If not specified, the volume defaultMode will be used. This might be in conflict with other options that affect the file mode, like fsGroup, and the result can be other mode bits set.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The key to project.</td>
        <td>true</td>
      </tr><tr>
        <td><b>path</b></td>
        <td>string</td>
        <td>The relative path of the file to map the key to. May not be an absolute path. May not contain the path element '..'. May not start with the string '..'.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.config.files[index].serviceAccountToken
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncerconfigfilesindex)</sup></sup>



information about the serviceAccountToken data to project

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>audience</b></td>
        <td>string</td>
        <td>Audience is the intended audience of the token. A recipient of a token must identify itself with an identifier specified in the audience of the token, and otherwise should reject the token. The audience defaults to the identifier of the apiserver.</td>
        <td>false</td>
      </tr><tr>
        <td><b>expirationSeconds</b></td>
        <td>integer</td>
        <td>ExpirationSeconds is the requested duration of validity of the service account token. As the token approaches expiration, the kubelet volume plugin will proactively rotate the service account token. The kubelet will start trying to rotate the token if the token is older than 80 percent of its time to live or if the token is older than 24 hours.Defaults to 1 hour and must be at least 10 minutes.</td>
        <td>false</td>
      </tr><tr>
        <td><b>path</b></td>
        <td>string</td>
        <td>Path is the path relative to the mount point of the file to project the token into.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.customTLSSecret
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncer)</sup></sup>



A secret projection containing a certificate and key with which to encrypt connections to PgBouncer. The "tls.crt", "tls.key", and "ca.crt" paths must be PEM-encoded certificates and keys. Changing this value causes PgBouncer to restart. More info: https://kubernetes.io/docs/concepts/configuration/secret/#projection-of-secret-keys-to-specific-paths

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecproxypgbouncercustomtlssecretitemsindex">items</a></b></td>
        <td>[]object</td>
        <td>If unspecified, each key-value pair in the Data field of the referenced Secret will be projected into the volume as a file whose name is the key and content is the value. If specified, the listed keys will be projected into the specified paths, and unlisted keys will not be present. If a key is specified which is not present in the Secret, the volume setup will error unless it is marked optional. Paths must be relative and may not contain the '..' path or start with '..'.</td>
        <td>false</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>Name of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#names TODO: Add other useful fields. apiVersion, kind, uid?</td>
        <td>false</td>
      </tr><tr>
        <td><b>optional</b></td>
        <td>boolean</td>
        <td>Specify whether the Secret or its key must be defined</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.customTLSSecret.items[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncercustomtlssecret)</sup></sup>



Maps a string key to a path within a volume.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>mode</b></td>
        <td>integer</td>
        <td>Optional: mode bits used to set permissions on this file. Must be an octal value between 0000 and 0777 or a decimal value between 0 and 511. YAML accepts both octal and decimal values, JSON requires decimal values for mode bits. If not specified, the volume defaultMode will be used. This might be in conflict with other options that affect the file mode, like fsGroup, and the result can be other mode bits set.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The key to project.</td>
        <td>true</td>
      </tr><tr>
        <td><b>path</b></td>
        <td>string</td>
        <td>The relative path of the file to map the key to. May not be an absolute path. May not contain the path element '..'. May not start with the string '..'.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.metadata
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncer)</sup></sup>



Metadata contains metadata for PostgresCluster resources

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>annotations</b></td>
        <td>map[string]string</td>
        <td></td>
        <td>false</td>
      </tr><tr>
        <td><b>labels</b></td>
        <td>map[string]string</td>
        <td></td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.resources
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncer)</sup></sup>



Compute resources of a PgBouncer container. Changing this value causes PgBouncer to restart. More info: https://kubernetes.io/docs/concepts/configuration/manage-resources-containers

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>limits</b></td>
        <td>map[string]int or string</td>
        <td>Limits describes the maximum amount of compute resources allowed. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr><tr>
        <td><b>requests</b></td>
        <td>map[string]int or string</td>
        <td>Requests describes the minimum amount of compute resources required. If Requests is omitted for a container, it defaults to Limits if that is explicitly specified, otherwise to an implementation-defined value. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.proxy.pgBouncer.tolerations[index]
<sup><sup>[↩ Parent](#postgresclusterspecproxypgbouncer)</sup></sup>



The pod this Toleration is attached to tolerates any taint that matches the triple <key,value,effect> using the matching operator <operator>.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>effect</b></td>
        <td>string</td>
        <td>Effect indicates the taint effect to match. Empty means match all taint effects. When specified, allowed values are NoSchedule, PreferNoSchedule and NoExecute.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>Key is the taint key that the toleration applies to. Empty means match all taint keys. If the key is empty, operator must be Exists; this combination means to match all values and all keys.</td>
        <td>false</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>Operator represents a key's relationship to the value. Valid operators are Exists and Equal. Defaults to Equal. Exists is equivalent to wildcard for value, so that a pod can tolerate all taints of a particular category.</td>
        <td>false</td>
      </tr><tr>
        <td><b>tolerationSeconds</b></td>
        <td>integer</td>
        <td>TolerationSeconds represents the period of time the toleration (which must be of effect NoExecute, otherwise this field is ignored) tolerates the taint. By default, it is not set, which means tolerate the taint forever (do not evict). Zero and negative values will be treated as 0 (evict immediately) by the system.</td>
        <td>false</td>
      </tr><tr>
        <td><b>value</b></td>
        <td>string</td>
        <td>Value is the taint value the toleration matches to. If the operator is Exists, the value should be empty, otherwise just a regular string.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive
<sup><sup>[↩ Parent](#postgresclusterspec)</sup></sup>



PostgreSQL archive configuration

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrest">pgbackrest</a></b></td>
        <td>object</td>
        <td>pgBackRest archive configuration</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest
<sup><sup>[↩ Parent](#postgresclusterspecarchive)</sup></sup>



pgBackRest archive configuration

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestconfigurationindex">configuration</a></b></td>
        <td>[]object</td>
        <td>Projected volumes containing custom pgBackRest configuration.  These files are mounted under "/etc/pgbackrest/conf.d" alongside any pgBackRest configuration generated by the PostgreSQL Operator: https://pgbackrest.org/configuration.html</td>
        <td>false</td>
      </tr><tr>
        <td><b>global</b></td>
        <td>map[string]string</td>
        <td>Global pgBackRest configuration settings.  These settings are included in the "global" section of the pgBackRest configuration generated by the PostgreSQL Operator, and then mounted under "/etc/pgbackrest/conf.d": https://pgbackrest.org/configuration.html</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestmanual">manual</a></b></td>
        <td>object</td>
        <td>Defines details for manual pgBackRest backup Jobs</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestmetadata">metadata</a></b></td>
        <td>object</td>
        <td>Metadata contains metadata for PostgresCluster resources</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohost">repoHost</a></b></td>
        <td>object</td>
        <td>Defines a pgBackRest repository host</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestreposindex">repos</a></b></td>
        <td>[]object</td>
        <td>Defines a pgBackRest repository</td>
        <td>false</td>
      </tr><tr>
        <td><b>image</b></td>
        <td>string</td>
        <td>The image name to use for pgBackRest containers.  Utilized to run pgBackRest repository hosts and backups.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.configuration[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrest)</sup></sup>



Projection that may be projected along with other supported volume types

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestconfigurationindexconfigmap">configMap</a></b></td>
        <td>object</td>
        <td>information about the configMap data to project</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestconfigurationindexdownwardapi">downwardAPI</a></b></td>
        <td>object</td>
        <td>information about the downwardAPI data to project</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestconfigurationindexsecret">secret</a></b></td>
        <td>object</td>
        <td>information about the secret data to project</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestconfigurationindexserviceaccounttoken">serviceAccountToken</a></b></td>
        <td>object</td>
        <td>information about the serviceAccountToken data to project</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.configuration[index].configMap
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestconfigurationindex)</sup></sup>



information about the configMap data to project

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestconfigurationindexconfigmapitemsindex">items</a></b></td>
        <td>[]object</td>
        <td>If unspecified, each key-value pair in the Data field of the referenced ConfigMap will be projected into the volume as a file whose name is the key and content is the value. If specified, the listed keys will be projected into the specified paths, and unlisted keys will not be present. If a key is specified which is not present in the ConfigMap, the volume setup will error unless it is marked optional. Paths must be relative and may not contain the '..' path or start with '..'.</td>
        <td>false</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>Name of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#names TODO: Add other useful fields. apiVersion, kind, uid?</td>
        <td>false</td>
      </tr><tr>
        <td><b>optional</b></td>
        <td>boolean</td>
        <td>Specify whether the ConfigMap or its keys must be defined</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.configuration[index].configMap.items[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestconfigurationindexconfigmap)</sup></sup>



Maps a string key to a path within a volume.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>mode</b></td>
        <td>integer</td>
        <td>Optional: mode bits used to set permissions on this file. Must be an octal value between 0000 and 0777 or a decimal value between 0 and 511. YAML accepts both octal and decimal values, JSON requires decimal values for mode bits. If not specified, the volume defaultMode will be used. This might be in conflict with other options that affect the file mode, like fsGroup, and the result can be other mode bits set.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The key to project.</td>
        <td>true</td>
      </tr><tr>
        <td><b>path</b></td>
        <td>string</td>
        <td>The relative path of the file to map the key to. May not be an absolute path. May not contain the path element '..'. May not start with the string '..'.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.configuration[index].downwardAPI
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestconfigurationindex)</sup></sup>



information about the downwardAPI data to project

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestconfigurationindexdownwardapiitemsindex">items</a></b></td>
        <td>[]object</td>
        <td>Items is a list of DownwardAPIVolume file</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.configuration[index].downwardAPI.items[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestconfigurationindexdownwardapi)</sup></sup>



DownwardAPIVolumeFile represents information to create the file containing the pod field

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestconfigurationindexdownwardapiitemsindexfieldref">fieldRef</a></b></td>
        <td>object</td>
        <td>Required: Selects a field of the pod: only annotations, labels, name and namespace are supported.</td>
        <td>false</td>
      </tr><tr>
        <td><b>mode</b></td>
        <td>integer</td>
        <td>Optional: mode bits used to set permissions on this file, must be an octal value between 0000 and 0777 or a decimal value between 0 and 511. YAML accepts both octal and decimal values, JSON requires decimal values for mode bits. If not specified, the volume defaultMode will be used. This might be in conflict with other options that affect the file mode, like fsGroup, and the result can be other mode bits set.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestconfigurationindexdownwardapiitemsindexresourcefieldref">resourceFieldRef</a></b></td>
        <td>object</td>
        <td>Selects a resource of the container: only resources limits and requests (limits.cpu, limits.memory, requests.cpu and requests.memory) are currently supported.</td>
        <td>false</td>
      </tr><tr>
        <td><b>path</b></td>
        <td>string</td>
        <td>Required: Path is  the relative path name of the file to be created. Must not be absolute or contain the '..' path. Must be utf-8 encoded. The first item of the relative path must not start with '..'</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.configuration[index].downwardAPI.items[index].fieldRef
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestconfigurationindexdownwardapiitemsindex)</sup></sup>



Required: Selects a field of the pod: only annotations, labels, name and namespace are supported.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>apiVersion</b></td>
        <td>string</td>
        <td>Version of the schema the FieldPath is written in terms of, defaults to "v1".</td>
        <td>false</td>
      </tr><tr>
        <td><b>fieldPath</b></td>
        <td>string</td>
        <td>Path of the field to select in the specified API version.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.configuration[index].downwardAPI.items[index].resourceFieldRef
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestconfigurationindexdownwardapiitemsindex)</sup></sup>



Selects a resource of the container: only resources limits and requests (limits.cpu, limits.memory, requests.cpu and requests.memory) are currently supported.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>containerName</b></td>
        <td>string</td>
        <td>Container name: required for volumes, optional for env vars</td>
        <td>false</td>
      </tr><tr>
        <td><b>divisor</b></td>
        <td>int or string</td>
        <td>Specifies the output format of the exposed resources, defaults to "1"</td>
        <td>false</td>
      </tr><tr>
        <td><b>resource</b></td>
        <td>string</td>
        <td>Required: resource to select</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.configuration[index].secret
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestconfigurationindex)</sup></sup>



information about the secret data to project

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestconfigurationindexsecretitemsindex">items</a></b></td>
        <td>[]object</td>
        <td>If unspecified, each key-value pair in the Data field of the referenced Secret will be projected into the volume as a file whose name is the key and content is the value. If specified, the listed keys will be projected into the specified paths, and unlisted keys will not be present. If a key is specified which is not present in the Secret, the volume setup will error unless it is marked optional. Paths must be relative and may not contain the '..' path or start with '..'.</td>
        <td>false</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>Name of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#names TODO: Add other useful fields. apiVersion, kind, uid?</td>
        <td>false</td>
      </tr><tr>
        <td><b>optional</b></td>
        <td>boolean</td>
        <td>Specify whether the Secret or its key must be defined</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.configuration[index].secret.items[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestconfigurationindexsecret)</sup></sup>



Maps a string key to a path within a volume.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>mode</b></td>
        <td>integer</td>
        <td>Optional: mode bits used to set permissions on this file. Must be an octal value between 0000 and 0777 or a decimal value between 0 and 511. YAML accepts both octal and decimal values, JSON requires decimal values for mode bits. If not specified, the volume defaultMode will be used. This might be in conflict with other options that affect the file mode, like fsGroup, and the result can be other mode bits set.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The key to project.</td>
        <td>true</td>
      </tr><tr>
        <td><b>path</b></td>
        <td>string</td>
        <td>The relative path of the file to map the key to. May not be an absolute path. May not contain the path element '..'. May not start with the string '..'.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.configuration[index].serviceAccountToken
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestconfigurationindex)</sup></sup>



information about the serviceAccountToken data to project

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>audience</b></td>
        <td>string</td>
        <td>Audience is the intended audience of the token. A recipient of a token must identify itself with an identifier specified in the audience of the token, and otherwise should reject the token. The audience defaults to the identifier of the apiserver.</td>
        <td>false</td>
      </tr><tr>
        <td><b>expirationSeconds</b></td>
        <td>integer</td>
        <td>ExpirationSeconds is the requested duration of validity of the service account token. As the token approaches expiration, the kubelet volume plugin will proactively rotate the service account token. The kubelet will start trying to rotate the token if the token is older than 80 percent of its time to live or if the token is older than 24 hours.Defaults to 1 hour and must be at least 10 minutes.</td>
        <td>false</td>
      </tr><tr>
        <td><b>path</b></td>
        <td>string</td>
        <td>Path is the path relative to the mount point of the file to project the token into.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.manual
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrest)</sup></sup>



Defines details for manual pgBackRest backup Jobs

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>options</b></td>
        <td>[]string</td>
        <td>Command line options to include when running the pgBackRest backup command. https://pgbackrest.org/command.html#command-backup</td>
        <td>false</td>
      </tr><tr>
        <td><b>repoName</b></td>
        <td>string</td>
        <td>The name of the pgBackRest repo to run the backup command against.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.metadata
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrest)</sup></sup>



Metadata contains metadata for PostgresCluster resources

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>annotations</b></td>
        <td>map[string]string</td>
        <td></td>
        <td>false</td>
      </tr><tr>
        <td><b>labels</b></td>
        <td>map[string]string</td>
        <td></td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrest)</sup></sup>



Defines a pgBackRest repository host

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicated">dedicated</a></b></td>
        <td>object</td>
        <td>Defines a dedicated repository host configuration</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostresources">resources</a></b></td>
        <td>object</td>
        <td>Resource requirements for a pgBackRest repository host</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostsshconfigmap">sshConfigMap</a></b></td>
        <td>object</td>
        <td>ConfigMap containing custom SSH configuration</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostsshsecret">sshSecret</a></b></td>
        <td>object</td>
        <td>Secret containing custom SSH keys</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohost)</sup></sup>



Defines a dedicated repository host configuration

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinity">affinity</a></b></td>
        <td>object</td>
        <td>Scheduling constraints of the Dedicated repo host pod. Changing this value causes repo host to restart. More info: https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedresources">resources</a></b></td>
        <td>object</td>
        <td>Resource requirements for the dedicated repository host</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicated)</sup></sup>



Scheduling constraints of the Dedicated repo host pod. Changing this value causes repo host to restart. More info: https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinity">nodeAffinity</a></b></td>
        <td>object</td>
        <td>Describes node affinity scheduling rules for the pod.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinity">podAffinity</a></b></td>
        <td>object</td>
        <td>Describes pod affinity scheduling rules (e.g. co-locate this pod in the same node, zone, etc. as some other pod(s)).</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinity">podAntiAffinity</a></b></td>
        <td>object</td>
        <td>Describes pod anti-affinity scheduling rules (e.g. avoid putting this pod in the same node, zone, etc. as some other pod(s)).</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.nodeAffinity
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinity)</sup></sup>



Describes node affinity scheduling rules for the pod.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindex">preferredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>The scheduler will prefer to schedule pods to nodes that satisfy the affinity expressions specified by this field, but it may choose a node that violates one or more of the expressions. The node that is most preferred is the one with the greatest sum of weights, i.e. for each node that meets all of the scheduling requirements (resource request, requiredDuringScheduling affinity expressions, etc.), compute a sum by iterating through the elements of this field and adding "weight" to the sum if the node matches the corresponding matchExpressions; the node(s) with the highest sum are the most preferred.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinityrequiredduringschedulingignoredduringexecution">requiredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>object</td>
        <td>If the affinity requirements specified by this field are not met at scheduling time, the pod will not be scheduled onto the node. If the affinity requirements specified by this field cease to be met at some point during pod execution (e.g. due to an update), the system may or may not try to eventually evict the pod from its node.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinity)</sup></sup>



An empty preferred scheduling term matches all objects with implicit weight 0 (i.e. it's a no-op). A null preferred scheduling term matches no objects (i.e. is also a no-op).

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreference">preference</a></b></td>
        <td>object</td>
        <td>A node selector term, associated with the corresponding weight.</td>
        <td>true</td>
      </tr><tr>
        <td><b>weight</b></td>
        <td>integer</td>
        <td>Weight associated with matching the corresponding nodeSelectorTerm, in the range 1-100.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].preference
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindex)</sup></sup>



A node selector term, associated with the corresponding weight.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreferencematchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>A list of node selector requirements by node's labels.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreferencematchfieldsindex">matchFields</a></b></td>
        <td>[]object</td>
        <td>A list of node selector requirements by node's fields.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].preference.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreference)</sup></sup>



A node selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. If the operator is Gt or Lt, the values array must have a single element, which will be interpreted as an integer. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>Represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist. Gt, and Lt.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].preference.matchFields[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreference)</sup></sup>



A node selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. If the operator is Gt or Lt, the values array must have a single element, which will be interpreted as an integer. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>Represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist. Gt, and Lt.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinity)</sup></sup>



If the affinity requirements specified by this field are not met at scheduling time, the pod will not be scheduled onto the node. If the affinity requirements specified by this field cease to be met at some point during pod execution (e.g. due to an update), the system may or may not try to eventually evict the pod from its node.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindex">nodeSelectorTerms</a></b></td>
        <td>[]object</td>
        <td>Required. A list of node selector terms. The terms are ORed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinityrequiredduringschedulingignoredduringexecution)</sup></sup>



A null or empty node selector term matches no objects. The requirements of them are ANDed. The TopologySelectorTerm type implements a subset of the NodeSelectorTerm.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindexmatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>A list of node selector requirements by node's labels.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindexmatchfieldsindex">matchFields</a></b></td>
        <td>[]object</td>
        <td>A list of node selector requirements by node's fields.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[index].matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindex)</sup></sup>



A node selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. If the operator is Gt or Lt, the values array must have a single element, which will be interpreted as an integer. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>Represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist. Gt, and Lt.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[index].matchFields[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindex)</sup></sup>



A node selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. If the operator is Gt or Lt, the values array must have a single element, which will be interpreted as an integer. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>Represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist. Gt, and Lt.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAffinity
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinity)</sup></sup>



Describes pod affinity scheduling rules (e.g. co-locate this pod in the same node, zone, etc. as some other pod(s)).

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindex">preferredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>The scheduler will prefer to schedule pods to nodes that satisfy the affinity expressions specified by this field, but it may choose a node that violates one or more of the expressions. The node that is most preferred is the one with the greatest sum of weights, i.e. for each node that meets all of the scheduling requirements (resource request, requiredDuringScheduling affinity expressions, etc.), compute a sum by iterating through the elements of this field and adding "weight" to the sum if the node has pods which matches the corresponding podAffinityTerm; the node(s) with the highest sum are the most preferred.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinityrequiredduringschedulingignoredduringexecutionindex">requiredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>If the affinity requirements specified by this field are not met at scheduling time, the pod will not be scheduled onto the node. If the affinity requirements specified by this field cease to be met at some point during pod execution (e.g. due to a pod label update), the system may or may not try to eventually evict the pod from its node. When there are multiple elements, the lists of nodes corresponding to each podAffinityTerm are intersected, i.e. all terms must be satisfied.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAffinity.preferredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinity)</sup></sup>



The weights of all of the matched WeightedPodAffinityTerm fields are added per-node to find the most preferred node(s)

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinityterm">podAffinityTerm</a></b></td>
        <td>object</td>
        <td>Required. A pod affinity term, associated with the corresponding weight.</td>
        <td>true</td>
      </tr><tr>
        <td><b>weight</b></td>
        <td>integer</td>
        <td>weight associated with matching the corresponding podAffinityTerm, in the range 1-100.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindex)</sup></sup>



Required. A pod affinity term, associated with the corresponding weight.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselector">labelSelector</a></b></td>
        <td>object</td>
        <td>A label query over a set of resources, in this case pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>namespaces</b></td>
        <td>[]string</td>
        <td>namespaces specifies which namespaces the labelSelector applies to (matches against); null or empty list means "this pod's namespace"</td>
        <td>false</td>
      </tr><tr>
        <td><b>topologyKey</b></td>
        <td>string</td>
        <td>This pod should be co-located (affinity) or not co-located (anti-affinity) with the pods matching the labelSelector in the specified namespaces, where co-located is defined as running on a node whose value of the label with key topologyKey matches that of any node on which any of the selected pods is running. Empty topologyKey is not allowed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm.labelSelector
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinityterm)</sup></sup>



A label query over a set of resources, in this case pods.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm.labelSelector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAffinity.requiredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinity)</sup></sup>



Defines a set of pods (namely those matching the labelSelector relative to the given namespace(s)) that this pod should be co-located (affinity) or not co-located (anti-affinity) with, where co-located is defined as running on a node whose value of the label with key <topologyKey> matches that of any node on which a pod of the set of pods is running

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinityrequiredduringschedulingignoredduringexecutionindexlabelselector">labelSelector</a></b></td>
        <td>object</td>
        <td>A label query over a set of resources, in this case pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>namespaces</b></td>
        <td>[]string</td>
        <td>namespaces specifies which namespaces the labelSelector applies to (matches against); null or empty list means "this pod's namespace"</td>
        <td>false</td>
      </tr><tr>
        <td><b>topologyKey</b></td>
        <td>string</td>
        <td>This pod should be co-located (affinity) or not co-located (anti-affinity) with the pods matching the labelSelector in the specified namespaces, where co-located is defined as running on a node whose value of the label with key topologyKey matches that of any node on which any of the selected pods is running. Empty topologyKey is not allowed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAffinity.requiredDuringSchedulingIgnoredDuringExecution[index].labelSelector
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinityrequiredduringschedulingignoredduringexecutionindex)</sup></sup>



A label query over a set of resources, in this case pods.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinityrequiredduringschedulingignoredduringexecutionindexlabelselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAffinity.requiredDuringSchedulingIgnoredDuringExecution[index].labelSelector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodaffinityrequiredduringschedulingignoredduringexecutionindexlabelselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAntiAffinity
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinity)</sup></sup>



Describes pod anti-affinity scheduling rules (e.g. avoid putting this pod in the same node, zone, etc. as some other pod(s)).

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindex">preferredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>The scheduler will prefer to schedule pods to nodes that satisfy the anti-affinity expressions specified by this field, but it may choose a node that violates one or more of the expressions. The node that is most preferred is the one with the greatest sum of weights, i.e. for each node that meets all of the scheduling requirements (resource request, requiredDuringScheduling anti-affinity expressions, etc.), compute a sum by iterating through the elements of this field and adding "weight" to the sum if the node has pods which matches the corresponding podAffinityTerm; the node(s) with the highest sum are the most preferred.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindex">requiredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>If the anti-affinity requirements specified by this field are not met at scheduling time, the pod will not be scheduled onto the node. If the anti-affinity requirements specified by this field cease to be met at some point during pod execution (e.g. due to a pod label update), the system may or may not try to eventually evict the pod from its node. When there are multiple elements, the lists of nodes corresponding to each podAffinityTerm are intersected, i.e. all terms must be satisfied.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinity)</sup></sup>



The weights of all of the matched WeightedPodAffinityTerm fields are added per-node to find the most preferred node(s)

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinityterm">podAffinityTerm</a></b></td>
        <td>object</td>
        <td>Required. A pod affinity term, associated with the corresponding weight.</td>
        <td>true</td>
      </tr><tr>
        <td><b>weight</b></td>
        <td>integer</td>
        <td>weight associated with matching the corresponding podAffinityTerm, in the range 1-100.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindex)</sup></sup>



Required. A pod affinity term, associated with the corresponding weight.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselector">labelSelector</a></b></td>
        <td>object</td>
        <td>A label query over a set of resources, in this case pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>namespaces</b></td>
        <td>[]string</td>
        <td>namespaces specifies which namespaces the labelSelector applies to (matches against); null or empty list means "this pod's namespace"</td>
        <td>false</td>
      </tr><tr>
        <td><b>topologyKey</b></td>
        <td>string</td>
        <td>This pod should be co-located (affinity) or not co-located (anti-affinity) with the pods matching the labelSelector in the specified namespaces, where co-located is defined as running on a node whose value of the label with key topologyKey matches that of any node on which any of the selected pods is running. Empty topologyKey is not allowed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm.labelSelector
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinityterm)</sup></sup>



A label query over a set of resources, in this case pods.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm.labelSelector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAntiAffinity.requiredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinity)</sup></sup>



Defines a set of pods (namely those matching the labelSelector relative to the given namespace(s)) that this pod should be co-located (affinity) or not co-located (anti-affinity) with, where co-located is defined as running on a node whose value of the label with key <topologyKey> matches that of any node on which a pod of the set of pods is running

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindexlabelselector">labelSelector</a></b></td>
        <td>object</td>
        <td>A label query over a set of resources, in this case pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>namespaces</b></td>
        <td>[]string</td>
        <td>namespaces specifies which namespaces the labelSelector applies to (matches against); null or empty list means "this pod's namespace"</td>
        <td>false</td>
      </tr><tr>
        <td><b>topologyKey</b></td>
        <td>string</td>
        <td>This pod should be co-located (affinity) or not co-located (anti-affinity) with the pods matching the labelSelector in the specified namespaces, where co-located is defined as running on a node whose value of the label with key topologyKey matches that of any node on which any of the selected pods is running. Empty topologyKey is not allowed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAntiAffinity.requiredDuringSchedulingIgnoredDuringExecution[index].labelSelector
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindex)</sup></sup>



A label query over a set of resources, in this case pods.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindexlabelselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.affinity.podAntiAffinity.requiredDuringSchedulingIgnoredDuringExecution[index].labelSelector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicatedaffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindexlabelselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.dedicated.resources
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostdedicated)</sup></sup>



Resource requirements for the dedicated repository host

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>limits</b></td>
        <td>map[string]int or string</td>
        <td>Limits describes the maximum amount of compute resources allowed. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr><tr>
        <td><b>requests</b></td>
        <td>map[string]int or string</td>
        <td>Requests describes the minimum amount of compute resources required. If Requests is omitted for a container, it defaults to Limits if that is explicitly specified, otherwise to an implementation-defined value. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.resources
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohost)</sup></sup>



Resource requirements for a pgBackRest repository host

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>limits</b></td>
        <td>map[string]int or string</td>
        <td>Limits describes the maximum amount of compute resources allowed. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr><tr>
        <td><b>requests</b></td>
        <td>map[string]int or string</td>
        <td>Requests describes the minimum amount of compute resources required. If Requests is omitted for a container, it defaults to Limits if that is explicitly specified, otherwise to an implementation-defined value. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.sshConfigMap
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohost)</sup></sup>



ConfigMap containing custom SSH configuration

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostsshconfigmapitemsindex">items</a></b></td>
        <td>[]object</td>
        <td>If unspecified, each key-value pair in the Data field of the referenced ConfigMap will be projected into the volume as a file whose name is the key and content is the value. If specified, the listed keys will be projected into the specified paths, and unlisted keys will not be present. If a key is specified which is not present in the ConfigMap, the volume setup will error unless it is marked optional. Paths must be relative and may not contain the '..' path or start with '..'.</td>
        <td>false</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>Name of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#names TODO: Add other useful fields. apiVersion, kind, uid?</td>
        <td>false</td>
      </tr><tr>
        <td><b>optional</b></td>
        <td>boolean</td>
        <td>Specify whether the ConfigMap or its keys must be defined</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.sshConfigMap.items[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostsshconfigmap)</sup></sup>



Maps a string key to a path within a volume.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>mode</b></td>
        <td>integer</td>
        <td>Optional: mode bits used to set permissions on this file. Must be an octal value between 0000 and 0777 or a decimal value between 0 and 511. YAML accepts both octal and decimal values, JSON requires decimal values for mode bits. If not specified, the volume defaultMode will be used. This might be in conflict with other options that affect the file mode, like fsGroup, and the result can be other mode bits set.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The key to project.</td>
        <td>true</td>
      </tr><tr>
        <td><b>path</b></td>
        <td>string</td>
        <td>The relative path of the file to map the key to. May not be an absolute path. May not contain the path element '..'. May not start with the string '..'.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.sshSecret
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohost)</sup></sup>



Secret containing custom SSH keys

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestrepohostsshsecretitemsindex">items</a></b></td>
        <td>[]object</td>
        <td>If unspecified, each key-value pair in the Data field of the referenced Secret will be projected into the volume as a file whose name is the key and content is the value. If specified, the listed keys will be projected into the specified paths, and unlisted keys will not be present. If a key is specified which is not present in the Secret, the volume setup will error unless it is marked optional. Paths must be relative and may not contain the '..' path or start with '..'.</td>
        <td>false</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>Name of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#names TODO: Add other useful fields. apiVersion, kind, uid?</td>
        <td>false</td>
      </tr><tr>
        <td><b>optional</b></td>
        <td>boolean</td>
        <td>Specify whether the Secret or its key must be defined</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repoHost.sshSecret.items[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestrepohostsshsecret)</sup></sup>



Maps a string key to a path within a volume.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>mode</b></td>
        <td>integer</td>
        <td>Optional: mode bits used to set permissions on this file. Must be an octal value between 0000 and 0777 or a decimal value between 0 and 511. YAML accepts both octal and decimal values, JSON requires decimal values for mode bits. If not specified, the volume defaultMode will be used. This might be in conflict with other options that affect the file mode, like fsGroup, and the result can be other mode bits set.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The key to project.</td>
        <td>true</td>
      </tr><tr>
        <td><b>path</b></td>
        <td>string</td>
        <td>The relative path of the file to map the key to. May not be an absolute path. May not contain the path element '..'. May not start with the string '..'.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repos[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrest)</sup></sup>



PGBackRestRepo represents a pgBackRest repository.  Only one of its members may be specified.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestreposindexazure">azure</a></b></td>
        <td>object</td>
        <td>Represents a pgBackRest repository that is created using Azure storage</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestreposindexgcs">gcs</a></b></td>
        <td>object</td>
        <td>Represents a pgBackRest repository that is created using Google Cloud Storage</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestreposindexs3">s3</a></b></td>
        <td>object</td>
        <td>RepoS3 represents a pgBackRest repository that is created using AWS S3 (or S3-compatible) storage</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestreposindexschedules">schedules</a></b></td>
        <td>object</td>
        <td>Defines the schedules for the pgBackRest backups Full, Differential and Incremental backup types are supported: https://pgbackrest.org/user-guide.html#concept/backup</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestreposindexvolume">volume</a></b></td>
        <td>object</td>
        <td>Represents a pgBackRest repository that is created using a PersistentVolumeClaim</td>
        <td>false</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>The name of the the repository</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repos[index].azure
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestreposindex)</sup></sup>



Represents a pgBackRest repository that is created using Azure storage

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>container</b></td>
        <td>string</td>
        <td>The Azure container utilized for the repository</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repos[index].gcs
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestreposindex)</sup></sup>



Represents a pgBackRest repository that is created using Google Cloud Storage

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>bucket</b></td>
        <td>string</td>
        <td>The GCS bucket utilized for the repository</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repos[index].s3
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestreposindex)</sup></sup>



RepoS3 represents a pgBackRest repository that is created using AWS S3 (or S3-compatible) storage

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>bucket</b></td>
        <td>string</td>
        <td>The S3 bucket utilized for the repository</td>
        <td>true</td>
      </tr><tr>
        <td><b>endpoint</b></td>
        <td>string</td>
        <td>A valid endpoint corresponding to the specified region</td>
        <td>true</td>
      </tr><tr>
        <td><b>region</b></td>
        <td>string</td>
        <td>The region corresponding to the S3 bucket</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repos[index].schedules
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestreposindex)</sup></sup>



Defines the schedules for the pgBackRest backups Full, Differential and Incremental backup types are supported: https://pgbackrest.org/user-guide.html#concept/backup

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>differential</b></td>
        <td>string</td>
        <td>Defines the Cron schedule for a differential pgBackRest backup. Follows the standard Cron schedule syntax: https://k8s.io/docs/concepts/workloads/controllers/cron-jobs/#cron-schedule-syntax</td>
        <td>false</td>
      </tr><tr>
        <td><b>full</b></td>
        <td>string</td>
        <td>Defines the Cron schedule for a full pgBackRest backup. Follows the standard Cron schedule syntax: https://k8s.io/docs/concepts/workloads/controllers/cron-jobs/#cron-schedule-syntax</td>
        <td>false</td>
      </tr><tr>
        <td><b>incremental</b></td>
        <td>string</td>
        <td>Defines the Cron schedule for an incremental pgBackRest backup. Follows the standard Cron schedule syntax: https://k8s.io/docs/concepts/workloads/controllers/cron-jobs/#cron-schedule-syntax</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repos[index].volume
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestreposindex)</sup></sup>



Represents a pgBackRest repository that is created using a PersistentVolumeClaim

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestreposindexvolumevolumeclaimspec">volumeClaimSpec</a></b></td>
        <td>object</td>
        <td>Defines a PersistentVolumeClaim spec used to create and/or bind a volume</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repos[index].volume.volumeClaimSpec
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestreposindexvolume)</sup></sup>



Defines a PersistentVolumeClaim spec used to create and/or bind a volume

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>accessModes</b></td>
        <td>[]string</td>
        <td>AccessModes contains the desired access modes the volume should have. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes#access-modes-1</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestreposindexvolumevolumeclaimspecdatasource">dataSource</a></b></td>
        <td>object</td>
        <td>This field can be used to specify either: * An existing VolumeSnapshot object (snapshot.storage.k8s.io/VolumeSnapshot) * An existing PVC (PersistentVolumeClaim) * An existing custom resource that implements data population (Alpha) In order to use custom resource types that implement data population, the AnyVolumeDataSource feature gate must be enabled. If the provisioner or an external controller can support the specified data source, it will create a new volume based on the contents of the specified data source.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestreposindexvolumevolumeclaimspecresources">resources</a></b></td>
        <td>object</td>
        <td>Resources represents the minimum resources the volume should have. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes#resources</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestreposindexvolumevolumeclaimspecselector">selector</a></b></td>
        <td>object</td>
        <td>A label query over volumes to consider for binding.</td>
        <td>false</td>
      </tr><tr>
        <td><b>storageClassName</b></td>
        <td>string</td>
        <td>Name of the StorageClass required by the claim. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes#class-1</td>
        <td>false</td>
      </tr><tr>
        <td><b>volumeMode</b></td>
        <td>string</td>
        <td>volumeMode defines what type of volume is required by the claim. Value of Filesystem is implied when not included in claim spec.</td>
        <td>false</td>
      </tr><tr>
        <td><b>volumeName</b></td>
        <td>string</td>
        <td>VolumeName is the binding reference to the PersistentVolume backing this claim.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repos[index].volume.volumeClaimSpec.dataSource
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestreposindexvolumevolumeclaimspec)</sup></sup>



This field can be used to specify either: * An existing VolumeSnapshot object (snapshot.storage.k8s.io/VolumeSnapshot) * An existing PVC (PersistentVolumeClaim) * An existing custom resource that implements data population (Alpha) In order to use custom resource types that implement data population, the AnyVolumeDataSource feature gate must be enabled. If the provisioner or an external controller can support the specified data source, it will create a new volume based on the contents of the specified data source.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>apiGroup</b></td>
        <td>string</td>
        <td>APIGroup is the group for the resource being referenced. If APIGroup is not specified, the specified Kind must be in the core API group. For any other third-party types, APIGroup is required.</td>
        <td>false</td>
      </tr><tr>
        <td><b>kind</b></td>
        <td>string</td>
        <td>Kind is the type of resource being referenced</td>
        <td>true</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>Name is the name of resource being referenced</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repos[index].volume.volumeClaimSpec.resources
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestreposindexvolumevolumeclaimspec)</sup></sup>



Resources represents the minimum resources the volume should have. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes#resources

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>limits</b></td>
        <td>map[string]int or string</td>
        <td>Limits describes the maximum amount of compute resources allowed. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr><tr>
        <td><b>requests</b></td>
        <td>map[string]int or string</td>
        <td>Requests describes the minimum amount of compute resources required. If Requests is omitted for a container, it defaults to Limits if that is explicitly specified, otherwise to an implementation-defined value. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repos[index].volume.volumeClaimSpec.selector
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestreposindexvolumevolumeclaimspec)</sup></sup>



A label query over volumes to consider for binding.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecarchivepgbackrestreposindexvolumevolumeclaimspecselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.archive.pgbackrest.repos[index].volume.volumeClaimSpec.selector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecarchivepgbackrestreposindexvolumevolumeclaimspecselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index]
<sup><sup>[↩ Parent](#postgresclusterspec)</sup></sup>





<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinity">affinity</a></b></td>
        <td>object</td>
        <td>Scheduling constraints of a Instance pod. Changing this value causes Instance to restart. More info: https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexmetadata">metadata</a></b></td>
        <td>object</td>
        <td>Metadata contains metadata for PostgresCluster resources</td>
        <td>false</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td></td>
        <td>false</td>
      </tr><tr>
        <td><b>replicas</b></td>
        <td>integer</td>
        <td></td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexresources">resources</a></b></td>
        <td>object</td>
        <td>Compute resources of a PostgreSQL container.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexwalvolumeclaimspec">walVolumeClaimSpec</a></b></td>
        <td>object</td>
        <td>Defines a separate PersistentVolumeClaim for PostgreSQL's write-ahead log. More info: https://www.postgresql.org/docs/current/wal.html</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexvolumeclaimspec">volumeClaimSpec</a></b></td>
        <td>object</td>
        <td>Defines a PersistentVolumeClaim for PostgreSQL data. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindex)</sup></sup>



Scheduling constraints of a Instance pod. Changing this value causes Instance to restart. More info: https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitynodeaffinity">nodeAffinity</a></b></td>
        <td>object</td>
        <td>Describes node affinity scheduling rules for the pod.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodaffinity">podAffinity</a></b></td>
        <td>object</td>
        <td>Describes pod affinity scheduling rules (e.g. co-locate this pod in the same node, zone, etc. as some other pod(s)).</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodantiaffinity">podAntiAffinity</a></b></td>
        <td>object</td>
        <td>Describes pod anti-affinity scheduling rules (e.g. avoid putting this pod in the same node, zone, etc. as some other pod(s)).</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.nodeAffinity
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinity)</sup></sup>



Describes node affinity scheduling rules for the pod.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindex">preferredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>The scheduler will prefer to schedule pods to nodes that satisfy the affinity expressions specified by this field, but it may choose a node that violates one or more of the expressions. The node that is most preferred is the one with the greatest sum of weights, i.e. for each node that meets all of the scheduling requirements (resource request, requiredDuringScheduling affinity expressions, etc.), compute a sum by iterating through the elements of this field and adding "weight" to the sum if the node matches the corresponding matchExpressions; the node(s) with the highest sum are the most preferred.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitynodeaffinityrequiredduringschedulingignoredduringexecution">requiredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>object</td>
        <td>If the affinity requirements specified by this field are not met at scheduling time, the pod will not be scheduled onto the node. If the affinity requirements specified by this field cease to be met at some point during pod execution (e.g. due to an update), the system may or may not try to eventually evict the pod from its node.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitynodeaffinity)</sup></sup>



An empty preferred scheduling term matches all objects with implicit weight 0 (i.e. it's a no-op). A null preferred scheduling term matches no objects (i.e. is also a no-op).

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreference">preference</a></b></td>
        <td>object</td>
        <td>A node selector term, associated with the corresponding weight.</td>
        <td>true</td>
      </tr><tr>
        <td><b>weight</b></td>
        <td>integer</td>
        <td>Weight associated with matching the corresponding nodeSelectorTerm, in the range 1-100.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].preference
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindex)</sup></sup>



A node selector term, associated with the corresponding weight.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreferencematchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>A list of node selector requirements by node's labels.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreferencematchfieldsindex">matchFields</a></b></td>
        <td>[]object</td>
        <td>A list of node selector requirements by node's fields.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].preference.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreference)</sup></sup>



A node selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. If the operator is Gt or Lt, the values array must have a single element, which will be interpreted as an integer. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>Represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist. Gt, and Lt.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].preference.matchFields[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitynodeaffinitypreferredduringschedulingignoredduringexecutionindexpreference)</sup></sup>



A node selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. If the operator is Gt or Lt, the values array must have a single element, which will be interpreted as an integer. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>Represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist. Gt, and Lt.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitynodeaffinity)</sup></sup>



If the affinity requirements specified by this field are not met at scheduling time, the pod will not be scheduled onto the node. If the affinity requirements specified by this field cease to be met at some point during pod execution (e.g. due to an update), the system may or may not try to eventually evict the pod from its node.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindex">nodeSelectorTerms</a></b></td>
        <td>[]object</td>
        <td>Required. A list of node selector terms. The terms are ORed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitynodeaffinityrequiredduringschedulingignoredduringexecution)</sup></sup>



A null or empty node selector term matches no objects. The requirements of them are ANDed. The TopologySelectorTerm type implements a subset of the NodeSelectorTerm.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindexmatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>A list of node selector requirements by node's labels.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindexmatchfieldsindex">matchFields</a></b></td>
        <td>[]object</td>
        <td>A list of node selector requirements by node's fields.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[index].matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindex)</sup></sup>



A node selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. If the operator is Gt or Lt, the values array must have a single element, which will be interpreted as an integer. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>Represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist. Gt, and Lt.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[index].matchFields[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitynodeaffinityrequiredduringschedulingignoredduringexecutionnodeselectortermsindex)</sup></sup>



A node selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. If the operator is Gt or Lt, the values array must have a single element, which will be interpreted as an integer. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>The label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>Represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist. Gt, and Lt.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAffinity
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinity)</sup></sup>



Describes pod affinity scheduling rules (e.g. co-locate this pod in the same node, zone, etc. as some other pod(s)).

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindex">preferredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>The scheduler will prefer to schedule pods to nodes that satisfy the affinity expressions specified by this field, but it may choose a node that violates one or more of the expressions. The node that is most preferred is the one with the greatest sum of weights, i.e. for each node that meets all of the scheduling requirements (resource request, requiredDuringScheduling affinity expressions, etc.), compute a sum by iterating through the elements of this field and adding "weight" to the sum if the node has pods which matches the corresponding podAffinityTerm; the node(s) with the highest sum are the most preferred.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodaffinityrequiredduringschedulingignoredduringexecutionindex">requiredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>If the affinity requirements specified by this field are not met at scheduling time, the pod will not be scheduled onto the node. If the affinity requirements specified by this field cease to be met at some point during pod execution (e.g. due to a pod label update), the system may or may not try to eventually evict the pod from its node. When there are multiple elements, the lists of nodes corresponding to each podAffinityTerm are intersected, i.e. all terms must be satisfied.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAffinity.preferredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodaffinity)</sup></sup>



The weights of all of the matched WeightedPodAffinityTerm fields are added per-node to find the most preferred node(s)

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinityterm">podAffinityTerm</a></b></td>
        <td>object</td>
        <td>Required. A pod affinity term, associated with the corresponding weight.</td>
        <td>true</td>
      </tr><tr>
        <td><b>weight</b></td>
        <td>integer</td>
        <td>weight associated with matching the corresponding podAffinityTerm, in the range 1-100.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindex)</sup></sup>



Required. A pod affinity term, associated with the corresponding weight.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselector">labelSelector</a></b></td>
        <td>object</td>
        <td>A label query over a set of resources, in this case pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>namespaces</b></td>
        <td>[]string</td>
        <td>namespaces specifies which namespaces the labelSelector applies to (matches against); null or empty list means "this pod's namespace"</td>
        <td>false</td>
      </tr><tr>
        <td><b>topologyKey</b></td>
        <td>string</td>
        <td>This pod should be co-located (affinity) or not co-located (anti-affinity) with the pods matching the labelSelector in the specified namespaces, where co-located is defined as running on a node whose value of the label with key topologyKey matches that of any node on which any of the selected pods is running. Empty topologyKey is not allowed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm.labelSelector
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinityterm)</sup></sup>



A label query over a set of resources, in this case pods.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm.labelSelector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAffinity.requiredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodaffinity)</sup></sup>



Defines a set of pods (namely those matching the labelSelector relative to the given namespace(s)) that this pod should be co-located (affinity) or not co-located (anti-affinity) with, where co-located is defined as running on a node whose value of the label with key <topologyKey> matches that of any node on which a pod of the set of pods is running

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodaffinityrequiredduringschedulingignoredduringexecutionindexlabelselector">labelSelector</a></b></td>
        <td>object</td>
        <td>A label query over a set of resources, in this case pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>namespaces</b></td>
        <td>[]string</td>
        <td>namespaces specifies which namespaces the labelSelector applies to (matches against); null or empty list means "this pod's namespace"</td>
        <td>false</td>
      </tr><tr>
        <td><b>topologyKey</b></td>
        <td>string</td>
        <td>This pod should be co-located (affinity) or not co-located (anti-affinity) with the pods matching the labelSelector in the specified namespaces, where co-located is defined as running on a node whose value of the label with key topologyKey matches that of any node on which any of the selected pods is running. Empty topologyKey is not allowed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAffinity.requiredDuringSchedulingIgnoredDuringExecution[index].labelSelector
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodaffinityrequiredduringschedulingignoredduringexecutionindex)</sup></sup>



A label query over a set of resources, in this case pods.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodaffinityrequiredduringschedulingignoredduringexecutionindexlabelselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAffinity.requiredDuringSchedulingIgnoredDuringExecution[index].labelSelector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodaffinityrequiredduringschedulingignoredduringexecutionindexlabelselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAntiAffinity
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinity)</sup></sup>



Describes pod anti-affinity scheduling rules (e.g. avoid putting this pod in the same node, zone, etc. as some other pod(s)).

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindex">preferredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>The scheduler will prefer to schedule pods to nodes that satisfy the anti-affinity expressions specified by this field, but it may choose a node that violates one or more of the expressions. The node that is most preferred is the one with the greatest sum of weights, i.e. for each node that meets all of the scheduling requirements (resource request, requiredDuringScheduling anti-affinity expressions, etc.), compute a sum by iterating through the elements of this field and adding "weight" to the sum if the node has pods which matches the corresponding podAffinityTerm; the node(s) with the highest sum are the most preferred.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindex">requiredDuringSchedulingIgnoredDuringExecution</a></b></td>
        <td>[]object</td>
        <td>If the anti-affinity requirements specified by this field are not met at scheduling time, the pod will not be scheduled onto the node. If the anti-affinity requirements specified by this field cease to be met at some point during pod execution (e.g. due to a pod label update), the system may or may not try to eventually evict the pod from its node. When there are multiple elements, the lists of nodes corresponding to each podAffinityTerm are intersected, i.e. all terms must be satisfied.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodantiaffinity)</sup></sup>



The weights of all of the matched WeightedPodAffinityTerm fields are added per-node to find the most preferred node(s)

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinityterm">podAffinityTerm</a></b></td>
        <td>object</td>
        <td>Required. A pod affinity term, associated with the corresponding weight.</td>
        <td>true</td>
      </tr><tr>
        <td><b>weight</b></td>
        <td>integer</td>
        <td>weight associated with matching the corresponding podAffinityTerm, in the range 1-100.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindex)</sup></sup>



Required. A pod affinity term, associated with the corresponding weight.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselector">labelSelector</a></b></td>
        <td>object</td>
        <td>A label query over a set of resources, in this case pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>namespaces</b></td>
        <td>[]string</td>
        <td>namespaces specifies which namespaces the labelSelector applies to (matches against); null or empty list means "this pod's namespace"</td>
        <td>false</td>
      </tr><tr>
        <td><b>topologyKey</b></td>
        <td>string</td>
        <td>This pod should be co-located (affinity) or not co-located (anti-affinity) with the pods matching the labelSelector in the specified namespaces, where co-located is defined as running on a node whose value of the label with key topologyKey matches that of any node on which any of the selected pods is running. Empty topologyKey is not allowed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm.labelSelector
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinityterm)</sup></sup>



A label query over a set of resources, in this case pods.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[index].podAffinityTerm.labelSelector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodantiaffinitypreferredduringschedulingignoredduringexecutionindexpodaffinitytermlabelselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAntiAffinity.requiredDuringSchedulingIgnoredDuringExecution[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodantiaffinity)</sup></sup>



Defines a set of pods (namely those matching the labelSelector relative to the given namespace(s)) that this pod should be co-located (affinity) or not co-located (anti-affinity) with, where co-located is defined as running on a node whose value of the label with key <topologyKey> matches that of any node on which a pod of the set of pods is running

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindexlabelselector">labelSelector</a></b></td>
        <td>object</td>
        <td>A label query over a set of resources, in this case pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>namespaces</b></td>
        <td>[]string</td>
        <td>namespaces specifies which namespaces the labelSelector applies to (matches against); null or empty list means "this pod's namespace"</td>
        <td>false</td>
      </tr><tr>
        <td><b>topologyKey</b></td>
        <td>string</td>
        <td>This pod should be co-located (affinity) or not co-located (anti-affinity) with the pods matching the labelSelector in the specified namespaces, where co-located is defined as running on a node whose value of the label with key topologyKey matches that of any node on which any of the selected pods is running. Empty topologyKey is not allowed.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAntiAffinity.requiredDuringSchedulingIgnoredDuringExecution[index].labelSelector
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindex)</sup></sup>



A label query over a set of resources, in this case pods.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexaffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindexlabelselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].affinity.podAntiAffinity.requiredDuringSchedulingIgnoredDuringExecution[index].labelSelector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexaffinitypodantiaffinityrequiredduringschedulingignoredduringexecutionindexlabelselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].metadata
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindex)</sup></sup>



Metadata contains metadata for PostgresCluster resources

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>annotations</b></td>
        <td>map[string]string</td>
        <td></td>
        <td>false</td>
      </tr><tr>
        <td><b>labels</b></td>
        <td>map[string]string</td>
        <td></td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].resources
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindex)</sup></sup>



Compute resources of a PostgreSQL container.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>limits</b></td>
        <td>map[string]int or string</td>
        <td>Limits describes the maximum amount of compute resources allowed. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr><tr>
        <td><b>requests</b></td>
        <td>map[string]int or string</td>
        <td>Requests describes the minimum amount of compute resources required. If Requests is omitted for a container, it defaults to Limits if that is explicitly specified, otherwise to an implementation-defined value. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].walVolumeClaimSpec
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindex)</sup></sup>



Defines a separate PersistentVolumeClaim for PostgreSQL's write-ahead log. More info: https://www.postgresql.org/docs/current/wal.html

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>accessModes</b></td>
        <td>[]string</td>
        <td>AccessModes contains the desired access modes the volume should have. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes#access-modes-1</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexwalvolumeclaimspecdatasource">dataSource</a></b></td>
        <td>object</td>
        <td>This field can be used to specify either: * An existing VolumeSnapshot object (snapshot.storage.k8s.io/VolumeSnapshot) * An existing PVC (PersistentVolumeClaim) * An existing custom resource that implements data population (Alpha) In order to use custom resource types that implement data population, the AnyVolumeDataSource feature gate must be enabled. If the provisioner or an external controller can support the specified data source, it will create a new volume based on the contents of the specified data source.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexwalvolumeclaimspecresources">resources</a></b></td>
        <td>object</td>
        <td>Resources represents the minimum resources the volume should have. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes#resources</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexwalvolumeclaimspecselector">selector</a></b></td>
        <td>object</td>
        <td>A label query over volumes to consider for binding.</td>
        <td>false</td>
      </tr><tr>
        <td><b>storageClassName</b></td>
        <td>string</td>
        <td>Name of the StorageClass required by the claim. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes#class-1</td>
        <td>false</td>
      </tr><tr>
        <td><b>volumeMode</b></td>
        <td>string</td>
        <td>volumeMode defines what type of volume is required by the claim. Value of Filesystem is implied when not included in claim spec.</td>
        <td>false</td>
      </tr><tr>
        <td><b>volumeName</b></td>
        <td>string</td>
        <td>VolumeName is the binding reference to the PersistentVolume backing this claim.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].walVolumeClaimSpec.dataSource
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexwalvolumeclaimspec)</sup></sup>



This field can be used to specify either: * An existing VolumeSnapshot object (snapshot.storage.k8s.io/VolumeSnapshot) * An existing PVC (PersistentVolumeClaim) * An existing custom resource that implements data population (Alpha) In order to use custom resource types that implement data population, the AnyVolumeDataSource feature gate must be enabled. If the provisioner or an external controller can support the specified data source, it will create a new volume based on the contents of the specified data source.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>apiGroup</b></td>
        <td>string</td>
        <td>APIGroup is the group for the resource being referenced. If APIGroup is not specified, the specified Kind must be in the core API group. For any other third-party types, APIGroup is required.</td>
        <td>false</td>
      </tr><tr>
        <td><b>kind</b></td>
        <td>string</td>
        <td>Kind is the type of resource being referenced</td>
        <td>true</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>Name is the name of resource being referenced</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].walVolumeClaimSpec.resources
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexwalvolumeclaimspec)</sup></sup>



Resources represents the minimum resources the volume should have. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes#resources

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>limits</b></td>
        <td>map[string]int or string</td>
        <td>Limits describes the maximum amount of compute resources allowed. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr><tr>
        <td><b>requests</b></td>
        <td>map[string]int or string</td>
        <td>Requests describes the minimum amount of compute resources required. If Requests is omitted for a container, it defaults to Limits if that is explicitly specified, otherwise to an implementation-defined value. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].walVolumeClaimSpec.selector
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexwalvolumeclaimspec)</sup></sup>



A label query over volumes to consider for binding.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexwalvolumeclaimspecselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].walVolumeClaimSpec.selector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexwalvolumeclaimspecselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].volumeClaimSpec
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindex)</sup></sup>



Defines a PersistentVolumeClaim for PostgreSQL data. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>accessModes</b></td>
        <td>[]string</td>
        <td>AccessModes contains the desired access modes the volume should have. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes#access-modes-1</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexvolumeclaimspecdatasource">dataSource</a></b></td>
        <td>object</td>
        <td>This field can be used to specify either: * An existing VolumeSnapshot object (snapshot.storage.k8s.io/VolumeSnapshot) * An existing PVC (PersistentVolumeClaim) * An existing custom resource that implements data population (Alpha) In order to use custom resource types that implement data population, the AnyVolumeDataSource feature gate must be enabled. If the provisioner or an external controller can support the specified data source, it will create a new volume based on the contents of the specified data source.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexvolumeclaimspecresources">resources</a></b></td>
        <td>object</td>
        <td>Resources represents the minimum resources the volume should have. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes#resources</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterspecinstancesindexvolumeclaimspecselector">selector</a></b></td>
        <td>object</td>
        <td>A label query over volumes to consider for binding.</td>
        <td>false</td>
      </tr><tr>
        <td><b>storageClassName</b></td>
        <td>string</td>
        <td>Name of the StorageClass required by the claim. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes#class-1</td>
        <td>false</td>
      </tr><tr>
        <td><b>volumeMode</b></td>
        <td>string</td>
        <td>volumeMode defines what type of volume is required by the claim. Value of Filesystem is implied when not included in claim spec.</td>
        <td>false</td>
      </tr><tr>
        <td><b>volumeName</b></td>
        <td>string</td>
        <td>VolumeName is the binding reference to the PersistentVolume backing this claim.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].volumeClaimSpec.dataSource
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexvolumeclaimspec)</sup></sup>



This field can be used to specify either: * An existing VolumeSnapshot object (snapshot.storage.k8s.io/VolumeSnapshot) * An existing PVC (PersistentVolumeClaim) * An existing custom resource that implements data population (Alpha) In order to use custom resource types that implement data population, the AnyVolumeDataSource feature gate must be enabled. If the provisioner or an external controller can support the specified data source, it will create a new volume based on the contents of the specified data source.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>apiGroup</b></td>
        <td>string</td>
        <td>APIGroup is the group for the resource being referenced. If APIGroup is not specified, the specified Kind must be in the core API group. For any other third-party types, APIGroup is required.</td>
        <td>false</td>
      </tr><tr>
        <td><b>kind</b></td>
        <td>string</td>
        <td>Kind is the type of resource being referenced</td>
        <td>true</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>Name is the name of resource being referenced</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].volumeClaimSpec.resources
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexvolumeclaimspec)</sup></sup>



Resources represents the minimum resources the volume should have. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes#resources

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>limits</b></td>
        <td>map[string]int or string</td>
        <td>Limits describes the maximum amount of compute resources allowed. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr><tr>
        <td><b>requests</b></td>
        <td>map[string]int or string</td>
        <td>Requests describes the minimum amount of compute resources required. If Requests is omitted for a container, it defaults to Limits if that is explicitly specified, otherwise to an implementation-defined value. More info: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].volumeClaimSpec.selector
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexvolumeclaimspec)</sup></sup>



A label query over volumes to consider for binding.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterspecinstancesindexvolumeclaimspecselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>matchExpressions is a list of label selector requirements. The requirements are ANDed.</td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.spec.instances[index].volumeClaimSpec.selector.matchExpressions[index]
<sup><sup>[↩ Parent](#postgresclusterspecinstancesindexvolumeclaimspecselector)</sup></sup>



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</td>
        <td>false</td>
      </tr><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>key is the label key that the selector applies to.</td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.status
<sup><sup>[↩ Parent](#postgrescluster)</sup></sup>



PostgresClusterStatus defines the observed state of PostgresCluster

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterstatusconditionsindex">conditions</a></b></td>
        <td>[]object</td>
        <td>conditions represent the observations of postgrescluster's current state. Known .status.conditions.type are: "PersistentVolumeResizing", "ProxyAvailable"</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterstatusinstancesindex">instances</a></b></td>
        <td>[]object</td>
        <td>Current state of PostgreSQL instances.</td>
        <td>false</td>
      </tr><tr>
        <td><b>observedGeneration</b></td>
        <td>integer</td>
        <td>observedGeneration represents the .metadata.generation on which the status was based.</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterstatuspatroni">patroni</a></b></td>
        <td>object</td>
        <td></td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterstatuspgbackrest">pgbackrest</a></b></td>
        <td>object</td>
        <td>Status information for pgBackRest</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterstatusproxy">proxy</a></b></td>
        <td>object</td>
        <td>Current state of the PostgreSQL proxy.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.status.conditions[index]
<sup><sup>[↩ Parent](#postgresclusterstatus)</sup></sup>



Condition contains details for one aspect of the current state of this API Resource. --- This struct is intended for direct use as an array at the field path .status.conditions.  For example, type FooStatus struct{     // Represents the observations of a foo's current state.     // Known .status.conditions.type are: "Available", "Progressing", and "Degraded"     // +patchMergeKey=type     // +patchStrategy=merge     // +listType=map     // +listMapKey=type     Conditions []metav1.Condition `json:"conditions,omitempty" patchStrategy:"merge" patchMergeKey:"type" protobuf:"bytes,1,rep,name=conditions"` 
     // other fields }

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>observedGeneration</b></td>
        <td>integer</td>
        <td>observedGeneration represents the .metadata.generation that the condition was set based upon. For instance, if .metadata.generation is currently 12, but the .status.conditions[x].observedGeneration is 9, the condition is out of date with respect to the current state of the instance.</td>
        <td>false</td>
      </tr><tr>
        <td><b>lastTransitionTime</b></td>
        <td>string</td>
        <td>lastTransitionTime is the last time the condition transitioned from one status to another. This should be when the underlying condition changed.  If that is not known, then using the time when the API field changed is acceptable.</td>
        <td>true</td>
      </tr><tr>
        <td><b>message</b></td>
        <td>string</td>
        <td>message is a human readable message indicating details about the transition. This may be an empty string.</td>
        <td>true</td>
      </tr><tr>
        <td><b>reason</b></td>
        <td>string</td>
        <td>reason contains a programmatic identifier indicating the reason for the condition's last transition. Producers of specific condition types may define expected values and meanings for this field, and whether the values are considered a guaranteed API. The value should be a CamelCase string. This field may not be empty.</td>
        <td>true</td>
      </tr><tr>
        <td><b>status</b></td>
        <td>enum</td>
        <td>status of the condition, one of True, False, Unknown. [True False Unknown]</td>
        <td>true</td>
      </tr><tr>
        <td><b>type</b></td>
        <td>string</td>
        <td>type of condition in CamelCase or in foo.example.com/CamelCase. --- Many .condition.type values are consistent across resources like Available, but because arbitrary conditions can be useful (see .node.status.conditions), the ability to deconflict is important. The regex it matches is (dns1123SubdomainFmt/)?(qualifiedNameFmt)</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.status.instances[index]
<sup><sup>[↩ Parent](#postgresclusterstatus)</sup></sup>





<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>readyReplicas</b></td>
        <td>integer</td>
        <td>Total number of ready pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>replicas</b></td>
        <td>integer</td>
        <td>Total number of non-terminated pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>updatedReplicas</b></td>
        <td>integer</td>
        <td>Total number of non-terminated pods that have the desired specification.</td>
        <td>false</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td></td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.status.patroni
<sup><sup>[↩ Parent](#postgresclusterstatus)</sup></sup>





<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>systemIdentifier</b></td>
        <td>string</td>
        <td>The PostgreSQL system identifier reported by Patroni.</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.status.pgbackrest
<sup><sup>[↩ Parent](#postgresclusterstatus)</sup></sup>



Status information for pgBackRest

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterstatuspgbackrestmanualbackup">manualBackup</a></b></td>
        <td>object</td>
        <td>Status information for manual backups</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterstatuspgbackrestrepohost">repoHost</a></b></td>
        <td>object</td>
        <td>Status information for the pgBackRest dedicated repository host</td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#postgresclusterstatuspgbackrestreposindex">repos</a></b></td>
        <td>[]object</td>
        <td>Status information for pgBackRest repositories</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.status.pgbackrest.manualBackup
<sup><sup>[↩ Parent](#postgresclusterstatuspgbackrest)</sup></sup>



Status information for manual backups

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>active</b></td>
        <td>integer</td>
        <td>The number of actively running manual backup Pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>completionTime</b></td>
        <td>string</td>
        <td>Represents the time the manual backup Job was determined by the Job controller to be completed.  This field is only set if the backup completed successfully. Additionally, it is represented in RFC3339 form and is in UTC.</td>
        <td>false</td>
      </tr><tr>
        <td><b>failed</b></td>
        <td>integer</td>
        <td>The number of Pods for the manual backup Job that reached the "Failed" phase.</td>
        <td>false</td>
      </tr><tr>
        <td><b>startTime</b></td>
        <td>string</td>
        <td>Represents the time the manual backup Job was acknowledged by the Job controller. It is represented in RFC3339 form and is in UTC.</td>
        <td>false</td>
      </tr><tr>
        <td><b>succeeded</b></td>
        <td>integer</td>
        <td>The number of Pods for the manual backup Job that reached the "Succeeded" phase.</td>
        <td>false</td>
      </tr><tr>
        <td><b>finished</b></td>
        <td>boolean</td>
        <td>Specifies whether or not the Job is finished executing (does not indicate success or failure).</td>
        <td>true</td>
      </tr><tr>
        <td><b>id</b></td>
        <td>string</td>
        <td>A unique identifier for the manual backup as provided using the "pgbackrest-backup" annotation when initiating a backup.</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.status.pgbackrest.repoHost
<sup><sup>[↩ Parent](#postgresclusterstatuspgbackrest)</sup></sup>



Status information for the pgBackRest dedicated repository host

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>apiVersion</b></td>
        <td>string</td>
        <td>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#resources</td>
        <td>false</td>
      </tr><tr>
        <td><b>kind</b></td>
        <td>string</td>
        <td>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#types-kinds</td>
        <td>false</td>
      </tr><tr>
        <td><b>ready</b></td>
        <td>boolean</td>
        <td>Whether or not the pgBackRest repository host is ready for use</td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.status.pgbackrest.repos[index]
<sup><sup>[↩ Parent](#postgresclusterstatuspgbackrest)</sup></sup>



RepoVolumeStatus the status of a pgBackRest repository

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>bound</b></td>
        <td>boolean</td>
        <td>Whether or not the pgBackRest repository PersistentVolumeClaim is bound to a volume</td>
        <td>false</td>
      </tr><tr>
        <td><b>replicaCreateBackupComplete</b></td>
        <td>boolean</td>
        <td>ReplicaCreateBackupReady indicates whether a backup exists in the repository as needed to bootstrap replicas.</td>
        <td>false</td>
      </tr><tr>
        <td><b>repoOptionsHash</b></td>
        <td>string</td>
        <td>A hash of the required fields in the spec for defining an Azure, GCS or S3 repository, Utilizd to detect changes to these fields and then execute pgBackRest stanza-create commands accordingly.</td>
        <td>false</td>
      </tr><tr>
        <td><b>stanzaCreated</b></td>
        <td>boolean</td>
        <td>Specifies whether or not a stanza has been successfully created for the repository</td>
        <td>false</td>
      </tr><tr>
        <td><b>volume</b></td>
        <td>string</td>
        <td>The name of the volume the containing the pgBackRest repository</td>
        <td>false</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>The name of the pgBackRest repository</td>
        <td>true</td>
      </tr></tbody>
</table>


### PostgresCluster.status.proxy
<sup><sup>[↩ Parent](#postgresclusterstatus)</sup></sup>



Current state of the PostgreSQL proxy.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#postgresclusterstatusproxypgbouncer">pgBouncer</a></b></td>
        <td>object</td>
        <td></td>
        <td>false</td>
      </tr></tbody>
</table>


### PostgresCluster.status.proxy.pgBouncer
<sup><sup>[↩ Parent](#postgresclusterstatusproxy)</sup></sup>





<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>postgresRevision</b></td>
        <td>string</td>
        <td>Identifies the revision of PgBouncer assets that have been installed into PostgreSQL.</td>
        <td>false</td>
      </tr><tr>
        <td><b>readyReplicas</b></td>
        <td>integer</td>
        <td>Total number of ready pods.</td>
        <td>false</td>
      </tr><tr>
        <td><b>replicas</b></td>
        <td>integer</td>
        <td>Total number of non-terminated pods.</td>
        <td>false</td>
      </tr></tbody>
</table>