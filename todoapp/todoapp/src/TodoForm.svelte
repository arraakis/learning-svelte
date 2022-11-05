<script>
    export let addTodo;

    let newTodo = "";

    function submitForm() {
        console.log(newTodo);
        addTodo(newTodo);
        newTodo = "";
    }
</script>

<form on:submit|preventDefault={submitForm}>
    <label for=""
        >New Todo
        <input bind:value={newTodo} placeholder="Enter a todo" />
    </label>

    <button>Add Todo</button>
</form>

<style>
</style>
