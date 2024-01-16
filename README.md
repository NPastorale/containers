# Containers Repository <!-- omit from toc -->

This collection houses a variety of containers that I use on my Kubernetes deployments.

- [Containers Overview](#containers-overview)
  - [BIND 9](#bind-9)
  - [kubectl](#kubectl)
  - [rsync](#rsync)
- [Contributing](#contributing)
- [License](#license)

## Containers Overview

### BIND 9

- Runs the latest version of [BIND 9](https://www.isc.org/bind/) available to the Alpine package repository.

### kubectl

- Contains several utilities, i.e. `kubectl`, `curl` and `bash`. It is designed to run an IP checker script that ultimately modifies zonefiles for BIND 9 and restarts the process for the changes to be picked up.

### rsync

- Runs `rsync`. It is intended to sync files from the Arch repository mirrors.

## Contributing

Contributions are welcome! If you have a script you'd like to add or if you find a bug, feel free to open an issue or submit a pull request.

## License

This repository is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. You are free to use, modify, and distribute the scripts, but I encourage giving credit where credit is due.
