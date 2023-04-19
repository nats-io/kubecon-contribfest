# KubeCon Contribfest 2023

Let's work on the NATS Go client!

## Getting started 

First, you will need to clone the NATS go repository:

```sh
git clone https://github.com/nats-io/nats.go
```

There we have setup two different branches to the nats.go repository (`kc-contrib-vnext` and `kc-contrib-main`)

- kc-contrib-vnext

  Send PRs to the ideas with backwards incompatible changes here.

- kc-contrib-main

  In this branch, we will try to upstream the changes to the main branch 
  
Then, look for one of the issues [here](https://github.com/nats-io/kubecon-contribfest/issues) and send a PR to the branch that matches the label from the issue.

## Running the tests

To run the tests from the client can be done as follows:

```sh
go test ./... -race --count=1 -p=1 -modfile=go_test.mod
```

Notice the `-modfile=go_test.mod`, we do this to be able to split test dependencies notably the NATS Server.
This way we avoid the client depending on the server (which itself depends on the nats.go client 🌀.
