2025-05-31 11:45

Tags: [[nixOS]] 

------------------------------------------------
#### Overview:

A nixOS feature that takes a bunch of inputs and locks them into a certain version, enabling the same version to run on any NixOS PC, no matter which system version it has.

Normally takes a nixpkgs input (with a declared version) and outputs e.g. a shell with the chosen packages at the declared version. This makes it possible to share this flake (usually a directory) with another system that will then be able to identically reproduce the output, no matter the system configuration or version.

#### Example:

`{`
	`description = "basic flake for demo purposes"

	  inputs = {
	    nixpkgs.url = "github:nixos/nixpkgs-23.11";
	  };
	
	  outputs = { self, nixpkgs }:
	   let
		system = "x86-64-linux"
		pkgs = nixpkgs.legacyPackages.${system};
	  in 
		{
			packages = {
				"${system}" = {
					hello = pkgs.hello;
				}
			}	
			
			defaultPackage.${system} = self.packages.${system}.hello;
			
			devShells = {
				"${system}" = {
					hello = pkgs.mkShell {
						buildInputs = [
							pkgs.hello
							pkgs.cowsay
						]
					}
				}
					
			devShell = self.devShells.${system}.hello;
		  
		  }
	}
`}

##### Executing the output:
(in the directory where the flake.nix is located)

`nix build
-> Builds the "defaultPackage" option

`nix build .#hello
-> Builds the "hello" option

`nix develop
-> Creates the "devShell" option and opens a shell with the added specified package(s) (here it just opens the devShells.hello option as a shell)

`nix develop .#hello
-> Creates the "hello" option and opens the specified shell (specified in mkShell in this case)

##### Additional Commands:
| Command                                 | Effect                                                                                              |
| --------------------------------------- | --------------------------------------------------------------------------------------------------- |
| `nix flake lock`                        | Creates missing lock entries for _newly added_ inputs in `flake.nix`; does not touch existing ones. |
| `nix flake lock --update-input <input>` | Updates (bumps) **just** that one input in `flake.lock`, leaves others alone.                       |
| `nix flake lock --recreate-lock-file`   | Re-resolves _all_ inputs from `flake.nix` and rewrites `flake.lock` (same as `update`). (           |
| `nix flake update`                      | Fetches the latest revision of _all_ inputs and overwrites `flake.lock`.                            |
| `nix flake update <input>`              | Fetches the latest revision of _just_ `<input>` and overwrites only that entry in `flake.lock`.     |
##### For new flakes:

executing `nix flake lock

- Without a branch (`github:nixos/nixpkgs`):  
    You float on “unstable,” and `nix flake lock` freezes in whatever the latest commit on the `master`/`trunk` branch is at lock time.
    
- With a branch (`github:nixos/nixpkgs/nixos-23.11`):  
    You pin explicitly to the 23.11 branch, and `nix flake lock` freezes in whatever the latest commit on that branch is at lock time.


------------------------------------------------------
### References

ChatGPT Feedback: https://chatgpt.com/c/683ada31-f508-8005-ba60-ed34249452b4
Nix Manual: https://nix.dev/manual/nix/2.28/command-ref/new-cli/nix3-flake.html#flake-inputs
Nix Wiki: https://nixos.wiki/wiki/Flakes
Vimjoyer: https://www.youtube.com/watch?v=S3VBi6kHw5c