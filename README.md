# Terraform (Docker Container)

[![Circle CI](https://circleci.com/gh/sjourdan/terraform-docker.svg?style=shield)](https://circleci.com/gh/sjourdan/terraform-docker)

Terraform is a tool for building, changing, and versioning infrastructure safely and efficiently. Terraform can manage existing and popular service providers as well as custom in-house solutions.

This container exists because I need to easily and quickly switch between various specific versions of Terraform for different projects, and use the same linux binary whatever platform I'm using.

- [Terraform Homepage](https://www.terraform.io/)
- [Terraform on GitHub](https://github.com/hashicorp/terraform)

## Supported tags

-	[`0.7.0-rc2`, `latest` (*Dockerfile*)](https://github.com/sjourdan/terraform-docker/blob/0.7.0-rc2/Dockerfile)
-	[~~`0.6.16`~~ (*Dockerfile*)](https://github.com/sjourdan/terraform-docker/blob/0.6.16/Dockerfile)
-	[`0.6.15` (*Dockerfile*)](https://github.com/sjourdan/terraform-docker/blob/0.6.15/Dockerfile)
-	[`0.6.14` (*Dockerfile*)](https://github.com/sjourdan/terraform-docker/blob/0.6.14/Dockerfile)

## Usage

Usage is basically the following:

```
$ docker run -it --rm -v `pwd`:/data sjourdan/terraform:<version> <terraform sub-command>
```

For example, if for a project you need version `0.6.14`:

```
$ docker run -it --rm -v `pwd`:/data sjourdan/terraform:0.6.14
```

And for another project you need the later `0.6.15` version:

```
$ docker run -it --rm -v `pwd`:/data sjourdan/terraform:0.6.15
```

## Known Bugs

- `0.6.16` doesn't work because of [this issue](https://github.com/hashicorp/terraform/issues/6714)

## Build

```
$ make build
```

### Release Tags

The Docker Hub build is building versions across tags, so tag releases properly:

```
$ git tag <terraform version>
$ git push --tags
```
