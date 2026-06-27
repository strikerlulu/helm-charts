# Homepage

A modern (fully static, fast), secure (fully proxied), highly customizable application dashboard with integrations for more than 25 services and translations for over 15 languages. Easily configured via YAML files (or discovery via docker labels).

[Homepage](https://github.com/gethomepage/homepage)

## TL;DR

```bash
helm repo add strikerlulu https://strikerlulu.github.io/helm-charts
helm install my-release strikerlulu/homepage
```

## References

- App-template introduction: https://bjw-s-labs.github.io/helm-charts/docs/app-template/introduction/
- App-template values explorer: https://bjw-s-labs.github.io/helm-charts/docs/app-template/reference/explorer/

## DNS Notes

Primary v5 style:

```yaml
defaultPodOptions:
  dnsPolicy: ClusterFirst
  dnsConfig:
    nameservers:
      - 8.8.8.8
      - 8.8.4.4
    options:
      - name: ndots
        value: "1"
```

Legacy compatibility (also supported):

```yaml
dnsPolicy: ClusterFirst
dnsConfig:
  nameservers:
    - 8.8.8.8
    - 8.8.4.4
  options:
    - name: ndots
      value: "1"
```
