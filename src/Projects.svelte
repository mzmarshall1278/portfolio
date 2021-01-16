<script>
import AppModal from './Modal.svelte';
  let projects = [
      {name: "Pipersoft", description: "Bookkeeping & Inventory management software", link: "", isDev: false, stack: ['Vue', 'Bootstrap', 'Python/Django', 'CouchDB/PouchDB']},
      {name: "Haitracker", description: "A light social Network for keeping track of friends location, time and description.", link: "", isDev: true, stack: ['Vue/Nuxt','Vuetify', 'Node/Express', 'MongoDB']},
      {name: "Corpad", description: "Corporate savings and loan Merchant software", link: "", isDev: false, stack: ['Vue/Nuxt', 'Vuetify', 'Python/Django', 'MySQL']},
      {name: "Lissafi", description: "Accounting software for small & medium businesses", link: "", isDev: false, stack: ['Vue', 'CoreUI','AntD', 'Node/Express', 'CouchDB/PouchDB']},
      {name: "Tribal Books", description: "A light social Network for keeping track of friends location, time and description.", link: "", isDev: true, stack: ['Vue/Nuxt', 'Bootstrap' ]},
      {name: "Recharge Plus", description: "A light social Network for keeping track of friends location, time and description.", link: "", isDev: true, stack: ['Vue', 'CoreUI', 'Django']},
      {name: "Usaifa", description: "A software for farming and productions stuff", link: "", isDev: true, stack: ['Vue/Nuxt', 'Tailwind']},
  ];
  let modal = false;
  let selectedProject = "";
  const showStack = (project)=>{
    selectedProject = project;
    modal = true;
  }
  let closeModal = ()=> {
    modal = false;
  }
</script>

<div class="bg-transparent sm:w-11/12 mx-auto mb-3 p-4">
  <div class="text-center text-xl font-black mb-3 text-teal-900">
    MY Projects
  </div>
  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-10">
    {#each projects as project}
    <div class="transition ease-linear duration-300 border text-teal-900 shadow-2xl rounded-lg border-teal-900 p-4 hover:shadow-md hover:border-2 hover:bg-teal-900 hover:text-gray-300">
        <div class="font-extrabold  text-center my-2 ">
          <span>{project.name}</span>
        </div>
        <div class="font-light w-10/12 text-center mx-auto my-8 h-16">
          {project.description}
        </div>
        <div class="flex justify-around my-3">
          {#if !project.isDev}
            <button class="transition ease-linear duration-300 outline-none hover:border-none rounded-full p-3 bg-teal-900 text-gray-300 hover:bg-white hover:text-teal-900 hover:font-black">View Site
              <svg class="inline-block ml-1 w-5" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 5l7 7-7 7M5 5l7 7-7 7" />
              </svg>
            </button>
          {/if}
          <button class="transition ease-linear duration-300 outline-none hover:border-none rounded-full p-3 bg-teal-900 text-gray-300 hover:bg-white hover:text-teal-900 hover:font-black" on:click={()=>{showStack(project)}}>View Stack
            <svg class="inline-block ml-1 w-5" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z" />
            </svg>
          </button>
        </div>
        {#if project.isDev}
          <div class="text-center">
            <span>
              In development
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="w-4 inline-block">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
              </svg>
            </span>
          </div>
        {/if}
    </div>
    {/each}
  </div>
</div>
{#if modal}
  <AppModal project={selectedProject} show={modal} on:click={closeModal}/>
{/if}


<style media="screen">
button:focus{
  outline: none;
}
</style>
