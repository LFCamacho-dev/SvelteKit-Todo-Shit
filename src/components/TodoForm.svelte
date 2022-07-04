<script>
import { subscribe } from 'svelte/internal';

    import { addTodo } from '../stores/todoStore.js';
    import { user } from '../stores/authStore.js';
    
    let todo = ''
    const handleSubmit = () => {
        addTodo(todo, $user.id);
        todo = '';
    }
</script>

<form class="my-6" on:submit|preventDefault="{handleSubmit}">
    <div class="flex flex-col text-sm mb-2">

        <label class="font-bold mb-2 text-gray-200" for="todo">ToDo</label>
        <input bind:value="{todo}" class="appearance-none shadow-sm border border-gray-200 p-2 focus:outline-none focus:border-gray-500 rounded-lg" type="text" id="todo" placeholder="Whatcha gonna do?">
    </div>
    <button class="w-full shadow-sm rounded bg-blue-500 hover:bg-blue-600 text-white py-2 px-4">Submit</button>    
</form>


