# nttinfra

## Physical Infra

Expecting to coexist with EZQS infra for now. *For example* - you wont find the
certificate issuers here because they live in the ezqs chart (if at all).


## Helm

Testing:

```helm upgrade --dry-run --debug --install -f nttchart/values.yaml -f nttchart/values-dev.yaml ntt-infra nttchart```

Rollback:

```helm list```

```helm rollback ntt-infra```

Uninstall:

*BE REALLY CAREFUL THIS WILL BLOW AWAY PROD CERTS* and then letsencrypt wont issue you any more for another week.

```helm uninstall ntt-infra```

## Microk8s

Config generated using `microk8s config  | sed "s/192.168.1.2:16443/ntt.steakholdermeating.com:47826/g" | base64 -w0`.