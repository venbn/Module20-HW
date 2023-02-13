# Unit 20 - "Joint Savings Account"

![alt=“”](Images/20-5-challenge-image.png)

### Background

A fintech startup company has recently hired you. This company is disrupting the finance industry with its own cross-border, Ethereum-compatible blockchain that connects financial institutions. Currently, the team is building smart contracts to automate many of the institutions’ financial processes and features, such as hosting joint savings accounts.

To automate the creation of joint savings accounts, I have created a Solidity smart contract that accepts two user addresses. These addresses will be able to control a joint savings account. My smart contract will use ether management functions to implement a financial institution’s requirements for providing the features of the joint savings account. These features will consist of the ability to deposit and withdraw funds from the account.

### What am I Creating ?

* The complete Solidity `JointSavings` smart contract.

* A folder named `Execution_Results` have got videos showing the deposit and withdrawal transactions.

#### Step 1: Created a Joint Savings Account Contract in Solidity

1. From the provided [starter code](Starter_Code), opened the Solidity file named `joint_savings.sol` in the Remix IDE.

2. Defined a new contract named `JointSavings`.

3. Defined the following variables in the new contract:

    * Two variables of type `address payable` named `accountOne` and `accountTwo`

    * A variable of type `address public` named `lastToWithdraw`

    * Two variables of type `uint public` named `lastWithdrawAmount` and `contractBalance`


4. Defined a function named `withdraw` that accepts two arguments: `amount` of type `uint` and `recipient` of type `payable address`. In this function, coded the following:

    * Defined a `require` statement that checks if `recipient` is equal to either `accountOne` or `accountTwo`. If it isn’t, the `require` statement returns the “You don't own this account!” text.

    * Defined a `require` statement that checks if `balance` is sufficient for accomplishing the withdrawal operation. If there are insufficient funds, it returns the “Insufficient funds!” text.

    * Added an `if` statement to check if `lastToWithdraw` is not equal (`!=`) to `recipient`. If it’s not equal, set it to the current value of `recipient`.

    * Called the `transfer` function of the `recipient`, and pass it the `amount` to transfer as an argument.

    * Have set `lastWithdrawAmount` equal to `amount`.

    * Have set the `contractBalance` variable equal to the balance of the contract by using `address(this).balance` to reflect the new balance of the contract.


5. Defined a `public payable` function named `deposit`. In this function, code the following:

    * Set the `contractBalance` variable equal to the balance of the contract by using `address(this).balance`.

6. Defined a `public` function named `setAccounts` that takes two `address payable` arguments, named `account1` and `account2`. In the body of the function, set the values of `accountOne` and `accountTwo` to `account1` and `account2`, respectively.

7. Added a fallback function so that your contract can store ether that’s sent from outside the deposit function.

#### Step 2: Compiled and Deploy Your Contract in the JavaScript VM

1. Successfully compiled my smart contract. Below is the video showing succefull deployment of the contract..

https://user-images.githubusercontent.com/112692272/218420892-e71fa3b9-7640-4ed7-bd31-7be89ca9d689.mp4


2. Click the Deploy button to deploy your smart contract, and then confirm that it successfully deployed.


https://user-images.githubusercontent.com/112692272/218421077-bfb88166-a68d-4721-9f75-9a7e56279fbe.mp4


#### Step 3: Interact with Your Deployed Smart Contract

Now that the contract is deployed, tested its functionality successfully ! 

A video has been recorded for each test performed and stored in the folder named `Execution_Results`. The same folder is part of the assignment submissions

To interact with the deployed smart contract, completed the following steps:

1. Tested the deposit functionality of your smart contract by sending the following amounts of ether. After each transaction, use the `contractBalance` function to verify that the funds were added to your contract :

    * Transaction 1: Send 1 ether as wei.   

      https://user-images.githubusercontent.com/112692272/218421267-cead76aa-7589-423f-87b9-254bc812e5d2.mp4

    * Transaction 2: Additionally Send 10 ether as wei.

      https://user-images.githubusercontent.com/112692272/218421413-f4abf68e-db9b-444a-9783-a2c389685075.mp4

    * Transaction 3: Additionally Send 5 ether.

      https://user-images.githubusercontent.com/112692272/218421560-a394768d-7322-4826-82e2-3b1f14739d9b.mp4


After the above 3 transactions, you must be able to see total of 16 Ether added to the contract.

3. Once the funds are successfully deposited funds into the contract, tested the contract’s withdrawal functionality by withdrawing 5 ether into `accountOne` and 10 ether into `accountTwo`. After each transaction, used the `contractBalance` function to verify that the funds were withdrawn from your contract. Also, used the `lastToWithdraw` and `lastWithdrawAmount` functions to verify that the address and amount were correct.

Below are the videos showing the withdraw funcitonality :

    * Withdraw 5 Ether to Account 1 and show the lastToWithdraw and lastWithdrawAmount including verifying the contractBalance
    

      https://user-images.githubusercontent.com/112692272/218424477-1be9b7bf-8cb9-4beb-85b5-1b011886eac9.mp4


    * Withdraw 10 Ether to Account 2 and show the lastToWithdraw and lastWithdrawAmount including verifying the contractBalance
    

      https://user-images.githubusercontent.com/112692272/218425394-3887ff82-053e-43d1-be5c-89c6c034cfe5.mp4


      

