## Seed:  Zero backend API for Hardware section
**Note** all datatype on this api is `string`

### 1. `GET` /
return time on present.

#### Examples
```json
{
  "time": "11:07:05"
}
```

### 2. `POST` /users/\<userId\>
for register account. you need to fill your \<userId\> 
if request success. API will create your collection on database. (you can check your data on next request.)

#### Examples

**if create success**
```
Create 6310500256 finished
```
**if userId exists on Database**
``` 
user exists
```

### 3. `GET` /users/\<userId\>
if you registered you can see your data from this request.

Will show `userId` `led` `button` `ldr`

#### Examples

**if userId exist**
```json
{
  "userId": "6310500287",
  "led": "0",
  "button": "0",
  "ldr": "1000"
}
```
**if userId not exists**
``` 
user not found
```

### 4. `PUT` /users/\<userId\>/update
This request for update your value from HARDWARE ex. `led` , `button` , `ldr`

#### Examples

**if userId exist and body is not empty**
```
update finished
```
**if body is empty**
``` 
Please fill the body before sending request.
```

if This method success when you call `GET` /users/\<userId\> value must change too.
