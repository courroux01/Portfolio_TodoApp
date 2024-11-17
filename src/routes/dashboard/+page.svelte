<div class="mainContainer">
    <header class="headerContainer">
        <h1>Todo List</h1>
        <button>Save</button>
    </header>

    <main></main>
    <div class="enterTodo">
        <input type="text" placeholder="Enter Todo">
        <button>ADD</button>
    </div>

</div>

<style>
    .mainContainer {
        display: flex;
        flex-direction: column;
        min-height: 100vh;
        height: 100vh;
        gap: 24px;
        width: 100%;
        max-width: 1000px;
        margin: 0 auto;
    }

    .headerContainer {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    main {
        display: flex;
        flex-direction: column;
        gap: 8px;
    }

    .enterTodo {
        display: flex;
        align-items: stretch;
        border: 1px solid cyan;
    }

    .enterTodo input {
        background: transparent;
        border: none;
        padding: 14px;
        color: white;
        flex: 1;
    }

    .enterTodo input:focus {
        outline: none;
    }

    .enterTodo button {
        padding: 0 14px;
        background: #003c5b;
        border: none;
        color: cyan;
        font-weight: bold;
        cursor: pointer;
    }


</style>