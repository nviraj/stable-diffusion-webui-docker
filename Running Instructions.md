In Docker compose change

`- CLI_ARGS=--allow-code --medvram`  
to  
`- CLI_ARGS=--allow-code --lowvram`

Add following to environment variables

```
- NVIDIA_DRIVER_CAPABILITIES=compute,utility
- NVIDIA_VISIBLE_DEVICES=all
```

Create a new .wslconfig with below config

```
[wsl2]
memory=12GB
```

For Auto UI  
`docker compose -f docker-compose-modified.yml --profile auto up --build`  
For Invoke UI  
`docker compose -f docker-compose-modified.yml --profile invoke up --build`
