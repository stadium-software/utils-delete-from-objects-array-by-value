# Delete by property value

A script to remove an item from a List of objects by the value or a property

# Version 

1.0 Initial

# Global Script Setup
1. Create a Global Script called "RemoveObjectByProperty"
2. Add the input parameters below to the Global Script
   1. List
   2. Property
   3. Value
3. Add the output parameter below to the Global Script
   1. Result
4. Drag a *JavaScript* action into the script
5. Add the Javascript below into the JavaScript code property
```javascript
/* Stadium Script 1.0 https://github.com/stadium-software/utils-find-object-by-property */
let list = ~.Parameters.Input.List;
let property = ~.Parameters.Input.Property;
let value = ~.Parameters.Input.Value;
list.splice(list.findIndex(item => item[property] === value), 1);
return list;
```
6. Drag a *SetValue* action into the Global Script and place it under the *JavaScript* action
   1. Target: = ~.Parameters.Output.Result
   2. Value: = ~.Javascript

## Usage
1. Drag the script called "RemoveObjectByProperty" into a script or event handler
2. Enter values for the script input parameters
   1. List: A List of objects
   2. Property: The name of the property to locate
   3. Value: The value the property to remove
3. Result: The script returns a List without the supplied