Please note: This component is **unmaintained and out-of-date**.

If the component fails to meet the [contrib requirements](https://github.com/kubeflow/manifests/blob/master/proposals/20220926-contrib-component-guidelines.md#component-requirements)
 by the next Kubeflow release ([1.7](https://github.com/kubeflow/community/tree/master/releases/release-1.7#timeline)),
 it will be removed from the [`manifest`](https://github.com/kubeflow/manifests) repository.

Updates to the `/contrib` components can be found in the [tracking issue](https://github.com/kubeflow/manifests/issues/2311).


# Feast Kustomize

## Installing with Kustomize

### Standalone

```
kustomize build feast/base | kubectl apply -n feast -f -
```

### With Kubeflow

If installing Feast as a component of Kubeflow, use the `kubeflow` overlay.

```
kustomize build feast/overlays/kubeflow | kubectl apply -f -
```

## Updating

The Feast Kustomize configuration in this folder is built from the Feast Helm charts and a custom `values.yaml` file.

Run the following command to regenerate the configuration:
```
make feast/base
```
