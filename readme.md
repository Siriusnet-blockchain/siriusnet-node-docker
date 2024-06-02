```
# Build the Docker image
docker build -t besu-node .

# Run the Docker container
docker run -d --name besu-node -p 30305:30305 besu-node


docker run -p 30303:30303 -p 30304:30304 -p 8546:8546 \
  --name besu-node \
  -v $(pwd)/data:/data \
  -v $(pwd)/genesis.json:/genesis.json \
  hyperledger/besu:latest \
  besu \
  --data-path=/data \
  --genesis-file=/genesis.json \
  --network-id=123 \
  --rpc-http-enabled \
  --rpc-http-api=ETH,NET,CLIQUE \
  --host-allowlist="*" \
  --rpc-http-cors-origins="all" \
  --bootnodes="enode://4f60cd410f9d12a1f73bb0df6ab9ae0a6c7f39ddb2f5a7e3a8efafd8217925cab73fb9d0b8b6060bbdf32f2f103eae54dcced861a5d44391c7928c2677b242b2@159.65.144.118:30313" \
  --p2p-port=30304 \
  --rpc-http-port=8546



  docker run -p 30303:30303 -p 30304:30304 -p 8546:8546 \
  --name besu \
  -v $(pwd)/data:/data \
  -v $(pwd)/genesis.json:/genesis.json \
  hyperledger/besu:latest \
  /bin/sh -c "besu --data-path=/data --genesis-file=/genesis.json --network-id=123 --rpc-http-enabled --rpc-http-api=ETH,NET,CLIQUE --host-allowlist=\"*\" --rpc-http-cors-origins=\"all\" --bootnodes=\"enode://4f60cd410f9d12a1f73bb0df6ab9ae0a6c7f39ddb2f5a7e3a8efafd8217925cab73fb9d0b8b6060bbdf32f2f103eae54dcced861a5d44391c7928c2677b242b2@159.65.144.118:30313\" --p2p-port=30304 --rpc-http-port=8546"


```


docker run -p 30303:30303 -p 30304:30304 -p 8546:8546 \
  --name besu-node \
  -v $(pwd)/data:/data \
  -v $(pwd)/genesis.json:/genesis.json \
  hyperledger/besu:latest \
  "besu --data-path=/data --genesis-file=/genesis.json --network-id=123 --rpc-http-enabled --rpc-http-api=ETH,NET,CLIQUE --host-allowlist=\"*\" --rpc-http-cors-origins=\"all\" --bootnodes=\"enode://4f60cd410f9d12a1f73bb0df6ab9ae0a6c7f39ddb2f5a7e3a8efafd8217925cab73fb9d0b8b6060bbdf32f2f103eae54dcced861a5d44391c7928c2677b242b2@159.65.144.118:30313\" --p2p-port=30304 --rpc-http-port=8546"