# Shadow Control Builder

Public build, release, and deployment automation for the private
`fireunix-app/shadow-control` and `fireunix-app/shadow-web` repositories.

Each private source repository is read with its own repository-scoped,
read-only PAT on an ephemeral runner. Source files, production configuration,
frontend source maps, and project build directories are never published or
cached. Release archives contain the compiled control binary and runtime
assets only.

