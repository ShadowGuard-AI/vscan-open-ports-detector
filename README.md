# vscan-open-ports-detector
Performs a quick scan of common open ports on a target host or network, specifically focusing on ports often associated with vulnerable services or misconfigurations that can be exploited. - Focused on Lightweight web application vulnerability scanning focused on identifying common misconfigurations and publicly known vulnerabilities

## Install
`git clone https://github.com/ShadowStrikeHQ/vscan-open-ports-detector`

## Usage
`./vscan-open-ports-detector [params]`

## Parameters
- `-h`: Show help message and exit
- `-p`: Specify a list of ports to scan. Defaults to common vulnerable ports.
- `-t`: No description provided
- `-v`: Enable verbose output for debugging.

## License
Copyright (c) ShadowStrikeHQ

## Behaviour notes
The -v flag sets the log level to DEBUG, so closed port lines appear. The target is resolved once before scanning; a target that cannot be resolved prints a scan failed line and exits non-zero. Every completed scan ends with a summary count of open, closed, and errored ports.
