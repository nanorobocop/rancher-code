# Rancher Wrangler: Kubernetes Controllers Framework

This review is based on version [rancher/wrangler v0.8.5](https://github.com/rancher/wrangler/releases/tag/v0.8.5),
released on Aug 5, 2021.

## Wrangler vs Norman

From [comment](https://github.com/rancher/wrangler/issues/82#issuecomment-683239992):

> Norman and Wrangler are basically competing frameworks with Norman being deprecated

Wrangler itself is heavily [based on Norman](https://github.com/rancher/wrangler/commit/a6b17de10a0ab5d0e8ec22709444a091878a80b6).

First usage of Wrangler in Rancher is from [Feb 1, 2020](https://github.com/rancher/rancher/pull/25195)
But Rancher still users Norman in many places.

## Questions

Why change?

What problem with Norman?

Why Wrangler is better?

What's the difference between Norman and Wrangler?

Is Norman abandoned?

Is migration from Norman to Wrangler completed?

How rancher/steve related?

How rancher/lasso related?

## Wrangler packages

- apply
  - Initializes Apply interface for controller.
  - Allows to set multiple parameters (id, owner, ratelimit, reconciler etc).
  - Contains logic for default reconcilers (deployment, service etc).
- broadcast
- cleanup
- clients
- codegen
- condition
- controller-gen
- crd
- data
- generated
- generic
  - Factory
  -
- genericcondition
- git
- gvk
- k8scheck
- kstatus
- kubeconfig
- kv
- leader
- merr
- name
- needacert
- objectset
  - Defines ObjectSet structure, which is basically a set of runtime.Object's
- patch
- randomtoken
- ratelimit
- relatedresource
- resolvehome
- schemas
- schemes
- seen
- signals
  - Interceptor for signals.
  - Propagates context, which is canceled when SIGINT/SIGTERM signals caught.
  - Exits with non-zero code on second signal.
  - You should use signals package at the very beginning of your app.
  - Example: [https://github.com/rancher/wrangler-sample/blob/master/main.go#L31-L32](https://github.com/rancher/wrangler-sample/blob/master/main.go#L31-L32)
- slice
- start
  - Syncs an and Starts desired list of controllers.
  - Example: [https://github.com/rancher/wrangler-sample/blob/master/main.go#L56-L58](https://github.com/rancher/wrangler-sample/blob/master/main.go#L56-L58)
- summary
- ticker
- trigger
- unstructured
- webhook
- yaml

## Links

- [https://github.com/rancher/wrangler](https://github.com/rancher/wrangler)
- [https://github.com/rancher/wrangler-sample](https://github.com/rancher/wrangler-sample/blob/master/main.go)
- [Change go-skel from norman to wrangler](https://github.com/rancher/go-skel/commit/74ff6c7910c4de5e0cfe10727061dcc0a581cea6)
