<h1>Учёт расходов</h1>

<form on:submit|preventDefault={addExpense}>
    <label for="name">Название</label>
    <input type="text" id="name" bind:value={newName}/>
    <br><br>
    <label for="amount">Сумма</label>
    <input type="text" id="amount" bind:value={newAmount}/>
    <br><br>
    <button type="submit">Добавить</button>
</form> 

<table>
    <thead>
        <tr>
        <th>Название</th>
        <th>Сумма</th>
        <th>Действия</th>
        </tr>
    </thead>
    <tbody>
        {#each expenses as expense, i}
        <tr>
        <td><div>{expense.name}</div> </td>
        <td><div>{expense.amount}</div> </td>
        <td><button on:click={() => deleteExpense(i)}>Удалить</button></td>
        </tr>
        {/each}
    </tbody>
</table>

<script>
    let expenses = [];

    let newName = ''; 
    let newAmount = '';

    function addExpense() { 
        if (newName.length > 0 && newAmount.length > 0) {
            const obj = { 
            name: newName, 
            amount: parseInt(newAmount),
            };
            expenses.push (obj) ;
            expenses = expenses;
            newName = '';
            newAmount = '';
        }
    }
    function deleteExpense(index) { 
        expenses.splice(index, 1);
        expenses = expenses;
    }
    </script>

<style>
    label {
     display: block;
     margin-bottom: 10px;
    }
    input[type='text'] {
     padding: 5px;
     border: 1px solid green;
     border-radius: 5px;
     margin-right: 10px;
     width: 150px;
    }
    table {
     margin-top: 20px;
     border-collapse: collapse;
     width: 100%;
     max-width:920px;
     margin-left: auto;
     margin-right: auto;  
     font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif   
    }
    th, td {
     border: 1px solid #ccc;
     padding: 8px;
     text-align: center;
    }
    th {
     background-color: #eee;
    }
    button {
     padding: 6px 40px;
     background-color: #ffffff;
     color:green;
     border: solid green;
     border-radius: 6px;
     cursor: pointer;
     font-weight: bold;
    }
    h1 {
     font-size: 24px;
     margin-bottom: 20px;
    }
   </style>