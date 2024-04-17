# Bind mount

- Binding localsystem files to container files
- It helps to hot relode the container while we are changing on our local system

## Binding mount

- -v /nextapp/node_modules(optional)

```bash
docker build -t image_name .

docker run -v .\app:/nextapp/app -v /nextapp/node_modules -p 3000:3000 image_name
```

## Issues in Binding on Windows

- update next.config
- [Stackoverflow_solution](https://stackoverflow.com/questions/54126848/why-nextjs-using-docker-container-did-not-reload-after-changed-code-for-dev-envi)
