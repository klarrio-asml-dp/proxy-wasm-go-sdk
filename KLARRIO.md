Change directory to one of the filter and execute:
```bash
tinygo build -o ./main.go.wasm -scheduler=none -target=wasi
```

Create a K8s ConfigMap using the wasm file created in previous step:

```bash
kubectl create configmap network-filter --from-file=network-filter.wasm=main.go.wasm
```

Apply the associated EnvoyFilter in the flux-system repo