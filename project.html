<!DOCTYPE html>
<html lang="en" ng-app="expenseApp">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Expense Tracker</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap" rel="stylesheet">
  <style>
    /* (Same CSS as before, omitted here for brevity; use previous CSS block) */
    :root {
      --primary-color: #008080;
      --income-color: #28a745;
      --expense-color: #dc3545;
      --bg-color: #f3f4f6;
      --text-color: #333;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Inter', sans-serif;
      background-color: var(--bg-color);
      display: flex;
      justify-content: center;
      align-items: flex-start;
      min-height: 100vh;
      padding: 40px 20px;
      color: var(--text-color);
    }

    .container {
      background: white;
      width: 100%;
      max-width: 420px;
      padding: 30px;
      border-radius: 16px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.1);
    }

    h2 {
      text-align: center;
      margin-bottom: 20px;
      color: var(--primary-color);
    }

    .balance {
      text-align: center;
      font-size: 28px;
      margin: 20px 0;
      font-weight: 600;
    }

    .inc-exp {
      display: flex;
      justify-content: space-between;
      margin: 25px 0;
      gap: 15px;
    }

    .inc-exp > div {
      flex: 1;
      background: #f9f9f9;
      border-radius: 12px;
      padding: 15px;
      text-align: center;
      border: 2px solid transparent;
      transition: 0.3s ease;
    }

    .inc-exp > div:hover {
      border-color: var(--primary-color);
    }

    .income {
      color: var(--income-color);
    }

    .expense {
      color: var(--expense-color);
    }

    ul {
      list-style: none;
      margin-top: 20px;
      max-height: 200px;
      overflow-y: auto;
      padding: 0;
    }

    li {
      background: #f7f7f7;
      padding: 12px 15px;
      border-left: 5px solid;
      border-radius: 8px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 12px;
      transition: transform 0.2s;
    }

    li:hover {
      transform: scale(1.02);
    }

    li.income {
      border-color: var(--income-color);
    }

    li.expense {
      border-color: var(--expense-color);
    }

    .delete-btn {
      background: var(--expense-color);
      border: none;
      color: white;
      padding: 4px 10px;
      font-size: 14px;
      border-radius: 5px;
      cursor: pointer;
      transition: background 0.3s;
    }

    .delete-btn:hover {
      background: #b22b36;
    }

    form {
      margin-top: 30px;
    }

    input, button {
      width: 100%;
      padding: 12px;
      margin-top: 12px;
      font-size: 15px;
      border: 1px solid #ddd;
      border-radius: 8px;
      transition: 0.3s;
    }

    input:focus {
      border-color: var(--primary-color);
      outline: none;
      background-color: #f0fdfa;
    }

    button {
      background-color: var(--primary-color);
      color: white;
      font-weight: 600;
      cursor: pointer;
      border: none;
    }

    button:hover {
      background-color: #006666;
    }

    ::-webkit-scrollbar {
      width: 6px;
    }

    ::-webkit-scrollbar-thumb {
      background: #ccc;
      border-radius: 10px;
    }
  </style>
</head>
<body ng-controller="ExpenseController as expCtrl">

  <div class="container">
    <h2>💰 Expense Tracker</h2>
    <div class="balance">Balance: ₹<span>{{ expCtrl.total.toFixed(2) }}</span></div>

    <div class="inc-exp">
      <div>
        <h4>Income</h4>
        <p class="income">₹<span>{{ expCtrl.income.toFixed(2) }}</span></p>
      </div>
      <div>
        <h4>Expense</h4>
        <p class="expense">₹<span>{{ expCtrl.expense.toFixed(2) }}</span></p>
      </div>
    </div>

    <ul>
      <li ng-repeat="t in expCtrl.transactions" ng-class="{'income': t.amount > 0, 'expense': t.amount < 0}">
        {{t.text}} <span>{{ (t.amount > 0 ? '+' : '-') + '₹' + Math.abs(t.amount) }}</span>
        <button class="delete-btn" ng-click="expCtrl.removeTransaction(t.id)">x</button>
      </li>
    </ul>

    <form ng-submit="expCtrl.addTransaction()">
      <input type="text" ng-model="expCtrl.newTransaction.text" placeholder="Enter description e.g. Salary" required />
      <input type="number" ng-model="expCtrl.newTransaction.amount" placeholder="Enter amount (+income, -expense)" required />
      <button type="submit">Add Transaction</button>
    </form>
  </div>

  <!-- AngularJS CDN -->
  <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.3/angular.min.js"></script>

  <script>
    angular.module('expenseApp', [])
      .controller('ExpenseController', ['$window', function($window) {
        const vm = this;

        // Load transactions from localStorage or start empty
        vm.transactions = JSON.parse($window.localStorage.getItem('transactions')) || [];

        vm.newTransaction = {
          text: '',
          amount: null
        };

        // Calculate totals
        function calculateTotals() {
          vm.total = vm.transactions.reduce((acc, t) => acc + t.amount, 0);
          vm.income = vm.transactions.filter(t => t.amount > 0).reduce((acc, t) => acc + t.amount, 0);
          vm.expense = vm.transactions.filter(t => t.amount < 0).reduce((acc, t) => acc + t.amount, 0);
        }

        // Initial calculation
        calculateTotals();

        vm.addTransaction = function() {
          if (!vm.newTransaction.text || vm.newTransaction.amount === null) return;

          vm.transactions.push({
            id: Date.now(),
            text: vm.newTransaction.text.trim(),
            amount: +vm.newTransaction.amount
          });

          $window.localStorage.setItem('transactions', JSON.stringify(vm.transactions));
          calculateTotals();

          // Reset form
          vm.newTransaction.text = '';
          vm.newTransaction.amount = null;
        };

        vm.removeTransaction = function(id) {
          vm.transactions = vm.transactions.filter(t => t.id !== id);
          $window.localStorage.setItem('transactions', JSON.stringify(vm.transactions));
          calculateTotals();
        };
      }]);
  </script>
</body>
</html>
