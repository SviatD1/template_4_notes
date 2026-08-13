3. Generate the PDF via MkDocs

## 1. Build the MkDocs+PDF image

```powershell
docker build -t mkdocs-material-pdf -f docker/Dockerfile.mkdocs-pdf .
```

## 2. Generate the PDF via MkDocs

When you want a **PDF**:

```powershell
docker run --rm -it `
  -v ${PWD}:/docs `
  -e ENABLE_PDF_EXPORT=1 `
  mkdocs-material-pdf build
```

This will:

* Build site into `site/`
* Generate a PDF at: `site/pdf/documentation.pdf`

### 2.1 (optional) Use MkDocs for web preview

```powershell
docker run --rm -it `
  -p 8001:8000 `
  -v ${PWD}:/docs `
  mkdocs-material-pdf mkdocs serve -a 0.0.0.0:8000
```

Open: [http://localhost:8001](http://localhost:8001) → MkDocs Material site (same `docs/` content).


