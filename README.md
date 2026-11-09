# vscan-open-ports-detector

TCP connect scanner that checks a target host for open ports, focused on a built-in list of common ports often associated with vulnerable services. It reports a summary count of open, closed, and errored ports.

## Install

`git clone https://github.com/ShadowGuard-AI/vscan-open-ports-detector`

No third-party packages are required (Python standard library only, see requirements.txt).

## Usage

`python3 main.py <target> [-p PORT [PORT ...]] [-t THREADS] [-v]`

Example: `python3 main.py 127.0.0.1 -p 22 80 443`

## Parameters

- `target`: Target host or IP address to scan (positional, required)
- `-p, --ports`: List of ports to scan. Defaults to the built-in common ports list.
- `-t, --threads`: Number of threads to use for scanning (default: 10)
- `-v, --verbose`: Enable verbose (DEBUG level) output

Ports must be between 1 and 65535 and the thread count must be positive, otherwise the tool exits non-zero. The service name shown in verbose mode comes from the local services table for the port number, not from the target.

## Behaviour notes

The -v flag sets the log level to DEBUG, so closed port lines appear. The target is resolved once before scanning; a target that cannot be resolved prints a scan failed line and exits non-zero. Every completed scan ends with a summary count of open, closed, and errored ports. A result reported as closed means the connection did not succeed, which includes filtered ports where the probe received no reply.

## License

MIT (see LICENSE)
