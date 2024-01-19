# Azure Playground

### Entire repo has been excluded from language stats

To exclude repo from language stats:
- in root create `.gitattributes`
- then add to `.gitattributes`:
    - entire repo:
        - `* linguist-vendored`
    - directory named 'foo':
        - `foo/* linguist-vendored`
    - nested directories:
        - `foo/bar/* linguist-vendored`
    - files of type 'html':
        - `*.html linguist-vendored`
    - a single file:
        - `foo.js linguist-vendored`