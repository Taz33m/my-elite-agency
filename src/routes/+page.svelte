<script>
    import { onMount } from 'svelte';
    import { fade, fly } from 'svelte/transition';
    import { ArrowRight, Brain, Zap, Layers, Code, Rocket, CheckCircle, Linkedin, Twitter, Check, Clock, Shield, Lightbulb, Clapperboard, ChefHat } from 'lucide-svelte';
    import ProjectShowcase from '../components/ProjectShowcase.svelte';
    import PremiumPricing from '../components/PremiumPricing.svelte';
    import FoundersSection from '../components/FoundersSection.svelte';
    import FinalCTA from '../components/FinalCTA.svelte';
  
    let scrollY;
    let innerHeight;
  
    onMount(() => {
      const updateScroll = () => {
        scrollY = window.scrollY;
        innerHeight = window.innerHeight;
      };
      window.addEventListener('scroll', updateScroll);
      updateScroll();
      return () => window.removeEventListener('scroll', updateScroll);
    });
  
    const projects = [
      {
        title: "Think.ai",
        tags: ["AI", "EdTech", "Study Companion", "PDF/Video Analysis"],
        description: "An intelligent study companion that transforms how students learn. Leveraging advanced AI to analyze PDFs and videos, providing personalized insights and interactive learning experiences.",
        image: "/project1.png"
      },
      {
        title: "Plaiful",
        tags: ["AI", "Study Material/Quiz Generation", "EdTech"],
        description: "Revolutionary quiz generation platform powered by GPT-4. Enables educators to instantly create engaging assessments from any learning material, saving hours of preparation time.",
        image: "/project2.png"
      },
      {
        title: "GoodSupplements",
        tags: ["E-commerce", "Health", "Subscription"],
        description: "Premium e-commerce platform connecting health enthusiasts with verified supplements. Features AI-powered recommendations and subscription management for optimal wellness journeys.",
        image: "/project3.png"
      },
      {
        title: "OutfitPro",
        tags: ["B2B", "Retail", "Management"],
        description: "Enterprise-grade inventory management system for modern retailers. Streamlines operations with predictive analytics and real-time insights, boosting efficiency by 40%.",
        image: "/project4.png"
      }
    ];
  
    const pricingPlans = [
      {
        name: "MVP Development Package",
        price: "$2497",
        period: "starting at",
        description: "Special rates for waitlist members.",
        features: [
          "Complete MVP development in 2-3 weeks",
          "Web application/ Mobile App",
          "Modern, scalable tech stack",
          "Seamless integrations (payments, auth, etc.)",
          "30 days of free maintenance",
          "Personalized, founder-led development",
          "Regular updates and transparent process"
        ],
        cta: "Book a Meeting",
        popular: true,
        oneTime: true
      },
      {
        name: "Growth Retainer Package",
        price: "$2997",
        period: "/month",
        description: "No commitment, cancel anytime",
        features: [
          "60 hours of development time per month",
          "Flexible hours allocation",
          "Weekly strategy calls",
          "Priority feature development",
          "Continuous maintenance & optimization",
          "Same-day emergency support"
        ],
        cta: "Book a Meeting",
        popular: false,
        oneTime: false
      }
    ];
  </script>
  
    <section class="relative py-24 overflow-hidden" id="final-cta">
      <!-- Background Effects -->
      <div class="absolute inset-0 bg-gradient-to-b from-gray-900 to-black"></div>
      <div class="absolute inset-0 opacity-30">
        <div class="absolute inset-0 bg-[linear-gradient(to_right,#4f4f4f2e_1px,transparent_1px),linear-gradient(to_bottom,#4f4f4f2e_1px,transparent_1px)] bg-[size:14px_24px]"></div>
      </div>
      <div class="absolute left-0 right-0 top-0 h-px bg-gradient-to-r from-transparent via-blue-500/50 to-transparent"></div>

      <!-- Main Content -->
      <div class="container mx-auto px-4 relative z-10">
        <div class="max-w-4xl mx-auto text-center">
          <!-- Urgency Badge -->
          <div 
            in:fly="{{ y: 20, duration: 600 }}"
            class="inline-flex items-center gap-2 bg-white/10 backdrop-blur-sm border border-white/10 rounded-full px-4 py-2 mb-8"
          >
            <div class="flex items-center gap-1.5">
              <div class="w-2 h-2 rounded-full bg-red-500 animate-pulse"></div>
              <span class="text-red-400 text-sm font-medium">Only 2 spots left for November</span>
            </div>
          </div>

          <!-- Main Heading -->
          <h2
            in:fly="{{ y: 20, duration: 600, delay: 100 }}"
            class="text-4xl md:text-6xl font-bold mb-6 bg-clip-text text-transparent bg-gradient-to-r from-white via-blue-100 to-white"
          >
            Ready to Transform Your Idea Into Reality?
          </h2>

          <!-- Value Proposition -->
          <p
            in:fly="{{ y: 20, duration: 600, delay: 200 }}"
            class="text-xl text-gray-400 mb-8"
          >
            Join successful founders who launched their MVPs in weeks, not months.
          </p>

          <!-- Social Proof Stats -->
          <div
            in:fly="{{ y: 20, duration: 600, delay: 300 }}"
            class="grid grid-cols-2 md:grid-cols-4 gap-6 mb-12"
          >
            {#each [
              { number: '50+', label: 'Projects Launched' },
              { number: '2-3', label: 'Weeks Average Delivery' },
              { number: '98%', label: 'Client Satisfaction' },
              { number: '24/7', label: 'Support Available' }
            ] as stat}
              <div class="p-4 rounded-xl bg-white/5 backdrop-blur-sm border border-white/10">
                <div class="text-3xl font-bold text-white mb-1">{stat.number}</div>
                <div class="text-sm text-gray-400">{stat.label}</div>
              </div>
            {/each}
          </div>

          <!-- CTA Buttons -->
          <div
            in:fly="{{ y: 20, duration: 600, delay: 400 }}"
            class="flex flex-col sm:flex-row gap-4 justify-center items-center mb-12"
          >
            <button 
              on:click={() => window.open('https://cal.com/tazeem', '_blank')}
              class="group relative px-8 py-4 rounded-xl text-white flex items-center justify-center overflow-hidden min-w-[200px] transition-transform duration-300 hover:scale-105"
            >
              <div class="absolute inset-0 bg-gradient-to-r from-blue-600 to-cyan-500"></div>
              <div class="absolute inset-0 opacity-0 group-hover:opacity-20 transition-opacity duration-500 bg-[radial-gradient(circle_at_50%_50%,rgba(255,255,255,0.4),transparent_75%)]"></div>
              <div class="absolute inset-0 opacity-0 group-hover:opacity-100 transition-opacity duration-300 bg-[linear-gradient(45deg,transparent_25%,rgba(255,255,255,0.2)_50%,transparent_75%)] bg-[length:250%_250%] animate-shimmer"></div>
              <span class="relative z-10 flex items-center font-medium">
                Book Your Spot <ArrowRight class="ml-2 w-5 h-5 transition-transform duration-300 group-hover:translate-x-1" />
              </span>
            </button>
            <a 
              href="#pricing"
              class="text-gray-400 hover:text-white transition-colors flex items-center gap-2 group"
            >
              View Pricing Details <ArrowRight class="w-4 h-4 transition-transform duration-300 group-hover:translate-x-1" />
            </a>
          </div>

          <!-- Trust Badges -->
          <div
            in:fly="{{ y: 20, duration: 600, delay: 500 }}"
            class="flex flex-wrap justify-center items-center gap-8"
          >
            {#each ['No commitment required', 'Money-back guarantee', 'Transparent pricing', 'Dedicated support'] as badge}
              <div class="flex items-center gap-2 text-sm text-gray-400">
                <CheckCircle class="w-5 h-5 text-blue-500" />
                <span>{badge}</span>
              </div>
            {/each}
          </div>

          <!-- Timeline Component -->
          <div class="flex justify-center my-12">
            <div class="bg-zinc-950/50 backdrop-blur-lg h-[400px] w-[850px] rounded-lg relative group flex flex-col p-4 overflow-hidden">
              <div class="flex-grow w-full relative overflow-hidden z-0">
                <div class="absolute z-0 left-0 w-full h-full flex">
                  <div class="content-scroll absolute left-0 right-0">
                    <div class="fixed left-6 w-[1px] h-[calc(100%-153px)] bg-zinc-600/40"></div>
                    <div class="pl-16">
                      {#each [
                        {
                          title: "CyberTrain",
                          tags: ["Cybersecurity", "Education", "Training", "Enterprise"],
                          description: "Interactive cybersecurity training platform that simulates real-world scenarios. Features hands-on exercises, threat detection modules, and personalized learning paths for enterprise security teams.",
                          icon: Shield,
                          deliveryTime: "1 Week"
                        },
                        {
                          title: "Nexxeaves",
                          tags: ["AI", "Startup Ideas", "Innovation", "Market Analysis"],
                          description: "AI-powered startup ideation platform that analyzes market trends, identifies opportunities, and generates viable business concepts with detailed market validation and feasibility analysis.",
                          icon: Lightbulb,
                          deliveryTime: "3 Days"
                        },
                        {
                          title: "Popcorn Pal",
                          tags: ["Social", "Movies", "Networking", "Dating"],
                          description: "Innovative social platform that connects people through their movie preferences, enabling meaningful relationships based on shared cinematic interests and viewing habits.",
                          icon: Clapperboard,
                          deliveryTime: "2-3 Weeks"
                        },
                        {
                          title: "REGAI",
                          tags: ["AI", "Culinary", "Recipe Generation", "Food"],
                          description: "Advanced culinary AI that creates unique recipes, suggests ingredient pairings, and provides personalized cooking instructions based on available ingredients and dietary preferences.",
                          icon: ChefHat,
                          deliveryTime: "1 Day"
                        }
                      ] as project, i}
                        <div class="h-[304px] flex items-center justify-center">
                          <div class="w-full mr-6 bg-[#070709]/80 backdrop-blur-sm rounded-md border-zinc-600/40 border flex flex-col p-3 relative z-30 isolate">
                            <div class="absolute -left-[44px] top-1/2 -translate-y-1/2 h-[1px] bg-zinc-600 w-[44px] opacity-70"></div>
                            <div class="absolute -left-[45px] top-1/2 -translate-y-1/2 h-[10px] w-[10px] bg-blue-600 border-zinc-600 border rounded-full"></div>
                            <div class="flex flex-col space-y-3">
                              <div class="flex items-center justify-between">
                                <div class="flex items-center space-x-3">
                                  <div class="border border-zinc-600/40 w-12 h-12 rounded-md relative overflow-hidden flex items-center justify-center bg-blue-500/10">
                                    <div class="absolute top-3/4 right-0 -translate-y-1/2 w-5 h-5 bg-blue-600 blur-[13px]"></div>
                                    <svelte:component 
                                      this={project.icon} 
                                      class="w-6 h-6 text-blue-400"
                                    />
                                  </div>
                                  <div class="flex flex-col justify-start items-start">
                                    <div class="text-zinc-100 font-medium">{project.title}</div>
                                    <div class="text-zinc-400 text-sm">Delivery: {project.deliveryTime}</div>
                                  </div>
                                </div>
                                <div class="text-zinc-400 italic text-sm">{project.tags.join(', ')}</div>
                              </div>
                              <div class="flex items-center space-x-2 border-l-2 border-blue-600/30 pl-3">
                                <div class="text-sm italic bg-clip-text text-transparent bg-gradient-to-b from-white via-gray-300 to-gray-400">
                                  {project.description}
                                </div>
                              </div>
                            </div>
                          </div>
                        </div>
                      {/each}
                    </div>
                  </div>
                </div>
                <div class="absolute left-0 right-0 top-0 h-12 bg-gradient-to-b from-zinc-950 to-transparent z-20"></div>
                <div class="absolute left-0 right-0 bottom-0 h-12 bg-gradient-to-t from-zinc-950 to-transparent z-20"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  
    <ProjectShowcase />
    <PremiumPricing />
    <FoundersSection />
    <FinalCTA />
  
    <div
      class="fixed bottom-8 left-0 right-0 z-50"
      in:fly="{{ y: 50, duration: 500 }}"
    >
      <div class="container mx-auto px-4">
        <nav class="flex justify-center items-center bg-gray-900/50 backdrop-blur-lg rounded-full px-6 py-3 max-w-fit mx-auto">
          <div class="flex items-center gap-8">
            <!-- Add Logo -->
            <img 
              src="/logo.png" 
              alt="Company Logo" 
              class="h-8 w-auto mr-4"
            />
            
            {#each ['How it works', 'Pricing', 'Work', 'Founder'] as item}
              <a 
                href="#{item.toLowerCase().replace(' ', '-')}" 
                class="text-gray-400 hover:text-white transition-colors"
              >
                {item}
              </a>
            {/each}
            <button 
              on:click={() => window.open('https://cal.com/tazeem', '_blank')}
              class="bg-white text-black hover:bg-gray-100 px-4 py-2 rounded-full transition-colors duration-300"
            >
              Book a Meeting <ArrowRight class="inline-block ml-2 w-4 h-4" />
            </button>
          </div>
        </nav>
      </div>
    </div>
  
  <style>
    :global(html) {
      scroll-behavior: smooth;
    }

    @keyframes spin {
      from {
        transform: translateX(-50%) rotate(0deg);
      }
      to {
        transform: translateX(-50%) rotate(360deg);
      }
    }

    .content-scroll {
      animation: scroll 20s ease-in-out infinite;
    }

    @keyframes scroll {
      0%, 12% { transform: translateY(0); }
      20%, 37% { transform: translateY(-304px); }
      45%, 62% { transform: translateY(-608px); }
      70%, 87% { transform: translateY(-912px); }
      95%, 100% { transform: translateY(0); }
    }

    :global(.glass) {
      background: rgba(255, 255, 255, 0.05);
      backdrop-filter: blur(10px);
      -webkit-backdrop-filter: blur(10px);
      border: 1px solid rgba(255, 255, 255, 0.05);
    }

    :global(.glass-dark) {
      background: rgba(0, 0, 0, 0.3);
      backdrop-filter: blur(10px);
      -webkit-backdrop-filter: blur(10px);
      border: 1px solid rgba(255, 255, 255, 0.05);
    }

    @keyframes shimmer {
      0% {
        background-position: 200% 0;
      }
      100% {
        background-position: -200% 0;
      }
    }

    .animate-shimmer {
      animation: shimmer 3s linear infinite;
    }
  </style>