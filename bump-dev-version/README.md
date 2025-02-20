# bumb-dev-version
 
This action increments the dev version of an R package in DESCRIPTION:

- Installing [desc](https://desc.r-lib.org/)
- Update the dev version using `desc::desc_bump_version("dev")`
- Commit the version change
- Create the associated tag if `create-tag: true` is added
- Update README.md if `update-readme: true` is added

# Usage

Inputs available

- `create-tag` - default `FALSE`. Whether a tag should be created to reference the new dev version.
- `update-readme` - default `FALSE`. Whether the "Installation" section in README.md should be updated with the new version.

Note on `update-readme`: This job is quite basic and will append the new version to any quoted mention of the repository name. For example, it will transform `pak::pak("DanChaltiel/crosstable")` into `pak::pak("DanChaltiel/crosstable@v0.0.0.9000")`. While this is intended to occur only in the "Installation" section, it may unintentionally affect other parts of your content.

Basic:
```yaml
steps:
- name: Check out repository
  uses: actions/checkout@v4
  
- name: Bump dev version
  uses: DanChaltiel/actions/bump-dev-version@v3
  with:
    create-tag: 'true'
    update-readme: 'true'
```

# Example

[This workflow file](https://github.com/DanChaltiel/EDCimport/blob/main/.github/workflows/bump_dev_version.yaml) can be copied and adapted to your needs.