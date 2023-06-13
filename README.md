Preview:
Internet Unique ID Identifier
![image](https://github.com/vaibhav-oo7/crypto-token/assets/97470918/37a67dac-8036-4b3b-ba9a-43fd99716651)
![image](https://github.com/vaibhav-oo7/crypto-token/assets/97470918/8a5eacd8-017f-4aaa-9940-116fb275efe6)


Wallet

![image](https://github.com/vaibhav-oo7/crypto-token/assets/97470918/8040292b-7743-4f90-b79f-2b5380159178)


image
# Check your Balance

1. Find out your principal id:

```
dfx identity get-principal
```

2. Save it somewhere.cxia3-w6xac-evbue-2iqm3-lqbcj-3luqd-bpbay-cwka6-6xdsa-hhrm6-kae

e.g. My principal id is: 


3. Format and store it in a command line variable:
```
OWNER_PUBLIC_KEY="principal \"$( \dfx identity get-principal )\""
```

4. Check that step 3 worked by printing it out:
```
echo $OWNER_PUBLIC_KEY
```

5. Check the owner's balance:
```
dfx canister call token balanceOf "( $OWNER_PUBLIC_KEY )"
```

# Charge the Canister


1. Check canister ID:
```
dfx canister id token
```

2. Save canister ID into a command line variable:
```
CANISTER_PUBLIC_KEY="principal \"$( \dfx canister id token )\""
```

3. Check canister ID has been successfully saved:
```
echo $CANISTER_PUBLIC_KEY
```

4. Transfer half a billion tokens to the canister Principal ID:
```
dfx canister call token transfer "($CANISTER_PUBLIC_KEY, 500_000_000)"
```

# Deploy the Project to the Live IC Network

1. Create and deploy canisters:

```
dfx deploy --network ic
```

2. Check the live canister ID:
```
dfx canister --network ic id token
```

3. Save the live canister ID to a command line variable:
```
LIVE_CANISTER_KEY="principal \"$( \dfx canister --network ic id token )\""
```

4. Check that it worked:
```
echo $LIVE_CANISTER_KEY
```

5. Transfer some tokens to the live canister:
```
dfx canister --network ic call token transfer "($LIVE_CANISTER_KEY, 50_000_000)"
```

6. Get live canister front-end id:
```
dfx canister --network ic id token_assets
```
7. Copy the id from step 6 and add .raw.ic0.app to the end to form a URL.
e.g. zdv65-7qaaa-aaaai-qibdq-cai.raw.ic0.app
