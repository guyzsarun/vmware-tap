# vmware-tap

### Installation scripts for installing Tanzu Application Platform locally

1. Create developer credentials and namespace
```sh
# Update values in ./scripts/create-dev-ns.sh
./scripts/create-dev-ns.sh
```

2. Install Profile
```sh
tanzu package install tap -p tap.tanzu.vmware.com -v 1.1.0 --values-file profile-full.yaml -n tap-install

or

tanzu package installed update tap -p tap.tanzu.vmware.com -v 1.1.0  --values-file profile-full.yaml  -n tap-install
```

3. Create Scanning and Testing Pipeline
```sh
kubectl apply -f testing-scanning.yaml -n $DEV_NAMESPACE
```

4. Create Github Credentials for Private Repository
```sh
kubectl apply -f github-credentials.yaml -n $DEV_NAMESPACE
```

---

Example Python FastAPI Accelerator available at this [repo](https://github.com/guyzsarun/python-fastapi-accelerator)

