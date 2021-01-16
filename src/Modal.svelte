<script>
  
export let project;
export let show = false;
</script>

<!-- This example requires Tailwind CSS v2.0+ -->
<div class="fixed z-10 inset-0 overflow-y-hidden">
  <div class="flex items-end justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block">
    <!--
      Background overlay, show/hide based on modal state.

      Entering: "ease-out duration-300"
        From: "opacity-0"
        To: "opacity-100"
      Leaving: "ease-in duration-200"
        From: "opacity-100"
        To: "opacity-0"
    -->
    <div class="fixed inset-0 transition-opacity" >
      <div class="absolute inset-0 bg-teal-900 opacity-50"></div>
    </div>

    <!-- This element is to trick the browser into centering the modal contents. -->
    <span class="hidden sm:inline-block align-middle sm:h-screen" aria-hidden="true">&#8203;</span>
    <!--
      Modal panel, show/hide based on modal state.

      Entering: "ease-out duration-300"
        From: "opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
        To: "opacity-100 translate-y-0 sm:scale-100"
      Leaving: "ease-in duration-200"
        From: "opacity-100 translate-y-0 sm:scale-100"
        To: "opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
    -->
    <div class="inline-block align-bottom bg-white rounded-lg text-left overflow-hidden shadow-xl transform transition-all my-auto sm:align-middle sm:max-w-lg w-full" role="dialog" aria-modal="true" aria-labelledby="modal-headline">
      <div class="bg-teal-900 px-4 pb-4 p-3 sm:pb-4">
        <div class="sm:flex sm:items-start">
          
          <div class="ml-5 mx-auto text-white">
            <p class="text-2xl">{project.name}</p>
            <ul class="">
            {#each project.stack as stack}
              <li>{stack}</li>
            {/each}
              
            </ul>
          </div>
        </div>
        <button class="mt-3 w-1/4 bg-gray-300 text-teal-900 rounded transition ease-linear duration-300 hover:bg-transparent hover:text-white" on:click>Close</button>
      </div>
    </div>
  </div>
</div>

<style>
  button:focus{
    outline: none;
  }
</style>