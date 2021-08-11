# ray-wheels

Non-standard wheels for [ray-project/ray](https://github.com/ray-project/ray).

## Modus Operandi

1.  Pick Ray version (say, `M.m.p`)
    - the latest Ray version (`1.5.1` at the time of writing) is used by default
1.  [OPTIONAL] Add patches, if any, under `patches/M.m.p`
1.  Build the wheel (the resulting wheel, if produced, ends up under `wheels`)
    - latest
      ```sh
      ./build-wheel
      ```
    - Ray `M.m.p`
      ```sh
      ./build-wheel M.m.p
      ```
    - Ray `M.m.p` on Python `MM.mm`
      ```sh
      ./build-wheel M.m.p MM.mm
      ```
      * Passing an explicit Python version (e.g. `MM.mm`) is OPTIONAL
      * Python 3.8 is used by default
1.  [OPTIONAL] Update the barebones PyPi repo under `wheels`
    ```sh
    dir2pi -S wheels
    ```
    - This requires the `pip2i` package (installed as `pip install pip2pi`)
1.  [OPTIONAL] file a [Pull Request](https://github.com/mehes-kth/ray-wheels/pulls)


To use a non-standard wheel from this repo, but fall back to PyPi on platforms
where standard wheels are available, set `--extra-index-url` or `PIP_EXTRA_INDEX_URL`
to `https://mehes-kth.github.io/ray-wheels`.
