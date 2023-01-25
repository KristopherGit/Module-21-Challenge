# Module-21-Challenge
# KaseiCoin 


<p align= "left" width="100">
<img width= "30%" src="Starter_Code/Images/20-5-challenge-image.png">
</p>

---

## <i>Overview of the Analysis</i>

---

## <b>Purpose:</b>

The purpose of this program is to code a Smart Contract that serves as a joint savings decentralized Ethereum account. The intention is to automate the process & features of a standard joint savings account (from a conventional financial institution) as a cost savings initiative with the benefit of increased transparency, accountability & enhanced encrypted security. Specifically, the joint savings account will accept two user addresses which have control over said account. The main features in this contract will consist of the ability to deposit & withdraw funds from the main contract account in & out of the two designated ETH account addresses (accountOne & accountTwo). 

---

## <b>Process & Variables:</b>

The sequence of steps in this project are as follows:
<ol> 
Step 1: Create a Joint Savings Account Contract in Solidity
<br>
Step 2: Compile and Deploy Contract in JavaScript VM (Remix (Berlin) or (London))
<br>
Step 3: Interacting with Deployed Smart Contract </ol>


### <b><u>Step 1: Create a Joint Savings Account Contract in Solidity</b></u>
<br>
i.) Create a new Solidity file in the Remix IDE named joint_savings.sol. 
<br>
ii.) Define a new contract called JointSavings. 
<br>
iii.) Define the following variables in the contract: 
<br>
<ol> 
a.) Two variables of type 'address payable' named 'accountOne' and 'accountTwo'.
<br>
b.) A variable of type 'address public' named 'lastToWithDraw'.
<br>
c.) Two variables of type 'uint public' named 'lastWithdrawAccount' and 'contractBalance'. 
</ol>
iv.) Define a function named 'withdraw' that accepts two arguments: 'amount' of type 'uint' & 'recipient' of type 'payable address'. In this function, create code as follows: 
<ol> a.) Define a 'require' statement that checks if 'recipient' is equal to either 'accountOne' or 'accountTwo'. If it isn't, the require statement will return the "You don't own this account!" text.
<br>
b.) Define a 'require' statement that checks if balance is sufficient for accomplishing the withdrawal operation. If insufficient funds exist, it will return "Insufficient funds!" text.
<br>
c.) Add an 'if' statement to check if lastToWithdraw is not equal to '(!=) recipient'. If it isn't equal, set it to the current value of 'recipient'.
<br>
d.) Call the 'transfer()' function of the 'recipient', and pass it the 'amount' to transfer as an argument. 
<br>
e.) Set 'lastWithdrawAmount' equal to 'amount'. 
<br>
f.) Set the 'contractBalance' variable equal to the balance of the contract by using 'address(this).balance' to reflect the new balance of the contract.
<br></ol>
v.) Define a 'public payable' function named 'deposit'. In this function, code is initiated as follows: 
<br>
<ol>a.) Set the 'contractBalance' variable equal to the balance of the contract by using 'address(this).balance'. 
<br></ol>
vi.) Define a 'public' function named 'setAccounts' that takes two 'address payable' arguments, named 'account1' and 'account2'. In the body of the function, set the values of 'accountOne' and 'accountTwo' to 'account1' and 'account2', respectively.
<br>
vii.) A fallback function is added so that the contract can store ETH that's sent from outside of the 'deposit' function.

<br>

### <u><b>Step 2: Compile and Deploy Contract in JavaScript VM (Remix (Berlin) or (London))</b></u>
<br>
i.) The smart contract is then check for errors & compiled. Any additional errors will be caught sequentially by the compiler. 
<br>
ii.) In Remix IDE, the 'Deploy & Run Transactions' pane is selected and the 'Remix (Berlin)' environment is set.
<br>
iii.) The deploy button is selected to deploy the smart contract.

<br>

### <u><b>Step 3: Interacting with Deployed Smart Contract</b></u>
<br>
Testing of the smart contract is then undertaken. After each function & class call button is initiated captured screenshots were produced in order to verify the correct functionality of the smart contract. These cropped .png images are collectively stored in the root 'Execution_Results' folder, and additionally, listed below.

<br>

