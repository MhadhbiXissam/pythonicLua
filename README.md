# pythonicLua
Transpiler from python to lua 

# Example  : 

## Python 

```python
x = false
x = {}
x = {"a" : nil , "b" : 6 , "c" : "text"}
x = {a : nil , b : 6 , c : "text"}
x = idict(a = nil , b = 6 , c = "text")
y : local  = 6
for k , v in x : 
	print(k , " = " , v)

i : local = x.a
i = x["a"]

for i in irange(ilen(x)) : 
	print(x[i])

if x >= 2 : 
	if y != false and 1 <= x < 6 : 
		print("-")
	elif y == 2  : 
		print("+")
	else : 
		print(0)
else : 
	print("oops")

def print(x,i) : 
	return x + 1 

def print(x,i) ->local : 
	return x + 1 

def print(x,i) ->lvar : 
	return x + 1 

def print(x,i) ->gvar : 
	return x + 1 


if not x : 
	print("not x ")


v : local  = 1 if w > 3 else 0

import m.x
import m.r.t.v as mm

ilua("""
local v = (((w > 3)) and 1 or  0 )
""")

```


```lua
x = false
x = {}
x = {"a" = nil,"b" = 6,"c" = "text"}
x = {a = nil,b = 6,c = "text"}
x = { a = nil,b = 6,c = "text"}
local y = 6
for k , v in pairs(x) do
    print(k," = ",v)
end 
local i = x.a
i = x["a"]
for i = 1,#x,1 do
    print(x[i])
end 
if (x >= 2) then 
    if ( (y ~= false) and ( (1 <= x) and ( x < 6  ) ) ) then 
        print("-")
    elseif (y == 2) then 
        print("+")
    else 
       print(0)
   end
else 
   print("oops")
end
function print(x,i)
    return x + 1
end
local function print(x,i)
    return x + 1
end
local print = function (x,i)
    return x + 1
end
print = function (x,i)
    return x + 1
end
if (not x) then 
    print("not x ")
end
local v = (((w > 3)) and 1 or  0 )
require "m.x"
local mm  = require("m.r.t.v")

local v = (((w > 3)) and 1 or  0 )
```

# How to use  : 
## with sublime text : 
*	download the project then extracted 
*	create new build in sublime and put as build code  : 
*	```json
	subl = {
	"shell_cmd": "python3 /path to ... /pythonicLua/pythonicLua.py $file"
	}```
*	when you need to export the generated code to certain file add to the python code a line "###put_here_path_to_write_the_generated_lua_code"

## using transpiler a library  : 
*	import the pythonicLua.py then call transpile_code function
	```python
	from pythonicLua import transpile_code
	transpile_code(python_file,lua_code_file)
	```
