# noob-solidity
## Solidity Resume

The file name is solidity.sol, default file will looks like this
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0        // compiler version

// constant variable here

contract solidity {          // constract name must be the same with filename.

   // code here

}
```

### Data Types
| Data Type | Varian | Description|
|---|---|---|
|string| - | string variable |
| uint | - | unsigned integer |
| int | default is int256, int8, int16, .... | integer |
| bool | - | boolean value. true or false |
| address | - | Ethereum address |


### Variable Visibility
| Variable Type | Description |
|---|---|
| public | Outside and inside the contract can access |
| private | Hide and cannot viewed from outside. Can only be accesed in the same contract |
| internal | Can only accesed from the same contract and contract that inherit (other contract int the same file) |
| external | Can only be called from outside. Only used for function |

Default is `internal`

Example :
```
string public name = "surya"
string private yourname = "dave"
```

### Function 
| Function type | Description |
|---|---|
| pure | read-only function. Not changing any variable inside function |
| view | read-write function. You can do process for changing variable value inside function |

Example :
```
function readMyName(string _name) public pure returns(string){
  return _name;
}

function add(int _a, int _b) public view returns(int){
  int _c = _a + _b;
  return _c;
}
```

**Note** : it's tradition to add underscore (_) for private variable in function.















