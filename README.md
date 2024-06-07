# ETH-Beginner-final-project


// SPDX-License-Identifier: MIT
pragma solidity >=0.6.12 <0.9.0;

contract MyToken {
    string public tokenName = "Token-1";
    string public tokenAbbrv = "MyToken";
    uint public totalSupply = 0;

    mapping(address => uint) public balances;

    function mint(address _minted, uint _value) public {
        totalSupply += _value;
        balances[_minted] += _value;
    }

    function burn(address _burned, uint _value) public {
        if(balances[_burned]>=_value)
        {
            totalSupply -= _value;
            balances[_burned] -= _value;
        }
    }
}
