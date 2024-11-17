<script>
  const packages = [
    {
      name: "MVP Development Package",
      price: "2,297",
      period: "starting at",
      description: "Launch your MVP in weeks, not months. Perfect for founders ready to validate their ideas.",
      features: [
        "Complete MVP development in 1-2 weeks",
        "Web application or Mobile App",
        "Modern, scalable tech stack",
        "Seamless integrations (payments, auth, etc.)",
        "30 days of free maintenance",
        "Personalized, founder-led development",
        "Regular updates and transparent process"
      ],
      cta: "Schedule Consultation",
      oneTime: true,
      highlighted: true
    },
    {
      name: "Growth Retainer Package",
      price: "2,997",
      period: "/month",
      description: "Dedicated development support to scale your product. Cancel anytime.",
      features: [
        "60 hours of development time monthly",
        "Priority feature development",
        "Weekly strategy calls",
        "Technical architecture optimization",
        "Continuous maintenance & updates",
        "24/7 emergency support",
        "Flexible hours allocation"
      ],
      cta: "Book a Call",
      oneTime: false,
      highlighted: false
    }
  ];
</script>

<section class="relative py-24 overflow-hidden" id="pricing">
  <div class="absolute inset-0 bg-[#0A0F1C]"></div>
  
  <!-- Background effects -->
  <div class="absolute inset-0 opacity-30">
    <div class="absolute inset-0 bg-gradient-to-br from-blue-500/10 via-transparent to-purple-500/10"></div>
    <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_center,rgba(14,20,36,0)_0%,rgba(14,20,36,1)_100%)]"></div>
  </div>

  <div class="container mx-auto px-4 relative z-10">
    <div class="max-w-7xl mx-auto">
      <h2 class="text-4xl md:text-6xl font-bold text-center mb-6">
        <span class="bg-clip-text text-transparent bg-gradient-to-r from-white via-blue-100 to-white">
          Transparent Pricing, Exceptional Value
        </span>
      </h2>
      <p class="text-xl text-gray-300 text-center mb-16 max-w-3xl mx-auto">
        Choose the perfect package for your startup's needs. From rapid MVP development to ongoing growth support.
      </p>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 max-w-6xl mx-auto">
        {#each packages as pkg}
          <div class="relative group">
            {#if pkg.highlighted}
              <div class="absolute -inset-[1px] bg-gradient-to-r from-blue-500 to-purple-500 rounded-2xl blur group-hover:blur-md transition-all"></div>
            {/if}
            <div class="relative h-full bg-[#0E1524]/50 backdrop-blur-xl rounded-2xl p-8 border border-white/5 hover:border-white/10 transition-all duration-300 hover:shadow-2xl hover:shadow-blue-500/10">
              <!-- Package Header -->
              <div class="mb-8">
                <h3 class="text-2xl font-bold mb-2 text-white">{pkg.name}</h3>
                <div class="flex items-baseline gap-2 mb-3">
                  <span class="text-4xl font-bold text-white">${pkg.price}</span>
                  <span class="text-gray-400">{pkg.period}</span>
                </div>
                <p class="text-gray-300">{pkg.description}</p>
              </div>
              
              <!-- Features List -->
              <div class="space-y-4 mb-8">
                {#each pkg.features as feature}
                  <div class="flex items-start gap-3">
                    <div class="mt-1 w-5 h-5 rounded-full bg-blue-500/20 flex items-center justify-center flex-shrink-0">
                      <div class="w-2 h-2 rounded-full bg-blue-500"></div>
                    </div>
                    <span class="text-gray-300">{feature}</span>
                  </div>
                {/each}
              </div>

              <!-- CTA Button -->
              <a href="https://cal.com/tazeem" class="w-full py-4 px-6 rounded-xl text-white font-semibold transition-all duration-300 shadow-lg 
                {pkg.highlighted ? 
                  'bg-gradient-to-r from-blue-500 to-blue-600 hover:from-blue-600 hover:to-blue-700 shadow-blue-500/25 hover:shadow-blue-500/40' : 
                  'bg-white/10 hover:bg-white/20 shadow-white/5 hover:shadow-white/10'}">
                {pkg.cta}
              </a>

              <!-- Package Type Badge -->
              <div class="absolute top-4 right-4">
                <span class="px-3 py-1 rounded-full text-xs font-medium bg-white/10 text-gray-300">
                  {pkg.oneTime ? 'One-time' : 'Monthly'}
                </span>
              </div>
            </div>
          </div>
        {/each}
      </div>

      <!-- Trust Badges -->
      <div class="mt-16 flex flex-wrap justify-center gap-8">
        {#each ['No hidden fees', 'Priority support'] as badge}
          <div class="flex items-center gap-2 text-sm text-gray-400">
            <div class="w-4 h-4 rounded-full bg-blue-500/20 flex items-center justify-center">
              <div class="w-1.5 h-1.5 rounded-full bg-blue-500"></div>
            </div>
            <span>{badge}</span>
          </div>
        {/each}
      </div>
    </div>
  </div>
</section>
