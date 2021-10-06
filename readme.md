# GitHub Actions Composibility Tests

This is a repo which shows off the composibility of GitHub Actions. There are 3 workflows that all setup a Rust project and run tests across the 3 main operating systems and both stable and nightly versions of Rust.

The first version, `main.yml` does it without any composibility. This is the baseline of what has existed for the past few years of Actions.

The second version, `main-with-composite-action.yml` uses the [using: composite](https://docs.github.com/en/actions/creating-actions/metadata-syntax-for-github-actions#runsstepsuses) functionality where you can nest actions, shell scripts, and docker container runs within an action.

The final version, `main-with-reusable-workflow.yml` takes `main.yml` and exposes it to be used in another workflow using the newly released (in beta as of Oct 5) [reusable workflows feature](https://docs.github.com/en/actions/learn-github-actions/reusing-workflows). Then the workflow can be called similarly to how you call an action using the `uses` step, but at the root of a job rather than inside the `steps` section of a job.
