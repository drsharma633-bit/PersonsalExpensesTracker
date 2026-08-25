<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Personal Expense Tracker</title>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    :root {
      --bg: #f4f6f8;
      --card-bg: #ffffff;
      --primary: #4f46e5;
      --primary-hover: #4338ca;
      --text: #1f2937;
      --text-muted: #6b7280;
      --danger: #ef4444;
      --warning: #f59e0b;
      --success: #10b981;
      --border: #e5e7eb;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; font-family: system-ui, -apple-system, sans-serif; }
    body { background-color: var(--bg); color: var(--text); padding: 20px; }
    .container { max-width: 1000px; margin: 0 auto; }
    
    header { text-align: center; margin-bottom: 24px; }
    header h1 { font-size: 2rem; color: var(--text); }

    /* Summary Dashboard */
    .summary-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 16px; margin-bottom: 24px; }
    .card { background: var(--card-bg); padding: 20px; border-radius: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05); }
    .card h3 { font-size: 0.875rem; color: var(--text-muted); text-transform: uppercase; margin-bottom: 8px; }
    .card p { font-size: 1.75rem; font-weight: bold; color: var(--primary); }

    /* Budget Progress Bar */
    .budget-section { margin-bottom: 24px; }
    .budget-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
    .budget-controls { display: flex; gap: 8px; align-items: center; }
    .budget-controls input { width: 120px; padding: 6px 10px; border: 1px solid var(--border); border-radius: 6px; }
    .budget-controls button { padding: 6px 12px; font-size: 0.875rem; }
    .progress-bar-bg { background: var(--border); height: 16px; border-radius: 8px; overflow: hidden; }
    .progress-bar-fill { height: 100%; width: 0%; background: var(--success); transition: width 0.3s ease, background-color 0.3s ease; }
    .budget-status { font-size: 0.875rem; color: var(--text-muted); margin-top: 8px; }

    /* Main Grid */
    .main-grid { display: grid; grid-template-columns: 1fr; gap: 24px; }
    @media (min-width: 768px) { .main-grid { grid-template-columns: 1fr 1fr; } }

    /* Form Styles */
    form { display: flex; flex-direction: column; gap: 12px; }
    .form-group { display: flex; flex-direction: column; gap: 4px; }
    label { font-size: 0.875rem; font-weight: 600; }
    input, select { padding: 10px; border: 1px solid var(--border); border-radius: 6px; font-size: 1rem; }
    input:focus, select:focus { outline: 2px solid var(--primary); }
    button { background: var(--primary); color: white; border: none; padding: 12px; border-radius: 6px; font-weight: 600; cursor: pointer; transition: background 0.2s; }
    button:hover { background: var(--primary-hover); }

    /* Expense List & Chart */
    .chart-container { position: relative; height: 250px; display: flex; justify-content: center; }
    .filter-group { display: flex; justify-content: space-between; align-items: center; margin-bottom: 12px; }
    ul { list-style: none; max-height: 300px; overflow-y: auto; }
    li { display: flex; justify-content: space-between; align-items: center; padding: 12px; border-bottom: 1px solid var(--border); }
    li:last-child { border-bottom: none; }
    .expense-info { display: flex; flex-direction: column; }
    .expense-title { font-weight: 600; }
    .expense-meta { font-size: 0.75rem; color: var(--text-muted); }
    .expense-amount { font-weight: bold; color: var(--danger); }
    .delete-btn { background: transparent; color: var(--danger); border: none; font-size: 1.25rem; cursor: pointer; padding: 0 4px; }
  </style>
</head>
<body>

