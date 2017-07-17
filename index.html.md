--- 

title: Basic Swagger Combine Example 

language_tabs: 
   - shell 

toc_footers: 
   - <a href='#'>Sign Up for a Developer Key</a> 

includes: 
   - errors 

search: true 

--- 

# Introduction 

**Version:** 1.0.0 

# Authentication 
```shell
$ curl -k -XPOST https://auth.hcos.upmce.net/
```

|oauth2|*OAuth 2.0*|
|---|---| 

|apiKey|*API Key*|
|---|---| 

# /NEUTRINO/GREETING
## ***GET*** 

**Summary:** greeting

### HTTP Request 
`***GET*** /neutrino/greeting` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| name | query | name | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

# /NEUTRINO/SALUTATION
## ***DELETE*** 

**Summary:** salutation

### HTTP Request 
`***DELETE*** /neutrino/salutation` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| name | query | name | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 204 | No Content |
| 401 | Unauthorized |
| 403 | Forbidden |

# /NEUTRINO/WORD
## ***POST*** 

**Summary:** word

### HTTP Request 
`***POST*** /neutrino/word` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| name | query | name | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 201 | Created |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

# /PETS/PET
## ***POST*** 

**Summary:** Add a new pet to the store

**Description:** 

### HTTP Request 
`***POST*** /pets/pet` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | Pet object that needs to be added to the store | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 405 | Invalid input |

## ***PUT*** 

**Summary:** Update an existing pet

**Description:** 

### HTTP Request 
`***PUT*** /pets/pet` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | Pet object that needs to be added to the store | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 400 | Invalid ID supplied |
| 404 | Pet not found |
| 405 | Validation exception |

# /PETS/PET/FINDBYSTATUS
## ***GET*** 

**Summary:** Finds Pets by status

**Description:** Multiple status values can be provided with comma separated strings

### HTTP Request 
`***GET*** /pets/pet/findByStatus` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| status | query | Status values that need to be considered for filter | Yes | array |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid status value |

# /PETS/PET/FINDBYTAGS
## ***GET*** 

**Summary:** Finds Pets by tags

**Description:** Muliple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.

### HTTP Request 
`***GET*** /pets/pet/findByTags` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| tags | query | Tags to filter by | Yes | array |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid tag value |

# /PETS/PET/{PETID}
## ***GET*** 

**Summary:** Find pet by ID

**Description:** Returns a single pet

### HTTP Request 
`***GET*** /pets/pet/{petId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet to return | Yes | long |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid ID supplied |
| 404 | Pet not found |

## ***POST*** 

**Summary:** Updates a pet in the store with form data

**Description:** 

### HTTP Request 
`***POST*** /pets/pet/{petId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet that needs to be updated | Yes | long |
| name | formData | Updated name of the pet | No | string |
| status | formData | Updated status of the pet | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 405 | Invalid input |

## ***DELETE*** 

**Summary:** Deletes a pet

**Description:** 

### HTTP Request 
`***DELETE*** /pets/pet/{petId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| api_key | header |  | No | string |
| petId | path | Pet id to delete | Yes | long |

**Responses**

| Code | Description |
| ---- | ----------- |
| 400 | Invalid ID supplied |
| 404 | Pet not found |

# /PETS/PET/{PETID}/UPLOADIMAGE
## ***POST*** 

**Summary:** uploads an image

**Description:** 

### HTTP Request 
`***POST*** /pets/pet/{petId}/uploadImage` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet to update | Yes | long |
| additionalMetadata | formData | Additional data to pass to server | No | string |
| file | formData | file to upload | No | file |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |

# /PETS/STORE/INVENTORY
## ***GET*** 

**Summary:** Returns pet inventories by status

**Description:** Returns a map of status codes to quantities

### HTTP Request 
`***GET*** /pets/store/inventory` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |

# /PETS/STORE/ORDER
## ***POST*** 

**Summary:** Place an order for a pet

**Description:** 

### HTTP Request 
`***POST*** /pets/store/order` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | order placed for purchasing the pet | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid Order |

# /PETS/STORE/ORDER/{ORDERID}
## ***GET*** 

**Summary:** Find purchase order by ID

**Description:** For valid response try integer IDs with value >= 1 and <= 10. Other values will generated exceptions

### HTTP Request 
`***GET*** /pets/store/order/{orderId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| orderId | path | ID of pet that needs to be fetched | Yes | long |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid ID supplied |
| 404 | Order not found |

## ***DELETE*** 

**Summary:** Delete purchase order by ID

**Description:** For valid response try integer IDs with positive integer value. Negative or non-integer values will generate API errors

### HTTP Request 
`***DELETE*** /pets/store/order/{orderId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| orderId | path | ID of the order that needs to be deleted | Yes | long |

**Responses**

| Code | Description |
| ---- | ----------- |
| 400 | Invalid ID supplied |
| 404 | Order not found |

# /PETS/USER
## ***POST*** 

**Summary:** Create user

**Description:** This can only be done by the logged in user.

### HTTP Request 
`***POST*** /pets/user` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | Created user object | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | successful operation |

# /PETS/USER/CREATEWITHARRAY
## ***POST*** 

**Summary:** Creates list of users with given input array

**Description:** 

### HTTP Request 
`***POST*** /pets/user/createWithArray` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | List of user object | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | successful operation |

# /PETS/USER/CREATEWITHLIST
## ***POST*** 

**Summary:** Creates list of users with given input array

**Description:** 

### HTTP Request 
`***POST*** /pets/user/createWithList` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | List of user object | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | successful operation |

# /PETS/USER/LOGIN
## ***GET*** 

**Summary:** Logs user into the system

**Description:** 

### HTTP Request 
`***GET*** /pets/user/login` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| username | query | The user name for login | Yes | string |
| password | query | The password for login in clear text | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid username/password supplied |

# /PETS/USER/LOGOUT
## ***GET*** 

**Summary:** Logs out current logged in user session

**Description:** 

### HTTP Request 
`***GET*** /pets/user/logout` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | successful operation |

# /PETS/USER/{USERNAME}
## ***GET*** 

**Summary:** Get user by user name

**Description:** 

### HTTP Request 
`***GET*** /pets/user/{username}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | The name that needs to be fetched. Use user1 for testing.  | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid username supplied |
| 404 | User not found |

## ***PUT*** 

**Summary:** Updated user

**Description:** This can only be done by the logged in user.

### HTTP Request 
`***PUT*** /pets/user/{username}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | name that need to be updated | Yes | string |
| body | body | Updated user object | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 400 | Invalid user supplied |
| 404 | User not found |

## ***DELETE*** 

**Summary:** Delete user

**Description:** This can only be done by the logged in user.

### HTTP Request 
`***DELETE*** /pets/user/{username}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | The name that needs to be deleted | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 400 | Invalid username supplied |
| 404 | User not found |

<!-- Converted with the swagger-to-slate https://github.com/lavkumarv/swagger-to-slate -->
