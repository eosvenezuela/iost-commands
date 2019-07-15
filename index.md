# IOST command documentation

IOST is a multi-purpose Blockchain that uses a terminal command line to run actions to the blockchain. This website provides a guide to the most used commands.

Instructions on how to build an IOST node can be found here: [developers.iost.io](https://developers.iost.io/docs/en/1-getting-started/Overview.html)

### transfer
````
iwallet --account <YOURACCOUNT> call 'token.iost' 'transfer' '["iost","<YOURACCOUNT>","<RECEIVERACCOUNT>","1","1 iost"]'
````
### account create
````
docker-compose exec iserver ./iwallet --account <YOURACCOUNT> --amount_limit "ram:1000|iost:10" account create <NEWRACCOUNT> --initial_balance 1 --initial_gas_pledge 10 --initial_ram 10
````
### check balance
````
docker-compose exec iserver ./iwallet balance <YOURACCOUNT>
````
### import key
````
docker-compose exec iserver ./iwallet account import <YOURACCOUNT> <YOURPRIVATEKEY>
````
### buy ram
````
docker-compose exec iserver ./iwallet --account <YOURACCOUNT> call 'ram.iost' 'buy' '["<YOURACCOUNT>","<RECEIVERCCOUNT>",500]' --amount_limit '*:unlimited' --chain_id 1024
````

### check state
````
docker-compose exec iserver ./iwallet state
````
### pledge gas
````
docker-compose exec iserver ./iwallet --account <YOURACCOUNT> call 'gas.iost' 'pledge' '["<YOURACCOUNT>", "<RECEIVERACCOUNT>", "100"]'
````
### unpledge gas
````
docker-compose exec iserver ./iwallet --account iostvnzla call 'gas.iost' 'unpledge' '["iostvnzla", "iostvnzla", "10"]'
````
### get key
````
docker-compose exec iserver ./iwallet key
````
### Register a servi-node
````
docker-compose exec iserver ./iwallet --account <YOURACCOUNT> call 'vote_producer.iost' 'applyRegister' '["<PRODUCERNAME>","<PUBLICKEY>","<LOCATION>","<WEBSITE>","<NODEID>",true]' --amount_limit '*:unlimited'
````
### update-producer
````
docker-compose exec iserver ./iwallet --account <YOURACCOUNT> call 'vote_producer.iost' 'updateProducer' '["<PRODUCERNAME>","<PUBLICKEY>","<LOCATION>","<WEBSITE>","<NODEID>"]'
````
### start producer - log in
````
docker-compose exec iserver ./iwallet --account <YOURACCOUNT> call 'vote_producer.iost' 'logInProducer' '["<YOURACCOUNT>"]' --amount_limit '*:unlimited'
````
### stop producer
````
docker-compose exec iserver ./iwallet --account <YOURACCOUNT> call 'vote_producer.iost' 'logOutProducer' '["<YOURACCOUNT>"]' --amount_limit '*:unlimited'
````

### vote producer
````
docker-compose exec iserver ./iwallet --account <YOURACCOUNT> call "vote_producer.iost" "vote" '["<YOURACCOUNT>","venezuela","80000"]'
````
### unvote producer 
````
docker-compose exec iserver ./iwallet --account <YOURACCOUNT> call "vote_producer.iost" "unvote" '["venezuela","venezuela","1"]'
````
### claim rewards
````
docker-compose exec iserver ./iwallet --account <YOURACCOUNT> sys producer-redeem 6367
````
### check unclaimed balance
````
http://95.216.114.172:30001/getTokenBalance/<YOURACCOUNT>/contribute/1
````

### check node score
````
curl http://95.216.114.172:30001/getContractStorage -d '{"id":"vote_producer.iost","key":"producerScores"}'
````
### get chain info
````
http://YOURIP:30001/getChainInfo
````
### enter the docker
````
docker-compose exec iserver bash
````
### logs
````
docker-compose logs --tail 100 iserver
````
### withdraw producer vote bonus
````
docker-compose exec iserver ./iwallet --account <YOURACCOUNT> sys producer-withdraw
````
### withdraw voter bonus
````
docker-compose exec iserver ./iwallet --account <YOURACCOUNT> sys voter-withdraw
````
### check node version
````
docker exec -it iserver iwallet state | grep -E "codeVersion|gitHash"
````
<br>
<br>

# IOST VENEZUELA

This website is maintainned by IOST Venezuela, a Servi Node Candidate for the IOST Blockchain, a new consensus algorithm powered chain with the possibilities to unleash a whole new dimension of this technology. IOST Venezuela works to use these opportunities to build the future we all want!

Find out more about us here: [iostvenezuela.io](https://eosvenezuela.io/IOSTVenezuela.html)
