# esspec-memo

My personal notes about esspec (built with Emanote)

## dev

### VSCode integration

See: [`.vscode`](.vscode)

### cmd

To start the Emanote live server using Nix:

```sh
# For VSCode, this is executed automatically by the live server task.
nix run
```

To update Emanote version in flake.nix:

```sh
nix flake lock --update-input emanote
```
