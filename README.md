# Production vLLM Serving Stack on Kubernetes

Kubernetes manifests for an OpenAI-compatible vLLM endpoint with GPU scheduling, readiness probes, Prometheus scraping, and a model-aware routing placeholder.

## Deploy

```bash
kubectl apply -f manifests.yaml
kubectl -n llm-serving port-forward svc/vllm 8000:8000
curl http://localhost:8000/v1/models
```

Set `MODEL_NAME` to a model that your cluster nodes can access and ensure NVIDIA device plugins and GPU-capable nodes are available. The manifest is intentionally deployable only after you provide model access/authentication.
