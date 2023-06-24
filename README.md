# noob-solidity
#### Solidity Resume

The file name is solidity.sol, default file will looks like this
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0        // compiler version

// constant variable here

contract solidity {          // contract name must be the same with filename.

   // code here

}
```

## Data Types
| Data Type | Varian | Description|
|---|---|---|
|string| - | string variable |
| uint | - | unsigned integer |
| int | default is int256, int8, int16, .... | integer |
| bool | - | boolean value. true or false |
| address | - | Ethereum address |


## Variable Visibility
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

## Function 
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


## Storage type
| Storage type | Description |
|---|---|
| storage | Declared outside the functoin. Saved in blockchain |
| memory | Temporary variable. Declared inside the function or in function parameter |
| call data | Temporary variable. Same as `memory`, but can't change value inside variable. Ussually used with external function |

Example : 
```
contract myContract {
   uint myNumber = 1234;      // stored in blockchain

   function testFunction(uint memory _inputNumber) public view returns(uint memory){
   }
}
```

## Object Oriented Programming
```
contract oopContract {
   // Declare variable
   string public name;
   uint public age;

   // create an object
   constructor(string memory _name, uint memory _age){
      name = _name;
      age = _age;
   }
}
```

## Require and modifier in Function
Used to give a condition that must be fullfilled to execute the function

Example : 
Function is executed if the executor has the same ethereum address with the contract issuer.

```
contract myContract {
   string age = 13;
   address owner;

   // create construtor and run only once when first deploy
   constructor(){
      owner = msg.sender;
   }

   // condition to successfully execute
   modifier contractOwner() {
      //require(check executor, give "not owner" if not same)
      require(owner == msg.sender, "Not owner");
      _;            // must add this
   }

   function changeMyAge(string memory _newAge) public contractOwner {
      age = _newAge;
   }
}
```

## Mapping

Like dictionary in python

Example
```
// mapping(key ==> valueParameter) mappingName;
mapping(uint => string) public job;

// add value to mapping
//mappingName[key] = value;
job[1] = "Smart Contract Developer"

```





















