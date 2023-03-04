# Serving ML Models
```sh
# Some useful commands
kind create cluster --image=kindest/node:v1.23.0
helm install kuberay-operator kuberay/kuberay-operator --version 0.4.0
kubectl apply -f raycluster/raycluster.yaml
kubectl port-forward --address 0.0.0.0 svc/raycluster-head-svc 8265:8265
kubectl cp scripts/ default/$HEAD_POD:/home/ray

# Serve CLI
serve shutdown

# PyTorch example
serve run tutorial_pytorch:image_model
python3 tutorial_pytorch_req.py
```