# GitOps Operations Guide

## Daily Operations

### Check Application Status
```bash
kubectl get applications -n argocd
argocd app list
```

### Manual Sync (if needed)
```bash
argocd app sync APP_NAME
```

### View Sync History
```bash
argocd app history APP_NAME
```

## Troubleshooting

### App Out of Sync
1. Check ArgoCD UI for diff
2. Review Git commits
3. Check ArgoCD logs: `kubectl logs -n argocd deployment/argocd-application-controller`

### Sync Fails
1. Check resource errors in UI
2. Review Kubernetes events
3. Validate YAML syntax
4. Check RBAC permissions

## Best Practices

- Always use PRs for production changes
- Test in dev environment first
- Monitor sync status regularly
- Use webhooks for instant sync
- Enable notifications (Slack, etc.)
- Backup ArgoCD configuration
