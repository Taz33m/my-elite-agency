<script>
  import { fly } from 'svelte/transition';
  import { ArrowRight, Rocket, Shield, Clock } from 'lucide-svelte';
</script>

<section class="relative py-32 overflow-hidden">
  <div class="absolute inset-0 bg-gradient-to-b from-gray-900 to-black"></div>
  <div class="absolute inset-0 opacity-30">
    <div class="absolute inset-0 bg-[linear-gradient(to_right,#4f4f4f2e_1px,transparent_1px),linear-gradient(to_bottom,#4f4f4f2e_1px,transparent_1px)] bg-[size:14px_24px]"></div>
  </div>
  <div class="absolute left-0 right-0 top-0 h-px bg-gradient-to-r from-transparent via-blue-500/50 to-transparent"></div>

  <div class="container mx-auto px-4 relative z-10">
    <div class="max-w-4xl mx-auto text-center">
      <h2 
        in:fly={{ y: 20, duration: 600 }}
        class="text-4xl md:text-6xl font-bold mb-6"
      >
        <span class="bg-clip-text text-transparent bg-gradient-to-r from-white via-blue-100 to-white">
          Ready to Launch Your MVP in Weeks?
        </span>
      </h2>
      
      <p 
        in:fly={{ y: 20, duration: 600, delay: 100 }}
        class="text-xl text-gray-300 mb-12 leading-relaxed"
      >
        Join successful founders who transformed their ideas into reality. Book a free consultation and let's discuss how we can bring your vision to life.
      </p>

      <div 
        in:fly={{ y: 20, duration: 600, delay: 200 }}
        class="flex flex-col items-center gap-8"
      >
        <button 
          on:click={() => window.open('https://cal.com/tazeem', '_blank')}
          class="group relative inline-flex items-center gap-2 px-8 py-4 bg-white text-black rounded-full hover:bg-gray-100 transition-all duration-300 transform hover:scale-[1.02]"
        >
          <span class="font-medium">Schedule Free Consultation</span>
          <ArrowRight class="w-5 h-5 group-hover:translate-x-1 transition-transform duration-300" />
        </button>

        <div class="flex flex-wrap justify-center gap-8 text-sm text-gray-400">
          <div class="flex items-center gap-2">
            <Clock class="w-4 h-4 text-blue-400" />
            <span>15-min Discovery Call</span>
          </div>
          <div class="flex items-center gap-2">
            <Rocket class="w-4 h-4 text-blue-400" />
            <span>Launch in 1-2 Weeks</span>
          </div>
          <div class="flex items-center gap-2">
            <Shield class="w-4 h-4 text-blue-400" />
            <span>Risk-Free Consultation</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
