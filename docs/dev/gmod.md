# Garry's Mod

## Getting the VyHub user data of a player

The VyHub user of a player can be retrieved on the server as follows:

```
VyHub.Player:get(ply:SteamID64(), function(user)
    if user then
        -- user contains the VyHub user data
    else
        -- If user is nil: Given steamid was nil or API error
        -- If user is false: Given steamid was false or user could not be created
    end
end)
```

## Getting the VyHub user ID of a player

There is an easy way to get the VyHub user ID of player on the client and server:

```
local userid = ply:VyHubID()
```

The return value may be nil.

## Using the VyHub API via Lua

The VyHub API can be used via Lua on the server side. The API docs can be found [here](https://api.vyhub.app/demo/v1/docs). Please also check the API docs of your VyHub instance.

### Reference

Functions:

- `VyHub.API:get(endpoint, path_params, query, success, failed, no_error_for)`
- `VyHub.API:delete(endpoint, path_params, success, failed)`
- `VyHub.API:post(endpoint, path_params, body, success, failed, query)`
- `VyHub.API:patch(endpoint, path_params, body, success, failed)`
- `VyHub.API:put(endpoint, path_params, body, success, failed)`
  
Parameters:

  - `endpoint: String`

    The relative URL of the API endpoint, can contain `%s` as placeholders for path parameters
 
  - `path_params: Table`

    A numeric indexed table of path parameters that are used to build the endpoint URL (order sensitive)
 
  - `query: Table` 

    A key-value table with query parameters
  
  - `body: Table or String`
    
    A table or string that is used as request body. If value is a table, it will be JSON encoded before sending.
  
  - `success: Function(code, result)`
  
    A function that is called on a successful request
  
  - `failed: Function(code, reason)`
  
    A function that is called on a failed request
  
  - `no_error_for: Table`
  
    A numeric indexed table with error codes that should not trigger an error message in the server console


### Examples

- Retrieving bans of a user

  > GET /ban/?user_id=b41abcb7-64f1-4d9d-ac12-8440ad159683

```
VyHub.API:get('/ban/', nil, {'user_id': 'b41abcb7-64f1-4d9d-ac12-8440ad159683'}, function(code, result)
    print("bans of user: " .. result.items)
end,function(code, reason)
    print("error")
end)
```

- Retrieving details of one ban

  > GET /ban/3071c444-7e94-4280-88a0-fc872becbebd

```
VyHub.API:get('/ban/%s', {'3071c444-7e94-4280-88a0-fc872becbebd'}, nil, function(code, result)
    print("ban details: " .. result)
end,function(code, reason)
    print("error")
end)
```

- Creating a 20% discount code (requires `discount_edit` property)

  > POST /shop/discount/

```
local data = {
  begin = '2023-05-16T00:00:00Z',
  percentage = 20,
  code = "MYDISCOUNTCODE",
  enabled = true,
  all_packets = true,
}

VyHub.API:post('/shop/discount/', nil, data, function(code, result)
  print("success")
end,function(code, reason)
  print("error")
end)
```

### Using an API key with all required properties

By default, the API key of your gameserver can only access the resources that it needs.

It is possible to create an API key with more properties in the settinggs at `Admin -> Settings -> Servers -> <Bundle> -> Keys`.
