<script>
    import { toGamer } from '$lib/toGamer';
    import { writable } from 'svelte/store';

    let input = writable('กายดี้เทพซ่า');
    let result = toGamer($input);
    
    input.subscribe(value => {
        input.set(value);
        result = toGamer(value);
    });
</script>

<div class="grid h-screen place-items-center">
    <div>
        <div class="flex flex-col justify-center gap-6">
            <p class="md:text-8xl text-6xl m-4 text-center font-bold animate-bounce">
                🎮toGamer
            </p>
            <div class="flex flex-col gap-4">
              <input type="text" class="border border-gray-500 rounded-lg p-3" bind:value={$input}>
              <input type="text" class="border border-gray-500 rounded-lg p-3" bind:value={result}>
            </div>
        </div>
    </div>
</div>
<div class="absolute top-0 left-0 p-2 text-gray-500">
  By <a href="https://github.com/tinvv">Tinnaphat Somsang (@tinvv)</a>
</div>
<div class="absolute top-0 right-0 p-2 text-gray-500">
  <a href="https://github.com/tinvv/toGamer">Github</a>
</div>