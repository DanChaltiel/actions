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
  uses: DanChaltiel/actions/bumb-dev-version@v1
  with:
    create-tag: true
```