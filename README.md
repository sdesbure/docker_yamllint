# YAML Lint Docker

YAML lint - <https://yamllint.readthedocs.io/en/latest/>

Latest yamllint release in pip embedded into this docker.

Used to perform yaml linting into gitlab ci runner

## Docker image

[![](https://images.microbadger.com/badges/image/sdesbure/yamllint.svg)](https://microbadger.com/images/sdesbure/yamllint
"Get your own image badge on microbadger.com")
[![](https://images.microbadger.com/badges/version/sdesbure/yamllint.svg)](https://microbadger.com/images/sdesbure/yamllint
"Get your own version badge on microbadger.com")

## How to use

### Pull image

```
docker pull sdesbure/yamllint
```

## Run container

Per default, the docker will give you the version number of yamllint.

If you want to do linting you'll have to run a specific command:

```
docker run --rm -v <path for yaml to lint>:/yaml sdesbure/yamllint yamllint youryamlfiles.yaml
```

## In gitlab ci runner

Here's an example of a working configuration (that have a `lint` stage):

```
yaml_linting
  stage: lint
  image: sdesbure/yamllint
  script:
    - yamllint *.y?ml
```
