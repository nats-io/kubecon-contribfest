# KubeCon Contribfest 2023

Let's work on the NATS Go client!

## Slides

<img width="675" alt="image" src="https://user-images.githubusercontent.com/26195/233014806-17739e8c-d3c0-4660-8be0-82ca268baa0f.png">

https://docs.google.com/presentation/d/1SSCq53PMCd65pKsx3TZcAi19Huz0PGmdY4GuMex2ppc/edit?usp=sharing

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

## Slack 

Join the NATS community Slack channel! https://nats.io/community/
There you can find a `#kubecon-contribfest` channel for this session.
