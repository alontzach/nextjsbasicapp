# nextapp chart

This is the nextapp helm chart

### Updating the chart

```bash
helm package ./nextapp
helm gcs push nextapp-[version].tgz  mona-helm-charts (add --force if you don't want to change the chart's version)
```

### Deployment

Automatic

```bash
ansible-playbook kubernetes-services.yml \
    -e "hosts=[YOUR-CLUSTER] service_name=nextapp"
```

Manual

```bash
helm upgrade nextapp --install mona-helm-charts/nextapp \
    --namespace default \
    -f /tmp/values-nextapp.yml
```

### removal

```bash
 helm delete --purge nextapp
```
