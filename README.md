# Utilities for Cromwell Hackathon

## Clone this repo

```bash
cd ~
git clone https://github.com/wleepang/cromwell-hackathon.git
```

## Containers

Build all the containers

```bash
cd ~/cromwell-hackathon
./scripts/build
```

### Compiler

Compiles `cromwell.jar` from source.

#### Usage

Use the container to build cromwell

```bash
cd ~/cromwell-hackathon
git clone https://github.com/broadinstitute/cromwell.git

# this should just build cromwell
# equivalent to `sbt "project server" assembly`
./scripts/compile
```

If successful, the above should create a `cromwell-*-SNAP.jar` in the current folder and symlink it as `cromwell.jar`.
On a c5.18xlarge instance this takes about 140-200s.

### Runner

Runs the cromwell server locally

#### Usage

Use the container to run cromwell

```bash
cd ~/cromwell-hackathon/
./scripts/cromwell

