# Step Issuer

⚙️  A certificate issuer for cert-manager using step certificates CA.

To learn more, visit <https://github.com/smallstep/step-issuer>.

## TL;DR

```console
helm install step-issuer step-issuer
```

## Prerequisites

- Kubernetes 1.10+

## Installing the Chart

To install the chart with the release name `step-issuer`:

```console
helm install step-issuer step-issuer
```

The command deploys step-issuer on the Kubernetes cluster with the default configuration.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `step-issuer` deployment:

```console
helm uninstall step-issuer
```

The command removes all the Kubernetes components associated with the chart and
deletes the release.

## Configuration

The following table lists the configurable parameters of the Step Issuer chart
and their default values.

| Parameter                                 | Description                                                              | Default                             |
| ----------------------------------------- | ------------------------------------------------------------------------ | ----------------------------------- |
| `replicaCount`                            | Number of Step Issuer replicas.                                          | `1`                                 |
| `image.repository`                        | Repository of the Step Issuer image.                                     | `cr.step.sm/smallstep/step-issuer`  |
| `image.tag`                               | Tag of the image. If empty it will use .Chart.appVersion.                | `""`                                |
| `image.pullPolicy`                        | Step Issuer image pull policy                                            | `IfNotPresent`                      |
| `deployment.args.enableLeaderElection`    | Enable k8s controller leader election.                                   | `true`                              |
| `deployment.args.disableApprovalCheck`    | To disable cert-manager approvals on old version of cert-manager.        | `false`                             |
| `stepIssuer.create`                       | If we should automatically create an step-issuer.                        | `false`                             |
| `stepIssuer.caBundle`                     | Step Certificates root certificate in a single-line base64 string.       | `""`                                |
| `stepIssuer.provisioner.name`             | Name of the provisioner used for authorizing the sign of certificates.   | `""`                                |
| `stepIssuer.provisioner.kid`              | Key id of the provisioner used for authorizing the sign of certificates. | `""`                                |
| `stepIssuer.provisioner.passwordRef.name` | Name of the secret with the provisioner password.                        | `""`                                |
| `stepIssuer.provisioner.passwordRef.key`  | Key name in the the secret with the provisioner password.                | `""`                                |
