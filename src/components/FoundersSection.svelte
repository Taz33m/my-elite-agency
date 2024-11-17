<script>
  import { fly } from 'svelte/transition';
  import { Linkedin, Twitter, Github, Mail } from 'lucide-svelte';

  const founders = [
    {
      name: "Tazeem",
      role: "Founder & CEO",
      image: "/Founder1.jpeg",
      bio: "Full-stack developer with expertise in AI and scalable architectures. Previously built and scaled multiple successful startups. Passionate about leveraging cutting-edge technology to solve complex business challenges. Experienced in leading technical teams and delivering high-impact solutions.",
      achievements: ["4+ Years Experience", "50+ Projects Delivered", "AI/ML Expert"],
      skills: ["Full-Stack Development", "System Architecture", "AI Integration", "Team Leadership"],
      social: {
        linkedin: "https://linkedin.com/in/tazeemm",
      }
    },
    {
      name: "Nafis",
      role: "Co-Founder & COO",
      image: "/Founder2.jpeg",
      bio: "Product strategist and technical architect with a focus on AI/ML solutions. Specialized in building scalable products that deliver exceptional user experiences. Expert in modern tech stacks and cloud architecture.",
      achievements: ["Entrepreneur", "3x Public Speaker", "ML/AI Specialist"],
      skills: ["Product Strategy", "Full-Stack Development", "ML/AI Development", "Technical Leadership"],
      social: {
        linkedin: "https://linkedin.com/in/nafis-mahim-a206ab319/",
      }
    }
  ];
</script>

<section class="relative py-24 overflow-hidden" id="founder">
  <div class="absolute inset-0 bg-[#0A0F1C]"></div>
  
  <!-- Enhanced Background Effects -->
  <div class="absolute inset-0 opacity-30">
    <div class="absolute inset-0 bg-gradient-to-br from-blue-500/10 via-transparent to-purple-500/10"></div>
    <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_center,rgba(14,20,36,0)_0%,rgba(14,20,36,1)_100%)]"></div>
  </div>
  
  <!-- Graph Background -->
  <div class="absolute inset-0 opacity-10">
    <div class="absolute inset-0 bg-[linear-gradient(to_right,#4f4f4f2e_1px,transparent_1px),linear-gradient(to_bottom,#4f4f4f2e_1px,transparent_1px)] bg-[size:24px_24px]"></div>
  </div>
  
  <!-- Glow Effects -->
  <div class="absolute top-20 left-1/4 w-96 h-96 bg-blue-500/20 rounded-full blur-[128px]"></div>
  <div class="absolute bottom-20 right-1/4 w-96 h-96 bg-purple-500/20 rounded-full blur-[128px]"></div>

  <div class="container mx-auto px-4 relative z-10">
    <div class="max-w-7xl mx-auto">
      <h2 class="text-4xl md:text-6xl font-bold text-center mb-6">
        <span class="bg-clip-text text-transparent bg-gradient-to-r from-white via-blue-100 to-white">
          Meet Your Development Partners
        </span>
      </h2>
      <p class="text-xl text-gray-300 text-center mb-16 max-w-3xl mx-auto leading-relaxed">
        Combining technical expertise with entrepreneurial experience to deliver exceptional results. We're not just developers – we're your partners in success.
      </p>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-12 max-w-6xl mx-auto">
        {#each founders as founder}
          <div 
            in:fly={{ y: 20, duration: 600 }}
            class="group relative h-full"
          >
            <div class="absolute -inset-[1px] bg-gradient-to-r from-blue-500 to-purple-500 rounded-2xl opacity-50 group-hover:opacity-100 blur transition-all duration-500"></div>
            <div class="relative h-full bg-[#0E1524]/50 backdrop-blur-xl rounded-2xl p-8 border border-white/5 hover:border-white/10 transition-all duration-300">
              <div class="flex flex-col items-center h-full">
                <!-- Profile Image -->
                <div class="relative mb-6 group-hover:scale-105 transition-transform duration-500">
                  <div class="absolute -inset-1 bg-gradient-to-r from-blue-500 to-purple-500 rounded-full blur opacity-75"></div>
                  <img
                    src={founder.image}
                    alt={founder.name}
                    class="relative w-40 h-40 rounded-full object-cover border-2 border-white/10"
                  />
                </div>

                <!-- Bio Section -->
                <div class="text-center mb-6">
                  <h3 class="text-2xl font-bold text-white mb-2">{founder.name}</h3>
                  <p class="text-blue-400 font-medium mb-4">{founder.role}</p>
                  <p class="text-gray-300 leading-relaxed mb-6">{founder.bio}</p>
                </div>

                <!-- Achievements -->
                <div class="flex flex-wrap justify-center gap-3 mb-6">
                  {#each founder.achievements as achievement}
                    <span class="px-3 py-1 text-sm bg-blue-500/10 text-blue-400 rounded-full border border-blue-500/20">
                      {achievement}
                    </span>
                  {/each}
                </div>

                <!-- Skills -->
                <div class="w-full grid grid-cols-2 gap-3 mb-8">
                  {#each founder.skills as skill}
                    <div class="flex items-center gap-2 text-gray-300">
                      <div class="w-1.5 h-1.5 rounded-full bg-blue-500"></div>
                      <span class="text-sm">{skill}</span>
                    </div>
                  {/each}
                </div>

                <!-- Social Links -->
                <div class="mt-auto">
                  <a
                    href={founder.social.linkedin}
                    target="_blank"
                    rel="noopener noreferrer"
                    class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white/5 hover:bg-white/10 text-gray-400 hover:text-white transition-all duration-300"
                  >
                    <Linkedin class="w-5 h-5" />
                    <span>Connect on LinkedIn</span>
                  </a>
                </div>
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
