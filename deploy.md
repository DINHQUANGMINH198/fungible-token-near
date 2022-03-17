<!-- defaut testnet-->
<!-- Deploy contract -->
near login
ID=minhdq2.testnet
echo $ID
near deploy --wasmFile res/fungible_token.wasm --accountId minhdq3.glx
<!-- Call -->
CONTRACT_NAME=minhdq2.testnet
echo $CONTRACT_NAME
<!-- init -->
near call minhdq98.glx new '{"owner_id": "'minhdq98.glx'", "total_supply": "1000000000000000", "metadata": { "spec": "ft-1.0.0", "name": "MDQToken", "symbol": "MDQ", "decimals": 8 }}' --accountId minhdq98.glx --networkId localnet --nodeUrl http://10.0.0.35:3030 --walletUrl http://10.0.0.35:1234/ --helperUrl http://10.0.0.35:3002
near call minhdq98.glx new '{"owner_id": "minhdq98.glx", "total_supply": "1000000000000000", "metadata": { "spec": "ft-1.0.0", "name": "GALAXY Token", "symbol": "GLX", "decimals": 8 }}' --accountId minhdq98.glx

<!-- NOTE WINDOW: -->
near call minhdq3.glx new "{\"owner_id\": \"minhdq3.glx\", \"total_supply\": \"1000000000000000\", \"metadata\": { \"spec\": \"ft-1.0.0\", \"name\": \"GALAXY Token\", \"symbol\": \"GLX\", \"decimals\": 8 }}" --accountId minhdq3.glx 

<!-- view -->
near view $CONTRACT_NAME ft_metadata
<!-- transfer -->
<!-- deposit -->
near call minhdq3.glx storage_deposit '' --accountId minhdq.glx --amount 0.00125
<!-- Exactly 1 yoctoNEAR must be attached. -->
near call minhdq3.glx ft_transfer '{"receiver_id": "minhdq98.glx", "amount": "100000000000"}' --accountId minhdq3.glx --amount 0.000000000000000000000001  

near call minhdq3.glx ft_transfer "{\"receiver_id\": \"minhdq.glx\", \"amount\": \"100000000000\"}" --accountId minhdq3.glx --amount 0.000000000000000000000001 --networkId localnet --nodeUrl http://10.0.0.35:3030 --walletUrl http://10.0.0.35:1234/ --helperUrl http://10.0.0.35:3002 
<!-- GLX add aggument-->
--accountId minhdq.glx --networkId localnet --nodeUrl http://10.0.0.35:3030 --walletUrl http://10.0.0.35:1234/ --helperUrl http://10.0.0.35:3002