# esspec-memo

wip

## dev

### VSCode integration

When opened in VSCode, the live server task will start automatically. (Nix required)

Details: [`.vscode`](.vscode)

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

To build the static website via Nix:

```sh
nix build -o ./result
# Then test it:
nix run nixpkgs#nodePackages.live-server -- ./result
```
