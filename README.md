# subjack_docker

![Docker Pulls](https://img.shields.io/docker/pulls/bruteforce/subjack)docker.svg)

> Light weight Nmap container that uses grab_beacon_config.nse to parse Cobalt Strike Beacon for a given host.

- [Docker Container](https://hub.docker.com/r/bruteforce/subjack_docker) on Docker Hub
- [Dockerfile](https://github.com/beerMT/subjack_docker/blob/main/subjack.Dockerfile) on GitHub

## Usage

To run the script against an IP target:
```bash
docker run --rm -v $(pwd):/mnt/ bruteforce/subjack_docker -w /mnt/<target_list.txt> -ssl -v
```
> `-w` reads in the target list to enumerate against, this file directory is a mounted volume via the docker -v flag.

> `-ssl` will provide more fidelity by forcing the https session.

To receive details about sub-jack:
```bash
docker run --rm bruteforce/subjack_docker -h
```

## Target Selection

This tool can be used for offensive and defensive security posture checks. Determine public facing domains for the organization, usually cloud assets, and check to see if they are susceptible to dangling DNS/ subdomain hijacking. Subdomains can be gathered durign recon phases of an offensive engagement via passive DNS records, subdomain brute forcing Insert these domains into the target_list.txt and pass that into the subjack docker container for analysis.


## References:
* https://hub.docker.com/r/txt3rob/sub-jack (this wasn't building properly and is a bit outdated, super helpful though)
