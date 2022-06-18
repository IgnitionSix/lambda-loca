# lambda-loca
Livin La Mbda Loca

This is meant to be a lightweight, local environment for your Python lambda projects. 

Point the startup.py script to your lambda-loca.json file describing your endpoints and the lambdas that they map to and it will generate a docker-compose file that spins up a simulated API gateway, as well as any other resources that you want to pull in. The containers will be spun up with change monitoring for live reloading.

Once you are satisfied, run package.py against your lambda-loca.json to generate lambda zips and appropriate terraform to manage your API gateway definitions and lambdas.

## lambda-loca.json ##


```
	{
		"schema":"lambda-loca-v1",
		"endoints":{
			"/api/v1/order":{
				"verbs": "GET, POST, PUT, UPDATE, PATCH, DELETE",
				"layer": "default",
				"path": "/path/to/python_code"
			}
		},
		"layers":{
			"default":"/path/to/layer"
		}
	}
```