# ray-wheels

Non-standard wheels for [ray-project/ray](https://github.com/ray-project/ray).

## Modus Operandi

1.  Pick Ray version (say, `R.r.i`)
    - the latest Ray version (`1.6.0` at the time last checked)  is used by default
1.  [OPTIONAL] Add patches, if any, under `patches/R.r.i`
1.  Build the wheel (the resulting wheel, if produced, ends up in the current directory)
    - latest
      ```sh
      ./build-wheel
      ```
    - Ray `R.r.i`
      ```sh
      ./build-wheel R.r.i
      ```
    - Ray `R.r.i` on Python `P.p`
      ```sh
      ./build-wheel R.r.i P.p
      ```
      * Passing an explicit Python version (e.g. `P.p`) is OPTIONAL
      * Python 3.8 is used by default
1.  Update the `gh-pages` branch (a simple repo hosted on GitHub Pages)
    ```sh
    ./updates-pages
    ```
1.  [OPTIONAL] File a [Pull Request](https://github.com/mehes-kth/ray-wheels/pulls) for `gh-pages`


To use a non-standard wheel from this repo, but fall back to PyPi on platforms
where standard wheels are available, set `--extra-index-url` or `PIP_EXTRA_INDEX_URL`
to [`https://mehes-kth.github.io/ray-wheels/simple`](https://mehes-kth.github.io/ray-wheels/simple).
