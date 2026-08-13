## 1. Build the Zensical image

```powershell
docker build -t zensical-site -f docker/Dockerfile.zensical .
```

## 2. Build static site with Zensical

```powershell
docker run --rm -it \
  -v ${PWD}:/site \
  zensical-site build
```

Static HTML goes into `site/` (next to `zensical.toml`).

### 2.1 (optional) Run Zensical dev server

```powershell
docker run --rm -it \
  -p 8000:8000 \
  -v ${PWD}:/site \
  zensical-site
```

Open: [http://localhost:8000](http://localhost:8000) → Zensical-powered site, shared `docs/`.
