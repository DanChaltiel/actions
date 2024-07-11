# bumb-dev-version
 
This action increments the dev version of an R package in DESCRIPTION:

- Installing [desc](https://desc.r-lib.org/)
- Update the dev version using `desc::desc_bump_version("dev")`
- Commit the version change
- Create the associated tag if `create-tag: true` is added

# Usage

Inputs available

- `create-tag` - default `FALSE`. Whether a tag should be created to reference the new dev version.

Basic:
```yaml
steps:
- name: Check out repository
  uses: actions/checkout@v4
- name: Set up R
  uses: r-lib/actions/setup-r@v2
  with:
    install-r: false
- name: Bump dev version
  uses: DanChaltiel/actions/bump-dev-version@v1
  with:
    create-tag: true
```

# Example

[This workflow file](https://github.com/DanChaltiel/EDCimport/blob/2da8a3670ca6d0a0be3e0aa5c171441de5055638/.github/workflows/bump_dev_version.yaml) can be copied and adapted to your needs.