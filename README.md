# Simple path filtering on CircleCI

This repository demonstrates a minimalist implementation of path filtering on CircleCI.

Everything is implemented inside a single config `.circleci/config.yml`. The setup workflow/job runs on `.circleci/config.yml`, then it spools `.circleci/config.yml` again for continuation. For continuing workflows, the setup job passes 3 parameters (i.e., `run-setup`, `run-module-a` and `run-module-b`) to tell which job should run and which should not: For instance, `run-setup` is always set to `false` to avoid running the setup job again, and `run-module-a` / `run-module-b` will be set to `true` if (and only if) changes are made in `module-a` / `module-b` directory, respectively.
