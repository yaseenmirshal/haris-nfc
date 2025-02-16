

<script setup>
import { onMounted } from 'vue';

onMounted(() => {
  const scrollers = document.querySelectorAll(".scroller");

  // If a user hasn't opted in for reduced motion, then we add the animation
  if (!window.matchMedia("(prefers-reduced-motion: reduce)").matches) {
    addAnimation(scrollers);
  }

  function addAnimation(scrollers) {
    scrollers.forEach((scroller) => {
      // add data-animated="true" to every `.scroller` on the page
      scroller.setAttribute("data-animated", true);

      // Make an array from the elements within `.scroller-inner`
      const scrollerInner = scroller.querySelector(".scroller__inner");
      const scrollerContent = Array.from(scrollerInner.children);

      // For each item in the array, clone it
      // add aria-hidden to it
      // add it into the `.scroller-inner`
      scrollerContent.forEach((item) => {
        const duplicatedItem = item.cloneNode(true);
        duplicatedItem.setAttribute("aria-hidden", true);
        scrollerInner.appendChild(duplicatedItem);
      });
    });
  }
});
</script>

<template>
  <section id="about" class="about-area">
    <div class="container">
      <div class="row">
       <!-- START ABOUT IMAGE DESIGN AREA -->
<div class="col-lg-4">
  <div class="about-image-part wow fadeInUp delay-0-3s text-center">
    <img src="~/assets/images/about/harishsprofile.png" alt="About Me" class="mb-4" />
    <h2>Haris Backer</h2>
    <p>I am CEO of Artifitia Software Company</p>
    <div class="about-social text-center mt-4">
      <ul class="flex justify-center space-x-4">
        <li>
          <a href="http://wa.me/971552255763" target="_blank">
            <i class="ri-whatsapp-fill text-xl"></i>
          </a>
        </li>
        <li>
          <a href="https://www.instagram.com/artifitiasolutions/" target="_blank">
            <i class="ri-instagram-line text-xl"></i>
          </a>
        </li>
        <li>
          <a href="https://www.facebook.com/profile.php?id=100087994926383" target="_blank">
            <i class="ri-facebook-circle-fill text-xl"></i>
          </a>
        </li>
        <li>
          <a href="https://www.linkedin.com/in/artifitia-solutions-047648257/" target="_blank">
            <i class="ri-linkedin-fill text-xl"></i>
          </a>
        </li>
      </ul>
    </div>
  </div>
</div>

        <div class="col-lg-8">
          <div class="about-content-part wow fadeInUp delay-0-2s">
            <p>Hello There!</p>
            <h2>
              {{"I'm"}} Haris Backer, Cheif Exicutive Officer at Artifitia Software Company
            </h2>
            <div class="adress-field">
              <ul>
                <li><i class="ri-circle-fill"></i>Available for Freelancing</li>
              </ul>
            </div>
            <div class="hero-btns">
              <NuxtLink to="/contact" class="theme-btn">Download CV <i class="ri-download-line"></i></NuxtLink>
            </div>
          </div>
          <div class="about-content-part-bottom wow fadeInUp delay-0-2s">
            <h2>Company I Worked With</h2>
            <div class="company-list">
              <div class="scroller" data-direction="left" data-speed="slow">
                <div class="scroller__inner">
                  <img src="~/assets/images/client-logos/partner1.png" alt="" />
                  <img src="~/assets/images/client-logos/partner2.png" alt="" />
                  <img src="~/assets/images/client-logos/partner3.png" alt="" />
                  <img src="~/assets/images/client-logos/partner4.png" alt="" />
                  <img src="~/assets/images/client-logos/partner5.png" alt="" />
                  <img src="~/assets/images/client-logos/partner1.png" alt="" />
                </div>
              </div>
            </div>
          </div>
        </div>
        <!-- / END ABOUT TEXT DESIGN AREA -->
      </div>
    </div>
  </section>
</template>

 