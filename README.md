# 蛋白质宇宙 · The protein universe

The AFDB90v4 sequence-similarity network of Durairaj et al. (Nature 2023): 4.27 million UniRef50 clusters with confident AlphaFold structures, grouped into communities as the authors laid them out; six deep-zoom layers (annotation coverage, kingdom, lineage, protein length, unusual shape, sequenced relatives), the largest named communities labelled, and a narrated tour. Find a protein family or a UniProt id in the search box.

Live: https://youdata.github.io/protein-universe/

The image pyramids are tile folders (`protein-coverage/`, `protein-kingdom/`, `protein-length/`, `protein-lineage/`, `protein-novelty/`, `protein-relatives/`: `header.idx` + `{z}/{x}/{y}.png`), so any static host serves them. Its fonts are in `fonts/`, trimmed to the page's characters. The narrated video is not included.

Data: Durairaj J, Waterhouse AM, et al. Uncovering new families and folds in the natural protein universe. Nature 622, 646–653 (2023), doi:10.1038/s41586-023-06622-3; the AFDB90v4 network metadata and layout, Zenodo doi:10.5281/zenodo.8121336 (CC BY 4.0). Names: each community's median representative in UniProt.

## How it is made

From `infographic-examples/protein-universe/build.mjs`, with rx (`~/rx-cli`):

```sh
rx export protein-universe.json --out site --app /rx-graphic-editor/web/index.html --canvas --theme dark --lock-layers --tiles dir --plugin …/viewsPlugin.js --plugin …/placeSearchPlugin.js
rx publish site --to github:youdata/protein-universe --yes
```
