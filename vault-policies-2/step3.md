Now, create a token attached to the `base` policy so that you can test it.

You are going to run the `vault token create` command.  To view the full list of optional parameters for the operation, run the following command:

```
vault token create -h
```{{execute T1}}

To clear the screen: `clear`{{execute T1}}

Create a new token, and save the generated token in a file named, `token.txt`:

```
vault token create -policy="base" \
    -format=json | jq -r ".auth.client_token" > token.txt
```{{execute T1}}

<br>

## Authenticate with Base Token

Let's login with newly generated `token` (`token.txt`{{open}}).  The command is:

```
vault login $(cat token.txt)
```{{execute T1}}

Notice that the `base` policy is listed.

```
Key                  Value
---                  -----
token                s.hea9aAZJ8LMPL8Q0BJUEIk94
token_accessor       GypP6CuHkTyVHjlWkduiev2G
token_duration       767h59m50s
token_renewable      true
token_policies       ["base" "default"]
identity_policies    []
policies             ["base" "default"]
```

> **NOTE:** A built-in policy, `default`, is attached to all tokens and provides common permissions.
