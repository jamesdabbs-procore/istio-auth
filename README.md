An example of using an external OIDC provider to secure access to a service without requiring code changes to the underlying service.

## Running the Example

You will need a kubernetes cluster with istio installed. See e.g. https://istio.io/latest/docs/setup/platform-setup/minikube/. Tested with istio 1.7; earlier versions will require modifications.

    $ cp templates/config.example templates/config.yaml
    # Update required values in templates/config.yaml to match your OIDC provider
    $ kubectl apply -f templates

If using `minikube`, you should be able to start a `minikube tunnel -c` and then visit [lvh.me](http://lvh.me).

For simplicity, this example does not set up TLS, but _absolutely should_ in production configurations.

## What's Going on Here?

This is a lightly modified version of the setup from [this blog post](https://blog.jetstack.io/blog/istio-oidc/).

## TODO

* Visualization of traffic flow using Kiali
