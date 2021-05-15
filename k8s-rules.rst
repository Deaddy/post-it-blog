# rules for using k8s
- always run from .yml files, not kubectl run xxx or similar command line
  ninjaing
- strive for keeping everything in git
- use templating such as helm when appropriate
- be pure and handle deployment logic in kubernetes, e.g. initcontainers,
  scripts as configmaps etc., but not baked into the containers (so no
  entrypoint scripts etc.)
