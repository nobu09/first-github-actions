# action-char-count

 This GitHub Action counts the number of the characters in the files that match the pattern and comments it on the pull request.

## Inputs
### `token`

 **Required** The GitHub Token to create a comment on a pull request.

### `patterns`

 **Required** A list of files, and wildcard patterns to count the number of characters. See [@actions/glob](https://github.com/actions/toolkit/tree/master/packages/glob) for supported patterns.

## Example Usage

 This is the example of counting the number of the characters in the all markdown files under the `articles` directory.

 ```yaml
 on:
   pull_request:
     paths:
       - "articles/**/*.md"

jobs:
  char-count:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checokut@v2
    - uses: nobu09/action-char-count@v1.0.0
      with:
        token: ${{ secrets.GITHUB_TOKEN }}
        patterns: articles/**/*.md
 ```
