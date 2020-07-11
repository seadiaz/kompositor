# Kompositor
Create external component as DB, Message Brokers or Observabilities tools out of you apps platform to not suffer performance issues

## Some definitions
* Kompositor shuold be agnostic to CI/CD tools, supporting several ones.
* Kompositor will think big, but will begin focused, so we are going to pick one single toolset/process and after a first MVP we could add more variation depend upon customer feedback.

## Komponent 
- The komponent is an independent service where the application depend upon.
- The komponent have the responsibility to spin up the infrastructure and also every layer on top, like could be in Kubernetes or bare VMS
- It has dynamic names
- It's a Kubernetes operator based on fluxcd, drone, vault, ansible, terraform, rke y helm
- If the komponent have some internet facing artifact, it has to provided all the configuration to expose including tls, load balancer or ingress.
- The komponent works in a declarative fashion
- Every komponent have to comply certain interface, considering status, tls certificate, dns, observability.
- The komponent don’t have public access necesarily, so we encourage push healthy to minimize security surface
- The komponent is a Kubernetes CRD
- The komponent come from a kemplate, stored in a git repository and using tags a version control system. The komponent is an Instance of the Template
- The komponent is created based on some kemplate. Before a kemplate, after a komponent.

## Kemplate
* The kemplate define the very simple modules, which are as generic as posible and not coupled to any specific usage
* The kemplate is a very basic functional building block, so I could spin up a plain template and should works.
* The kemplate must be versioned to not break running komponents
* The kemplate must use git tags as versioning mechanism