<div class="container">
  <header>
    <h1>Personal Expense Tracker</h1>
  </header>

  <!-- Summary Cards -->
  <div class="summary-grid">
    <div class="card">
      <h3>Total Spending</h3>
      <p id="total-amount">₹0.00</p>
    </div>
    <div class="card">
      <h3>Remaining Budget</h3>
      <p id="remaining-budget">₹0.00</p>
    </div>
    <div class="card">
      <h3>Total Transactions</h3>
      <p id="total-count">0</p>
    </div>
  </div>

  <!-- Budget Section -->
  <div class="card budget-section">
    <div class="budget-header">
      <h3>Monthly Budget Limit</h3>
      <div class="budget-controls">
        <input type="number" id="budget-input" placeholder="Set limit" min="0" step="100">
        <button id="set-budget-btn">Save</button>
      </div>
    </div>
    <div class="progress-bar-bg">
      <div id="progress-bar" class="progress-bar-fill"></div>
    </div>
    <div class="budget-status" id="budget-status">Budget limit not set.</div>
  </div>

  <div class="main-grid">
    <!-- Expense Input Form -->
    <div class="card">
      <h3>Add New Expense</h3>
      <form id="expense-form">
        <div class="form-group">
          <label for="title">Title</label>
          <input type="text" id="title" placeholder="e.g., Grocery Shopping" required>
        </div>
        <div class="form-group">
          <label for="amount">Amount (₹)</label>
          <input type="number" id="amount" step="0.01" min="0.01" placeholder="0.00" required>
        </div>
        <div class="form-group">
          <label for="category">Category</label>
          <select id="category" required>
            <option value="Food">Food</option>
            <option value="Housing">Housing</option>
            <option value="Transportation">Transportation</option>
            <option value="Entertainment">Entertainment</option>
            <option value="Utilities">Utilities</option>
            <option value="Other">Other</option>
          </select>
        </div>
        <div class="form-group">
          <label for="date">Date</label>
          <input type="date" id="date" required>
        </div>
        <button type="submit">Add Expense</button>
      </form>
    </div>

    <!-- Visualization & History -->
    <div>
      <div class="card" style="margin-bottom: 24px;">
        <h3>Breakdown by Category</h3>
        <div class="chart-container">
          <canvas id="expense-chart"></canvas>
        </div>
      </div>

      <div class="card">
        <div class="filter-group">
          <h3>Expense Log</h3>
          <select id="filter-category" style="padding: 4px 8px; font-size: 0.875rem;">
            <option value="All">All Categories</option>
            <option value="Food">Food</option>
            <option value="Housing">Housing</option>
            <option value="Transportation">Transportation</option>
            <option value="Entertainment">Entertainment</option>
            <option value="Utilities">Utilities</option>
            <option value="Other">Other</option>
          </select>
        </div>
        <ul id="expense-list"></ul>
      </div>
    </div>
  </div>
</div>

