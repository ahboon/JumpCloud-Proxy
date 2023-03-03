# JumpCloud-Proxy

Found a JumpCloud Key in your RedTeam engagement or Pentest? Thinking that Jumpcloud documentation is a pain to decipher? Using Burp? No problem!

To view what permissions your current API key has, you can use this curl sample:
```
curl -i -s -k -X $'GET' \
    -H $'Host: console.jumpcloud.com' -H $'X-Api-Key: <apiKey>' -H $'Content-Length: 2' \
    --data-binary $'\x0d\x0a' \
    $'https://console.jumpcloud.com/api/users/getSelf'
```
Full list of Admin User Types in Jumpcloud enabled with API key can be seen here: https://support.jumpcloud.com/s/article/JumpCloud-Roles

1) Register an account for jumpcloud at: https://console.jumpcloud.com/signup (skip this step if you already have)
2) Open burp and load this Project Configuration file
3) Under "Proxy" > "Proxy Settings" > "Match and replace rules", uncheck all boxes to stop match and replace
4) Click on "Open Browser" using Burp's Proxy Browser, and login to your own Jumpcloud account at https://console.jumpcloud.com/login/admin
5) Once logged in, go back to Burp. Under "Proxy" > "Proxy Settings" > "Match and replace rules", and check all boxes to enable the match and replace. At the same time,  click on the line that says "x-api-key: <Jumpcloud api key>", and replace the "<Jumpcloud api key>" with your desired Jumpcloud API key
6) Start using Jumpcloud as though you are the user of the API key!
