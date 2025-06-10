# metazama
lam cho meta


----------------------------------
contract somina de deploy


// SPDX-License-Identifier: MIT
pragma solidity ^0.8.22;

contract tonythanh {
    string public name;
    address public owner;

    event NameChanged(string oldName, string newName);

    modifier onlyOwner() {
        require(msg.sender == owner, "Only the owner can perform this action");
        _;
    }
    
    constructor(string memory _initialName) {
        name = _initialName;
        owner = msg.sender;
    }

    function changeName(string memory _newName) external onlyOwner {
        string memory oldName = name;
        name = _newName;
        emit NameChanged(oldName, _newName);
    }

    function greet() external view returns (string memory) {
        return string(abi.encodePacked("Hello tonythanh, ", name, "!"));
    }
}


// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract SimpleWallet {
    address public owner;

    constructor() {
        owner = msg.sender;
    }

    receive() external payable {}

    function withdraw() public {
        require(msg.sender == owner, "Not owner");
        payable(owner).transfer(address(this).balance);
    }

    function getBalance() public view returns (uint) {
        return address(this).balance;
    }
}



// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Counter {
    int public count = 0;

    function increment() public {
        count += 1;
    }

    function decrement() public {
        count -= 1;
    }
}


sau khi chạy xong dán lệnh này chạy tiếp:  git push

Commit 1 line
Commit 2 line
Commit 3 line
Commit 4 line
Commit 5 line
Commit 6 line
Commit 7 line
Commit 8 line
Commit 9 line
Commit 10 line
