# supported-resources-operator-bundle-check task

## Description:
This task validates an operator bundle image to ensure all manifests contain only allowed Kubernetes resource kinds, based on OLM's supported resources list.

### What this check does:
- Confirms the image is an operator bundle.
- Converts the bundle image to OCI format using `skopeo` and unpacks it with `umoci`.
- Locates all manifest files in the bundle.
- Verifies each manifest’s kind against an allowlist of OLM-supported kinds.
- Fails the check if any unsupported kinds are found.

## Params:

| name         | description                      | default value |
|--------------|----------------------------------|---------|
| IMAGE_URL    | Fully qualified image name.      | |
| IMAGE_DIGEST | Image digest.                    | |

## Results:

| name               | description               |
|--------------------|---------------------------|
| TEST_OUTPUT | Tekton task test output. |

## Source repository for image:
https://github.com/konflux-ci/konflux-test

## Additional links:
https://github.com/containers/skopeo
https://github.com/opencontainers/umoci
