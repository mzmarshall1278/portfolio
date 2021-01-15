<script>
  let stacks = [
    {name: "Vue.js", image: "/images/logo.png"},
    {name: "Nuxt.js", image: "/images/nuxt.png"},
    {name: "Vuetify.js", image: "/images/vuetify.png"},
    {name: "Tailwindcss", image: "/images/tailwind.jpeg"},
    //{name: "Bootstrap", image: "/images/bootstrap.png"},
    //{name: "Typescript", image: "/images/typescript.png"},
    {name: "Express.js", image: "/images/express.png"},
    //{name: "Nest.js", image: "/images/nest.png"},
    {name: "Mongo DB", image: "/images/mongo.png"},
    {name: "GraphQL", image: "/images/graphql.png"},
    {name: "AWS", image: "/images/aws.png"}
  ]
</script>

<div class="bg-transparent sm:w-11/12 mx-auto my-3 p-4">
  <div class="text-center text-xl font-black text-teal-900">
    MY MAJOR STACK
  </div>
  <div class="grid grid-cols-3 content-center lg:grid-cols-8  md:grid-cols-6 sm:grid-cols-4 gap-5">
    {#each stacks as stack (stack.name)}
    <div class="card p-2 m-3 bg-transparent text-center rounded">
      <img src={stack.image} class="mx-auto h-12" alt="logo">
      <div class="text-gray-900 font-bold text-teal-900">
        {stack.name}
      </div>
    </div>
    {/each}
  </div>
</div>


<style media="screen">
  
</style>