i.) Next, the 'setAccounts' function is called to define the authorized Ethereum addresses (for 'accountOne' & 'accountTwo'). The addresses can be simply copy/pasted from above on the environment contract dropdown menu. (Note: Each test ETH account should hold 100.0 ETH as default).
<br>
ii.) The 'deposit' functionality is then tested by sending the following amounts of ETH and recording screenshots of each transaction: 
<br>
<ol> a.) Transaction 1: Send 1 ETH as Wei.
<br>
b.) Transaction 2: Send 10 ETH as Wei. 
<br>
c.) Transaction 3: Send 5 ETH.
<br></ol>
iii.) Following each transactional step, the 'contractBalance', 'lastToWithdraw' & 'lastWithdrawAmount' functions are invoked to ensure the correct addresses & amounts have been called.
<br>

---

## <b>Results:</b>

<u> 1.) Testing 'setAccounts' Functionality: </u>

  <p align= "left" width="60">
  <img width= "100%" src="Starter_Code/Execution_Results/step3_1_setAccounts.png">
  </p>

  <i>The figure above demonstrates invoking the 'setAccounts()' function button to set 'accountOne = 0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2' & 'accountTwo = 0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db' to their respective Remix (Berlin) test wallet addresses (index 1 & index 2, respectively).</i>
  <br>
  <br>

<u> 2.) Testing 'deposit()' Functionality (Transaction 1: Send 1 ETH as Wei): </u>

  <p align= "left" width="60">
  <img width= "100%" src="Starter_Code/Execution_Results/step3_2_deposit_transaction_1.png">
  </p>

  <i>Above, the 'deposit()' function is used to send 1 ETH as Wei from both 'accountOne = 0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2' & 'accountTwo = 0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db' to the contract address wallet. This can be confirmed by the 2 ETH total shown in the JointSavings (contract address ='0XD91...39138') total Deployed Contract ETH Balance at the bottom of the left-sidebar.</i>
  <br>
  <br>

<u> 3.) Testing 'deposit()' Functionality (Transaction 2: Send 10 ETH as Wei):</u>

  <p align= "left" width="60">
  <img width= "100%" src="Starter_Code/Execution_Results/step3_2_deposit_transaction_2.png">
  </p>

  <i>Above, the 'deposit()' function is used to send 10 ETH as Wei from both 'accountOne = 0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2' & 'accountTwo = 0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db' to the contract address wallet. This can be confirmed by the 22 ETH total shown in the JointSavings (contract address ='0XD91...39138') total Deployed Contract ETH Balance at the bottom of the left-sidebar.</i>
  <br>
  <br>

<u> 4.) Testing 'deposit()' Functionality (Transaction 3: Send 5 ETH):</u>

  <p align= "left" width="60">
  <img width= "100%" src="Starter_Code/Execution_Results/step3_2_deposit_transaction_3.png">
  </p>

  <i> Above, the 'deposit()' function is used to send 5 ETH as Wei from both 'accountOne = 0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2' & 'accountTwo = 0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db' to the contract address wallet. This can be confirmed by the 32 ETH total shown in the JointSavings (contract address ='0XD91...39138') total Deployed Contract ETH Balance at the bottom of the left-sidebar. </i>
  <br>
  <br>

<u> 5.) Testing 'withdraw()' Functionality (Withdraw 5 ETH Into 'accountOne'):</u>

  <p align= "left" width="60">
  <img width= "100%" src="Starter_Code/Execution_Results/step3_3_withdraw_5eth_accountOne.png">
  </p>

  <i>Above, the 'withdraw()' function is used to send 5 ETH as Wei from the JointSavings contract address into 'accountOne = 0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2'. This is confirmed by the 'lastToWithDraw' address being 'accountOne = 0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2', contract address being reduced by 5 ETH, and the 'lastWithdrawAmount' as 5 ETH.</i> 
  <br>
  <br>

<u> 6.) Testing 'withdraw()' Functionality (Withdraw 10 ETH Into 'accountTwo'):</u>

  <p align= "left" width="60">
  <img width= "100%" src="Starter_Code/Execution_Results/step3_3_withdraw_10eth_accountTwo.png">
  </p>

  <i>Above, the 'withdraw()' function is used to send 10 ETH as Wei from the JointSavings contract address into 'accountTwo = 0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db'. This is confirmed by the 'lastToWithDraw' address being 'accountTwo = 0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db', contract address being reduced further by 10 ETH, and the 'lastWithdrawAmount' as 10 ETH. </i>
  <br>
  <br>




## <b>Summary:</b>

In summary, the functionality of the ETH Smart Contract 'JointSavings' proves promising as an alternative decentralized joint savings account compared to a conventional savings account. The main 'JointSavings' contract address was able to act as a centralized store of value for ETH in which two assigned ('accountOne' & 'accountTwo') ETH wallets could interact to deposit funds, but also withdraw funds to their respective wallets out of the main contract account. 
