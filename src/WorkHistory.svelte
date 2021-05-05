<script>
  let works = [
    {
      company: 'Hooli Technologies Nigeria Limited',
      role: 'Software Developer ',
      duration: 'February 2019',
      achievements: [
        'Worked on product re-enginnering of an existing system there by increasing features   delivery by 27%.',
        'Fixed bugs and optimized softwares',
        'Worked with the marketing team to improve custumer and user experience'
      ],
    },
    {
      company: 'El-Bahrain Concept',
      role: 'Contract Developer ',
      duration: 'August 2020-Dec 2020',
      achievements: [
        'Worked and created a software based on Figma design',
        'Added features and fixed bugs on existing features',
        'Worked with the senior Developer and discuss on how to improve UX and performance'
      ],
    }
  ]
</script>

<div class=" w-full pt-3 px-4 text-gray-300 pb-5">
  <h3 class="text-center text-xl font-black text-teal-900"> MY WORK HISTORY</h3>
  <div class="mt-3">
    <ul>
      {#each works as work}
        <li>
          <div class=" bg-teal-800 py-4 px-8 mb-5 rounded-lg mx-auto lg:w-3/5">
            <h4 class="text-xl font-black">{work.company}</h4>
            <h6 class="text-white">{work.role}, <span> {work.duration}</span></h6>
            <ul class="x-auto">
              {#each work.achievements as achievement}
                <li style="list-style-type: square;">{achievement}</li>
              {/each}
            <ul>
          </div>
        </li>
      {/each}
      
    </ul>
  </div>
</div>


<style>

</style>
