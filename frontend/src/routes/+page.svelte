<script lang="ts">
  import { onMount } from 'svelte';
  import { supabase } from '$lib/supabase';

  let tasks: any[] = [];

  onMount(async () => {
    const { data, error } = await supabase
      .from('tasks')
      .select('*')
      .order('created_at', { ascending: false });

    if (error) {
      console.error('Error fetching tasks:', error);
    } else {
      tasks = data || [];
    }
  });
</script>

<div class="bg-white shadow rounded-lg p-6">
  <div class="flex justify-between items-center mb-6">
    <h2 class="text-2xl font-bold text-gray-900">Tasks</h2>
    <button class="btn-primary">New Task</button>
  </div>

  {#if tasks.length === 0}
    <p class="text-gray-500 text-center py-4">No tasks yet. Create one to get started!</p>
  {:else}
    <ul class="divide-y divide-gray-200">
      {#each tasks as task (task.id)}
        <li class="py-4">
          <div class="flex items-center space-x-4">
            <div class="flex-1 min-w-0">
              <p class="text-sm font-medium text-gray-900 truncate">
                {task.title}
              </p>
              <p class="text-sm text-gray-500">
                {task.description}
              </p>
            </div>
          </div>
        </li>
      {/each}
    </ul>
  {/if}
</div>
