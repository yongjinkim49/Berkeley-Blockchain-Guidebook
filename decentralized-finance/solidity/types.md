# Types

1. _**Bool**_\
   _****_True/False\

2.  _**int / uint:**_

    1. uint8 up to uint256, by 8
    2. int8 to int256, by 2 multiples\


    Example:

    <pre><code><strong>contract Example{
    </strong><strong>uint UnsignedInt =50;
    </strong><strong>}</strong></code></pre>


3.  _**Address:**_\
    Stores a 20 bits value, and comes in two forms (address and address payable).\
    \
    'Address payable' also has members, which is a basis for all contracts:

    1. balance: remaining balance at the queried address
    2. transfer: transfer amount to specified address

    \
    Example:

    ```
    address test = 0x123;
    address myAddress = this;
    if  (test.balance <= 50 && myAddress.balance > 100)
    test.transfer(10);
    ```


4.  _**Structs**_\
    Solidity provides a method of defining new methods using Structs. \
    Structs are self-defined type, and can divide up multiple variables into groups.&#x20;

    \
    Example:

    ```
    pragma solidity ^0.8.16;
    contract Example_miner {
    struct Worker { // Struct
    uint output1, output2, output3;
    bool available;
    address company1, company2;
    string name;
    uint mine1, mine2, mine3, mine4, mine5;
    uint age1, age2, age3    } }
    ```


5.  _**Arrays**_\
    Arrays in Solidity can be either fixed, or dynamic\


    Example:

    ```
    uint[4] fixed;  //array of fixed length 4
    uint[] dynamic; //a dynamic array has no fixed size, it can keep growing
    ```

    \
    We can also define an array with the Struct defined as 'Worker':

    ```
    Worker[] working;
    ```


6.  _**Mappings**_\
    Mappings can be seen as hash map, assigning a hash value to each possible key. \
    \
    Mapping assignment:

    ```
    Mapping(_Keytype => _ValueType )
    ```

    \
    Example:

    ```
    contract Example {
    mapping(address => uint) public balances;
    function update(uint Updated_Balance) {
    balances[msg.sender] = Updated_Balance;  }}
    ```

    \
    \
