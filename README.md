# Awesome GitHub Actions Security [![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re)

> A curated list of awesome things related to securing your GitHub Actions workflows.

GitHub Actions workflow files are extremely powerful and operate in a highly privileged software supply chain environment by default. Don't let their ease of implementation give you a false sense of security. It's easy to introduce supply chain vulnerabilities if you don't fully understand how workflow files are parsed and used by GitHub Actions.

This is a list of awesome resources for hardening your workflows in order to keep your CI/CD pipelines secure.

## Official resources

* [GitHub Docs: Security hardening for GitHub Actions](https://docs.github.com/en/actions/security-for-github-actions/security-guides/security-hardening-for-github-actions)
* [GitHub Blog: Tips to keep your GitHub Actions workflows secure](https://github.blog/security/supply-chain-security/four-tips-to-keep-your-github-actions-workflows-secure/)
* [GitHub Blog: Security best practices for authors of GitHub Actions](https://github.blog/security/application-security/security-best-practices-for-authors-of-github-actions/)
* [GitHub Blog: How to secure your GitHub Actions workflows with CodeQL](https://github.blog/security/application-security/how-to-secure-your-github-actions-workflows-with-codeql/)
* [GitHub Blog: Reach SLSA Level 3 with GitHub Artifact Attestations](https://github.blog/enterprise-software/devsecops/enhance-build-security-and-reach-slsa-level-3-with-github-artifact-attestations/)

## Unofficial resources

* [John Blackbourn: List of starred repos relating to GitHub Actions security](https://github.com/stars/johnbillion/lists/github-actions-security)  
  This is the non-curated source of many of the tools in this list.
* [OpenSSF: Mitigating Attack Vectors in GitHub Workflows](https://openssf.org/blog/2024/08/12/mitigating-attack-vectors-in-github-workflows/)  
  An overview of the most common attack vectors on GitHub workflows and recommendations on how to secure them.

## Static workflow file scanning

All of these scanners use static analysis to detect misconfiguration and vulnerabilities in your workflow files. They can be installed and run locally or run as part of your CI workflow on GitHub Actions. They are all capable of integrating with GitHub Code Scanning, so [you'll need to set up code scanning merge protection](https://docs.github.com/en/code-security/code-scanning/managing-your-code-scanning-configuration/set-code-scanning-merge-protection) in order for them to be effective.

* [Actionlint](https://github.com/rhysd/actionlint) ([List of rules here](https://github.com/rhysd/actionlint/blob/main/docs/checks.md))
* [Octoscan](https://github.com/synacktiv/octoscan) ([List of rules here](https://github.com/synacktiv/octoscan?tab=readme-ov-file#rules))
* [Poutine](https://github.com/boostsecurityio/poutine) ([List of rules here](https://boostsecurityio.github.io/poutine/))
* [Zizmor](https://github.com/woodruffw/zizmor) ([List of rules here](https://woodruffw.github.io/zizmor/audits/))

I'm currently using [all four of these scanners](https://github.com/johnbillion/plugin-infrastructure/blob/trunk/.github/workflows/reusable-workflow-lint.yml) on several of my repos. The scanners are complementary, they are all actively maintained, and together they provide good coverage of many aspects of workflow file security best practices as well as detecting misconfiguration and vulnerabilities.

## Security posture analysis

* [GitHub Action for OpenSSF Scorecard](https://github.com/ossf/scorecard-action)  
  Monitors and tracks the security metrics of your GitHub project, including best practices for GitHub Actions workflow files as well as many other checks. Several of the checks are opinionated which can be off-putting, but overall a valuable enough tool to recommend.

## Workflow and runner hardening

* [Harden-Runner](https://github.com/step-security/harden-runner)  
  Provides network egress filtering and runtime security for GitHub-hosted and self-hosted runners.
* [Secure-Repo](https://github.com/step-security/secure-repo)  
  Automatically applies security best practices in your GitHub repository. Covers GitHub Actions workflows plus a few other security related configurations.

## Shell script scanning

* [Shellcheck](https://github.com/koalaman/shellcheck) is the defacto solution for statically scanning and analysing shell scripts for correctness and security. It's included in various other tools such as Actionlint and Octoscan.

## Container scanning

* [grype](https://github.com/anchore/grype)  
  A vulnerability scanner for container images and filesystems.
* [Docker Scout](https://www.docker.com/products/docker-scout/) and [Docker Scout GitHub Action](https://github.com/docker/scout-action)  
  Identifies security issues, outdated packages, and potential compliance problems within container images. The GitHub Action runs Docker Scout as part of your workflows.

## Self-hosted runner security

Self-hosted Actions runners pose a higher security risk than the runners provided by GitHub. The main considerations are:

* Self-hosted runners are usually not ephemeral and therefore the risk of poisoning or interference between runs is higher.
* Self-hosted runners potentially allow access to a private network.

Resources:

* [GitHub Docs: About self-hosted runners](https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners/about-self-hosted-runners)  
  Official docs about self-hosted runners.
* [Deniz Onur Duzgun: Github Self-Hosted Runners Configuration](https://github.com/dduzgun-security/github-self-hosted-runners)  
  Best practices to follow to configure GitHub Enterprise Cloud self-hosted runners in a secure way.

## Research and hacking

* [pwnhub](https://github.com/nikitastupin/pwnhub)  
  Writings, scripts, and other results of GitHub Actions workflows vulnerabilities research.
* [Github Attack TOolkit](https://github.com/AdnaneKhan/Gato-X)  
  A fast scanning and attack tool for GitHub Actions pipelines.
* [GitHub Actions Cache Blasting](https://github.com/AdnaneKhan/ActionsCacheBlasting)  
  Proof-of-concept code for research into GitHub Actions Cache poisoning.

## Sponsors

The time that I spend maintaining this project and others is in part sponsored by:

[![Automattic](https://cdn.jsdelivr.net/gh/johnbillion/johnbillion/assets/sponsors/automattic.png)](https://automattic.com)

Plus all my kind sponsors on GitHub:

[![Sponsors](https://cdn.jsdelivr.net/gh/johnbillion/johnbillion/sponsors.svg)](https://github.com/sponsors/johnbillion)

[Click here to find out about supporting this project and my other WordPress development tools and plugins](https://github.com/sponsors/johnbillion).

## Related awesome lists

* [Awesome Actions](https://github.com/sdras/awesome-actions)
* [Awesome Software Supply Chain Security](https://github.com/bureado/awesome-software-supply-chain-security)

## License

CC0
