```nix
{
  inputs = {
    # ...
    flatpaks.url = "github:GermanBread/declarative-flatpak/stable";
    # ...
  };

  outputs = { ..., flatpaks, ... }: {
    homeConfigurations.<user> = nixpkgs.lib.nixosSystem {
      # ...
      modules = [
        # ...
        flatpaks.homeManagerModules.default
        # ...
        ./home.nix
        # ...
      ];
      # ...
    };
  };
}
```