<script>
  let expenses = JSON.parse(localStorage.getItem('expenses')) || [];
  let budgetLimit = parseFloat(localStorage.getItem('budgetLimit')) || 0;
  let chartInstance = null;

  document.getElementById('date').valueAsDate = new Date();

  const form = document.getElementById('expense-form');
  const expenseList = document.getElementById('expense-list');
  const totalAmountEl = document.getElementById('total-amount');
  const remainingBudgetEl = document.getElementById('remaining-budget');
  const totalCountEl = document.getElementById('total-count');
  const filterCategory = document.getElementById('filter-category');
  const budgetInput = document.getElementById('budget-input');
  const setBudgetBtn = document.getElementById('set-budget-btn');
  const progressBar = document.getElementById('progress-bar');
  const budgetStatus = document.getElementById('budget-status');

  if (budgetLimit > 0) {
    budgetInput.value = budgetLimit;
  }

  // Save budget limit
  setBudgetBtn.addEventListener('click', () => {
    const val = parseFloat(budgetInput.value);
    if (!isNaN(val) && val >= 0) {
      budgetLimit = val;
      localStorage.setItem('budgetLimit', budgetLimit);
      saveAndRender();
    }
  });

  // Add Expense
  form.addEventListener('submit', (e) => {
    e.preventDefault();
    const newExpense = {
      id: Date.now(),
      title: document.getElementById('title').value,
      amount: parseFloat(document.getElementById('amount').value),
      category: document.getElementById('category').value,
      date: document.getElementById('date').value
    };

    expenses.push(newExpense);
    saveAndRender();
    form.reset();
    document.getElementById('date').valueAsDate = new Date();
  });

  // Delete Expense
  function deleteExpense(id) {
    expenses = expenses.filter(expense => expense.id !== id);
    saveAndRender();
  }

  filterCategory.addEventListener('change', renderExpenses);

  function saveAndRender() {
    localStorage.setItem('expenses', JSON.stringify(expenses));
    renderExpenses();
    renderSummary();
    renderChart();
  }

  function renderExpenses() {
    expenseList.innerHTML = '';
    const selectedCategory = filterCategory.value;

    const filteredExpenses = selectedCategory === 'All' 
      ? expenses 
      : expenses.filter(e => e.category === selectedCategory);

    filteredExpenses.sort((a, b) => new Date(b.date) - new Date(a.date));

    filteredExpenses.forEach(expense => {
      const li = document.createElement('li');
      li.innerHTML = `
        <div class="expense-info">
          <span class="expense-title">${expense.title}</span>
          <span class="expense-meta">${expense.category} • ${expense.date}</span>
        </div>
        <div>
          <span class="expense-amount">-₹${expense.amount.toFixed(2)}</span>
          <button class="delete-btn" onclick="deleteExpense(${expense.id})">&times;</button>
        </div>
      `;
      expenseList.appendChild(li);
    });
  }

  function renderSummary() {
    const total = expenses.reduce((sum, item) => sum + item.amount, 0);
    totalAmountEl.textContent = `₹${total.toFixed(2)}`;
    totalCountEl.textContent = expenses.length;

    if (budgetLimit > 0) {
      const remaining = budgetLimit - total;
      remainingBudgetEl.textContent = `₹${remaining.toFixed(2)}`;
      
      const percentage = Math.min((total / budgetLimit) * 100, 100);
      progressBar.style.width = `${percentage}%`;

      if (total > budgetLimit) {
        progressBar.style.backgroundColor = 'var(--danger)';
        remainingBudgetEl.style.color = 'var(--danger)';
        budgetStatus.innerHTML = `<strong>Over Budget!</strong> You have exceeded your limit by ₹${(total - budgetLimit).toFixed(2)}.`;
      } else if (percentage >= 85) {
        progressBar.style.backgroundColor = 'var(--warning)';
        remainingBudgetEl.style.color = 'var(--warning)';
        budgetStatus.textContent = `Warning: You have used ${percentage.toFixed(0)}% of your monthly budget.`;
      } else {
        progressBar.style.backgroundColor = 'var(--success)';
        remainingBudgetEl.style.color = 'var(--success)';
        budgetStatus.textContent = `You have spent ${percentage.toFixed(0)}% of your monthly limit.`;
      }
    } else {
      remainingBudgetEl.textContent = 'N/A';
      remainingBudgetEl.style.color = 'var(--primary)';
      progressBar.style.width = '0%';
      budgetStatus.textContent = 'Set a budget limit above to track progress.';
    }
  }

  function renderChart() {
    const ctx = document.getElementById('expense-chart').getContext('2d');
    
    const categoryTotals = {};
    expenses.forEach(e => {
      categoryTotals[e.category] = (categoryTotals[e.category] || 0) + e.amount;
    });

    const labels = Object.keys(categoryTotals);
    const data = Object.values(categoryTotals);

    if (chartInstance) {
      chartInstance.destroy();
    }

    chartInstance = new Chart(ctx, {
      type: 'doughnut',
      data: {
        labels: labels,
        datasets: [{
          data: data,
          backgroundColor: ['#4f46e5', '#10b981', '#f59e0b', '#ef4444', '#8b5cf6', '#6b7280']
        }]
      },
      options: {
        responsive: true,
        maintainAspectRatio: false,
        plugins: {
          legend: { position: 'bottom' }
        }
      }
    });
  }

  // Initial load
  saveAndRender();
</script>
</body>
</html>
