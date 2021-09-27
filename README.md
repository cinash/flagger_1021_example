# flagger_1021_example

In order to reproduce the issue perform the following
1. install flagger & istio 
1. create flagger-test namespace and enable istio injection for it
1. deploy files from this repo to `flagger-test` namespace
1. upgrade deployment by for example changing image to `subfuzion/netcat`
1. if you describe the canary you will see an error:
```
reconcileVirtualService failed: VirtualService flagger-test.flagger-test get query error v1alpha3.VirtualService.Spec: v1alpha3.VirtualServiceSpec.Tcp: []v1alpha3.TCPRoute: v1alpha3.TCPRoute.Route: readObjectStart: expect { or n, but found [, error found in #10 byte of ...|,"route":[{"destinat|..., bigger context ...|"sourceLabels":{"version":"version-x"}}],"route":[{"destination":{"host":"flagger-test"}}]}]}}            |...
```
