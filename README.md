# ROS 2 Build and Test Workspace Action

[![latest version](https://img.shields.io/github/v/release/ichiro-its/ros2-build-and-test-action)](https://github.com/ichiro-its/ros2-build-and-test-action/releases/)
[![commits since latest version](https://img.shields.io/github/commits-since/ichiro-its/ros2-build-and-test-action/latest)](https://github.com/ichiro-its/ros2-build-and-test-action/releases/)
[![license](https://img.shields.io/github/license/ichiro-its/ros2-build-and-test-action)](./LICENSE)
[![test status](https://img.shields.io/github/workflow/status/ichiro-its/ros2-build-and-test-action/Action%20Test?label=test)](https://github.com/ichiro-its/ros2-build-and-test-action/actions)

This action could be used to build and test a [ROS 2](https://www.ros.org/) workspace from source.

## Usage

For more information, see [action.yml](./action.yml) and the [GitHub Actions guide](https://docs.github.com/en/actions/learn-github-actions/introduction-to-github-actions).

### Default Usage

```yaml
name: Build and Test Workspace
on:
  pull_request:
    branches: [ main ]
  push:
    branches: [ main ]
jobs:
  build-and-test-workspace:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout this repository
        uses: actions/checkout@v2.3.4
        with:
          path: repository
      - name: Build and test workspace
        uses: ichiro-its/ros2-build-and-test-action@main
```

> This will be defaulted to use [ROS 2 Foxy Fitzroy](https://docs.ros.org/en/foxy/Releases/Release-Foxy-Fitzroy.html).

> It's recommended to not checkout the repository in the root directory.
> Else, test could be failed because the package's files are mixed with the build result.

### Use Different ROS 2 Distribution

```yaml
- name: Build and test workspace
  uses: ichiro-its/ros2-build-and-test-action@main
  with:
    ros2-distro: dashing
```

## License

This project is maintained by [ICHIRO ITS](https://github.com/ichiro-its) and licensed under the [MIT License](./LICENSE).
