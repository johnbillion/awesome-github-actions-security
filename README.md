# Awesome GitHub Actions Security [![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re)

> A curated list of awesome things related to securing your GitHub Actions workflows.

GitHub Actions workflow files are extremely powerful. Don't let their ease of implementation give you a false sense of security. It's easy to introduce supply chain vulnerabilities if you don't fully understand how workflow files are parsed and used by GitHub Actions.

This is a list of awesome resources for hardening your workflows in order to keep your CI/CD pipelines secure.

## Official resources

* [GitHub Docs: Security hardening for GitHub Actions](https://docs.github.com/en/actions/security-for-github-actions/security-guides/security-hardening-for-github-actions)
* [GitHub Blog: Tips to keep your GitHub Actions workflows secure](https://github.blog/security/supply-chain-security/four-tips-to-keep-your-github-actions-workflows-secure/)
* [GitHub Blog: Security best practices for authors of GitHub Actions](https://github.blog/security/application-security/security-best-practices-for-authors-of-github-actions/)

## Unofficial resources

* [John Blackbourn: List of starred repos relating to GitHub Actions security](https://github.com/stars/johnbillion/lists/github-actions-security)  
  This is the non-curated source of many of the tools in this list.
* [OpenSSF: Mitigating Attack Vectors in GitHub Workflows](https://openssf.org/blog/2024/08/12/mitigating-attack-vectors-in-github-workflows/)  
  An overview of the most common attack vectors on GitHub workflows and recommendations on how to secure them.
* [Deniz Onur Duzgun: Github Self-Hosted Runners Configuration](https://github.com/dduzgun-security/github-self-hosted-runners)  
  Best practices to follow to configure GitHub Enterprise Cloud self-hosted runners in a secure way.

## Workflow file scanning

Most of these scanners integrate with GitHub Code Scanning, so [you'll need to set up code scanning merge protection](https://docs.github.com/en/code-security/code-scanning/managing-your-code-scanning-configuration/set-code-scanning-merge-protection) in order for them to be effective.

* [Octoscan](https://github.com/synacktiv/octoscan)  
  A static vulnerability scanner for GitHub action workflows. Available as a GitHub Action.
* [Poutine](https://github.com/boostsecurityio/poutine)  
  A security scanner that detects misconfigurations and vulnerabilities in workflow files on several CI/CD platforms. Available as a GitHub Action.

## Workflow and runner hardening

* [Harden-Runner](https://github.com/step-security/harden-runner)  
  Provides network egress filtering and runtime security for GitHub-hosted and self-hosted runners.
* [Secure-Repo](https://github.com/step-security/secure-repo)  
  Automatically applies security best practices in your GitHub repository. Covers GitHub Actions workflows plus a few other security related configurations.

## Shell script scanning



## Container scanning

* [grype](https://github.com/anchore/grype)  
  A vulnerability scanner for container images and filesystems.
* [Docker Scout](https://www.docker.com/products/docker-scout/) and [Docker Scout GitHub Action](https://github.com/docker/scout-action)  
  Identifies security issues, outdated packages, and potential compliance problems within container images. The GitHub Action runs Docker Scout as part of your workflows.

## Research and hacking

* [pwnhub](https://github.com/nikitastupin/pwnhub)  
  Writings, scripts, and other results of GitHub Actions workflows vulnerabilities research.
* [Github Attack TOolkit](https://github.com/AdnaneKhan/Gato-X)  
  A fast scanning and attack tool for GitHub Actions pipelines.

## Related awesome lists

* [Awesome Actions](https://github.com/sdras/awesome-actions)

## License

CC0
