2025-06-28 15:51

Tags: [[nixos]] [[computer science]]

------------------------------------------------
### Overview:

You can do it the "non-nix"-way by using a shell.nix and setting the library paths manually for each needed C/C++ lib or you can do it the full-nix-way by using either the python packages in nixpkgs or by wrapping them yourself if they arent available.

For wrapping them, theres a tool called pip2nix that you can use, for example:
`nix run github:nix-community/pip2nix -- generate -r ./requirements.txt`
this will generate a `python-packages.nix` which you then implement like this:

(in the shell.nix)

`{ pkgs ? import <nixpkgs> {} }:`

`let` 
   `packageOverrides = pkgs.callPackage ./python-packages.nix {};`
   `python = pkgs.python3.override { inherit packageOverrides; };`
`in`
`pkgs.mkShell {`

   `packages = with pkgs; [`
     `(python.withPackages(p: with p`
     `[`
        `## all packages from requirements.txt`
     `]`
     `))`
   `];`
`}`

### Alternative: 

the `devenv` package can make this easier. Invoking `devenv init`
will generate a `devenv.nix` file that will then have to be configured like this: 

`#devenv.nix`
`{ pkgs, config, ...}:`
`{`
   `languages.python = {`
     `enable = true;`
     `venv.enable = true;`
     `venv.requirements = ''`
        `# the contents of requirements.txt`
     `'';`
	`};`
`}`

if you then run `devenv shell`, it will be all up and working

------------------------------------------------------
### References
https://www.youtube.com/watch?v=6fftiTJ2vuQ