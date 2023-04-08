# Submitting Pull Requests

To get your changes included inside the official Renda repository and on [renda.studio](https://renda.studio/), you'll
need to submit a PR (pull request) on GitHub. If you are new to contributing code on GitHub,
[this is an excellent guide](https://docs.github.com/en/get-started/quickstart/contributing-to-projects) on how to do
so.

If you're already familiar with submitting Pull Requests, read on.

## Contributing to the main repository

When you submit a pull request to the main repository, a few checks will automatically run to ensure that your code
meets certain criteria. If you like to run these checks locally first. You can run the following commands:

- `deno task test` runs all the tests. More info about arguments and debugging tests can be found
  [here](https://github.com/rendajs/Renda/blob/main/test/readme.md).
- `deno task lint` will run the linter and check code for styling issues and common mistakes. Normally it only checks
  files that have been modified or staged. If you want it to check all files you can run it with the `--all` flag.
- `deno task check` downloads dependency type files and then runs the `tsc` type checker on all the code.
- Finally there's `deno task build-studio` and `deno task build-engine`, to build Studio and the engine respectively.
  Though you'll rarely need to run this.
