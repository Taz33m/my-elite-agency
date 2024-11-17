<script>
  import { fly } from 'svelte/transition';
  
  const projects = [
    {
      title: "AI For Consultants",
      tags: ["AI", "Automation", "Consulting", "Presentations"],
      description: "An AI-powered platform that revolutionizes consulting workflows by automating report and slide creation. Designed to save time and enhance professionalism, it transforms raw data into polished presentations, while offering capabilities like AI-driven avatars for personalized delivery.",
      image: "project1.png",
      deliveryTime: "2 Days"
    },
    {
      title: "NoPad", 
      tags: ["Social", "Community", "Local", "NYC"],
      description: "NoPad is a bold, NYC-inspired social platform reimagining community engagement. Combining the exclusivity of a private network with dynamic features like hyper-local content, interactive storytelling, and collaborative idea-sharing, NoPad offers a vibrant space to connect, debate, and inspire—just like the city it celebrates.",
      image: "project2.png",
      deliveryTime: "2-3 Weeks"
    },
    {
      title: "SynthEase",
      tags: ["AI", "Computer Vision", "Data Generation", "ML"],
      description: "SynthEase generates high-quality synthetic datasets for training and testing computer vision models. Upload 3D models, customize scenes, and create lifelike images with tools like batch generation and GAN integration.",
      image: "project3.png",
      deliveryTime: "2-3 Weeks"
    },
    {
      title: "RPInSights",
      tags: ["Navigation", "AI", "Campus", "Mobile"],
      description: "RPInSights is a campus navigation app for RPI, featuring PuckMan, an AI guide that suggests locations based on your needs and provides routes for walking, biking, or driving, with detailed info on each spot",
      image: "project4.png",
      deliveryTime: "1 Day"
    }
  ];
</script>

<section class="relative py-24 overflow-hidden" id="work">
  <div class="absolute inset-0 bg-[#0A0F1C]"></div>
  
  <div class="absolute inset-0 opacity-30">
    <div class="absolute inset-0 bg-gradient-to-br from-blue-500/10 via-transparent to-purple-500/10"></div>
    <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_center,rgba(14,20,36,0)_0%,rgba(14,20,36,1)_100%)]"></div>
  </div>
  
  <div class="absolute inset-0 opacity-10">
    <div class="absolute inset-0 bg-[linear-gradient(to_right,#4f4f4f2e_1px,transparent_1px),linear-gradient(to_bottom,#4f4f4f2e_1px,transparent_1px)] bg-[size:24px_24px]"></div>
  </div>
  
  <div class="absolute top-20 left-1/4 w-96 h-96 bg-blue-500/20 rounded-full blur-[128px]"></div>
  <div class="absolute bottom-20 right-1/4 w-96 h-96 bg-purple-500/20 rounded-full blur-[128px]"></div>
  
  <div class="container mx-auto px-4 relative z-10">
    <div class="max-w-7xl mx-auto">
      <h2 class="text-4xl md:text-6xl font-bold text-center mb-6">
        <span class="bg-clip-text text-transparent bg-gradient-to-r from-white via-blue-100 to-white">
          Transforming Ideas into Real Results
        </span>
      </h2>
      <p class="text-xl text-gray-300 text-center mb-16 max-w-3xl mx-auto leading-relaxed">
        Each project represents a founder's vision brought to life. Through rapid development and innovative solutions, we've helped launch successful MVPs that make a real impact.
      </p>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        {#each projects as project, i}
          <div 
            class="group relative bg-[#0E1524]/50 backdrop-blur-xl rounded-2xl overflow-hidden border border-white/5 hover:border-white/10 transition-all duration-300 hover:shadow-2xl hover:shadow-blue-500/10"
          >
            <div class="relative aspect-[16/9] overflow-hidden border-b border-white/5">
              <img 
                src={project.image} 
                alt={project.title}
                class="w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-500"
              />
              <div class="absolute inset-0 bg-gradient-to-t from-[#0E1524] via-transparent to-transparent opacity-60"></div>
              <div class="absolute inset-0 bg-gradient-to-t from-[#0E1524] to-transparent group-hover:opacity-0 transition-opacity duration-500"></div>
            </div>

            <div class="p-8">
              <div class="flex flex-wrap gap-2 mb-4">
                {#each project.tags as tag}
                  <span class="px-3 py-1 text-sm bg-blue-500/10 text-blue-400 rounded-full border border-blue-500/20 font-medium backdrop-blur-sm">
                    {tag}
                  </span>
                {/each}
              </div>

              <h3 class="text-2xl font-bold mb-3 text-white group-hover:text-blue-400 transition-colors">
                {project.title}
              </h3>

              <p class="text-gray-300 mb-6 leading-relaxed">
                {project.description}
              </p>

              <div class="flex items-center gap-6 text-sm">
                <span class="flex items-center gap-2 text-emerald-400">
                  <div class="w-1.5 h-1.5 rounded-full bg-emerald-500 shadow-lg shadow-emerald-500/50"></div>
                  Successfully Launched
                </span>
                <span class="flex items-center gap-2 text-blue-400">
                  <div class="w-1.5 h-1.5 rounded-full bg-blue-500 shadow-lg shadow-blue-500/50"></div>
                  {project.deliveryTime} Delivery
                </span>
              </div>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </div>
</section>

<style>
  @keyframes subtleFloat {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-10px); }
  }

  .grid > div {
    animation: subtleFloat 20s ease-in-out infinite;
    animation-delay: calc(var(--i) * -4s);
  }
</style>
