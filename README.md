# Utilities for Cromwell Hackathon

## Clone this repo

```bash
cd ~
git clone https://github.com/wleepang/cromwell-hackathon.git
```

## Containers

### Compiler

Compiles `cromwell.jar` from source.

#### Usage

Build the container
```bash
cd ~/cromwell-hackathon/containers/compiler
./build
```

Use the container to build cromwell

```bash
cd ~/cromwell-hackathon
git clone https://github.com/broadinstitute/cromwell.git

# this should just build cromwell
# equivalent to `sbt "project server" assembly`
docker run --rm -v $(pwd):/code cromwell-compiler

# this builds **everything**
docker run --rm -v $(pwd):/code cromwell-compiler assembly
```

If successful, the above should create a `cromwell-*-SNAP.jar` in the current folder

### Runner

Runs the cromwell server locally

#### Usage

Build the container

```bash
cd ~/cromwell-hackathon/containers/runner
./build
```

Use the container to run cromwell

```bash
cd ~/cromwell-hackathon/containers/runner
ln -s ~/cromwell-hackathon/cromwell-*-SNAP.jar cromwell.jar
./cromwell

