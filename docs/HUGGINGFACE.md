# Hugging Face dataset

DestBench is hosted at **[tag-nav-authors/DestBench](https://huggingface.co/datasets/tag-nav-authors/DestBench)**.

The showcase site **always** loads screenshots from Hugging Face. Task metadata is in `public/data/manifest.json`, built from the same repo.

## Refresh manifest from the Hub

```bash
python scripts/build_manifest.py
# Uses HF_DATASET=tag-nav-authors/DestBench by default
```

## Upload or update files on the Hub

```bash
pip install -U huggingface_hub
huggingface-cli login

export HF_DATASET=tag-nav-authors/DestBench
export AGENT_NAV_DATA=/path/to/local/DATA   # only needed for uploads

bash scripts/upload_huggingface.sh
python scripts/build_manifest.py
```

## Website configuration

`public/index.html`:

```html
<meta name="hf-dataset" content="tag-nav-authors/DestBench" />
<meta name="hf-revision" content="main" />
```

Image URLs:

`https://huggingface.co/datasets/tag-nav-authors/DestBench/resolve/main/<app_dir>/<task>/frame_....png`
