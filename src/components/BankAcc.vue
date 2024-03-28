<script>
import { ref } from 'vue';
 
export default {
  setup() {
    const accHolders = ref({ firstName:'', lastName:'', routingNumber:0, balance:0 });
 
    function createAccHolder(accFirstName, accLastName, accRoutingNumber, accBalance) {
      accHolders.value.firstName = accFirstName;
      accHolders.value.lastName = accLastName;
      accHolders.value.routingNumber = accRoutingNumber;
      accHolders.value.balance = accBalance;
    }
 
    createAccHolder('Vince', 'Carter', 1234567890, 100);
 
    function deposit(amount) {
      accHolders.value.balance += amount;
    }
 
    function withdraw(amount) {
      accHolders.value.balance -= amount;
    }
 
    function transfer(amount) {
      accHolders.value.balance -= amount;
    }
 
    return {
      accHolders,
      deposit,
      withdraw,
      transfer
    };
  },
};
</script>
 
<template>
  <header class="header"> <H1>$$$</H1></header>
  <div class="logo">
    <img src="C:\ic.Stars 54\С54 Deliverables\Vue\Banking App\bank-of-icstars\src\components\icons\money.jpg" alt="bankLogo" width="150">
  </div>
  <nav>
  </nav>
  <div><header></header></div>
  <div class="intro">Welcome, {{ accHolders.firstName }} {{ accHolders.lastName }}</div>
  <br>
  <div class="balance">Balance: {{ accHolders.balance }}</div>
  <br>
  <div class="money">
    <button @click="deposit(100)">Deposit $100</button>
    <button @click="withdraw(100)">Withdraw $100</button>
    <button @click="transfer(100)">Transfer $100</button>
    </div>
</template>
 

<style scoped>

.header {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  background-color: #333;
  color: #fff;
  font-family:Georgia, 'Times New Roman', Times, serif;
  font-size: 24px;
}

.logo {
  text-align: center;
  margin-top: 20px;
  margin-bottom: 20px;
}

.intro, .balance {
  text-align: center;
  font-family:Georgia, 'Times New Roman', Times, serif;
  margin: 10px 0;
}

.intro {
  font-size: 20px;
  color: #555;
}

.balance {
  font-size: 18px;
  color: #333;
  font-weight: bold;
}

.money {
  text-align: center;
  margin-top: 20px;
}

button {
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #45a049;
}
</style>