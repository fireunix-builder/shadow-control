# Shadow Control Builder

Public build, release, and deployment automation for the private
`fireunix-app/shadow-control` and `fireunix-app/shadow-web` repositories.

Each private source repository is read with its own repository-scoped,
read-only deploy key on an ephemeral runner. Source files, production configuration,
frontend source maps, and project build directories are never published or
cached. Release archives contain the compiled control binary and runtime
assets only.

GitHub Releases are written back to the private control repository with a short-lived installation token of the
`fireunix-publisher` GitHub App (`RELEASE_APP_CLIENT_ID` /
`RELEASE_APP_PRIVATE_KEY` secrets), scoped to that one repository. This public repository never hosts
Releases.
The requested release tag must already exist in the private control repository.

Private source checkouts use `SOURCE_DEPLOY_KEY` and `WEB_DEPLOY_KEY` Actions secrets. Each public key is registered with read-only access on its corresponding private repository. Release identity is checked against the fetched Git tag; source read access does not require a personal token.
