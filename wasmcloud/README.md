
```bash
	wash down --all 
	rm -rf /tmp/wash-jetstream-4222 
	wash build
	wash up -d --nats-websocket-port 4001 
	wash app deploy wadm.yaml 
	ps aux | grep nats
	curl localhost:8080
```

