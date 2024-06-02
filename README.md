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
docker run -it -v ${PWD}/src/sample:/doc sphinx bash -c "cd /doc && make clean latexpdf"
```