# sassy-webR

Browser demo for [`Rsassy`](https://sounkou-bioinfo.r-universe.dev/Rsassy), the R bindings to [`sassy`](https://github.com/RagnarGrootKoerkamp/sassy).

The page runs fully in the browser with [webR](https://docs.r-wasm.org/webr/latest/):

1. starts a webR runtime,
2. installs the WebAssembly build of `Rsassy` from r-universe,
3. runs `sassy_search()` on user-provided pattern/text strings, with optional `match_region` output in the result table.
4. supports a CRISPR mode using `sassy_crispr()` with guide/text input,
5. shows `sassy_features()` so the wasm SIMD build can be inspected.

For both modes, input rows are sent as character vectors in R lists (required by the current `Rsassy` API). In CRISPR mode, guide sequences should include a common PAM suffix.

## Local test

```sh
python3 -m http.server 8000
```

Then open <http://127.0.0.1:8000>.

## Deployment

GitHub Pages is deployed by `.github/workflows/pages.yml`.
