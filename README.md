# SphinxTemplate
Document writing environment for software engineers using Sphinx

# How to build

```
# Go top directory
cd SphinxTemplate
docker build -f docker/Dockerfile -t sphinx .
```

# How to run

```
cd SphinxTemplate
docker run --rm \
-u $(id -u $USER):$(id -g $USER) \
-it -v ${PWD}/src/sample:/docs \
sphinx bash -c "cd /docs && make clean latexpdf"
```
