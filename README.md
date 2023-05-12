Instructions

1. Clone Repo
2. Run `sam build`
3. Run `sam local start-api`


### Expectation
All endpoints in all nested stacks are accessible to run locally. With correct paths

Console Output
```
Mounting V1 at http://127.0.0.1:3000/v1/users [GET, OPTIONS]
Mounting V2 at http://127.0.0.1:3000/v2/users [GET, OPTIONS]
You can now browse to the above endpoints to invoke your functions. You do not need to restart/reload SAM CLI while working on your functions, changes will be reflected instantly/automatically. If you used sam build before running local commands, you will need to re-run sam build for the changes to be picked up. You only need to restart SAM CLI if you update your AWS SAM template
2023-05-11 17:31:19  * Running on http://127.0.0.1:3000/ (Press CTRL+C to quit)
```


### Reality
BasePath Mapping is ignored resulting in endpont being at wrong address. 
```
Mounting V2 at http://127.0.0.1:3000/users [GET, OPTIONS]
You can now browse to the above endpoints to invoke your functions. You do not need to restart/reload SAM CLI while working on your functions, changes will be reflected instantly/automatically. If you used sam build before running local commands, you will need to re-run sam build for the changes to be picked up. You only need to restart SAM CLI if you update your AWS SAM template
2023-05-11 17:31:19  * Running on http://127.0.0.1:3000/ (Press CTRL+C to quit)
```

