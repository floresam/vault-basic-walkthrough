# vault-basic-walkthrough
The most basic version of a hashicorp vault demo

1. [Download & install](https://www.vaultproject.io/downloads) vault. See the [tutorial](https://learn.hashicorp.com/tutorials/vault/getting-started-install?in=vault/getting-started) for guidance.
2. Run `vault` to verify your installation
    
    ![image](https://user-images.githubusercontent.com/15929779/160003315-56fe9143-ec7d-4cb9-9f0f-e28c60281c55.png)
3. Start your server in dev mode with `vault server -dev`
Note: NEVER EVER DO THIS IN PRODUCTION!!!!
    
    ![image](https://user-images.githubusercontent.com/15929779/160003463-63b7de1e-0416-44fb-b0f9-298e44b3188d.png)
4. Set up your environment variables
    1. `export VAULT_ADDR=‘http://127.0.0.1:8200’`
    2. `export VAULT_TOKEN="s.XmpNPoi9sRhYtdKHaQhkHP6x”`
5. Verify with `vault status`

    ![image](https://user-images.githubusercontent.com/15929779/160004264-eb1f6738-1b25-499c-8695-76c8c27ee061.png)
    
6.  Determine what path the kv secrets engine is using with `vault secrets list`
    1. My setup is using the path `secret/`. Remember that value and plug it in anywhere I use `secret/`! ![image](https://user-images.githubusercontent.com/15929779/160005249-c8e5a216-25d6-4408-b52a-4215b00568f1.png)
7.  Write a secret greeting to your kv path with `vault kv put secret/word greeting=howdy`
8.  Retrieve your secret greeting with `vault kv get secret/word`
