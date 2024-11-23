<template>
  <div class="hero-container">
    <div
      id="heroCarousel"
      class="carousel slide carousel-fade"
      data-bs-ride="carousel"
    >
      <div class="carousel-indicators">
        <button
          type="button"
          data-bs-target="#heroCarousel"
          data-bs-slide-to="0"
          class="active"
        ></button>
        <button
          type="button"
          data-bs-target="#heroCarousel"
          data-bs-slide-to="1"
        ></button>
        <button
          type="button"
          data-bs-target="#heroCarousel"
          data-bs-slide-to="2"
        ></button>
      </div>
      <div class="carousel-inner">
        <!-- First Slide -->
        <div class="carousel-item active">
          <img
            src="@/assets/images/img-bg-hero.png"
            class="d-block w-100"
            alt="Hero Image 1"
            style="scale: 2.5; object-fit: cover"
          />
          <div class="carousel-caption">
            <div class="container-fluid" style="width: 90%">
              <div class="content-wrapper">
                <h1 class="hero-title">
                  The Gateway <br />
                  State
                </h1>
                <p class="hero-description">
                  Ogun State was created on the 3rd of February, 1976. It was
                  carved out of the old Western State of Nigeria and named after
                  the Ogun River which runs across it from North to South.
                </p>
                <button class="mda-button">Ogun State MDAs</button>
              </div>
            </div>
          </div>
        </div>

        <!-- Second Slide -->
        <div class="carousel-item">
          <img
            src="@/assets/images/img-bg-hero-2.png"
            class="d-block w-100"
            alt="Hero Image 2"
          />
          <div class="carousel-caption">
            <div class="container-fluid" style="width: 90%">
              <div class="content-wrapper">
                <h1 class="hero-title">
                  Our <br />
                  Heritage
                </h1>
                <p class="hero-description">
                  Ogun State is predominantly Yoruba, with the Yoruba language
                  serving as the lingua franca of the state. The dominant
                  religions in Ogun State are Islam and Christianity, although a
                  certain amount of traditional religion is still practiced.
                  Ogun State is noted for being the almost exclusive site of
                  Ofada rice production.
                </p>
                <button class="mda-button">Ogun State MDAs</button>
              </div>
            </div>
          </div>
        </div>

        <!-- Third Slide -->
        <div class="carousel-item">
          <img
            src="@/assets/images/img-bg-hero-3.png"
            class="d-block w-100"
            alt="Hero Image 3"
          />
          <div class="carousel-caption">
            <div class="container-fluid" style="width: 90%">
              <div class="content-wrapper">
                <h1 class="hero-title">
                  Our <br />
                  People
                </h1>
                <p class="hero-description">
                  The state is predominantly populated by the Egbas, Ijebus,
                  Yewas, Remos, and Aworis, who belong to the main Yoruba ethnic
                  group. It also includes sub-groups such as Ketu, Ikale, Ilaje,
                  Ohori, Anago, and Egun. There are also significant numbers of
                  Nigerians from other parts of the country as well as foreign
                  nationals residing in the state.
                </p>
                <button class="mda-button">Ogun State MDAs</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    // Import Bootstrap's Carousel dynamically
    import("bootstrap").then((bootstrap) => {
      const carousel = new bootstrap.Carousel(
        document.getElementById("heroCarousel"),
        {
          interval: 5000, // 5 seconds
          pause: false,
          ride: "carousel",
          wrap: true,
        }
      );
    });

    // Add animation reset on slide change
    document
      .getElementById("heroCarousel")
      .addEventListener("slide.bs.carousel", () => {
        const activeSlide = document.querySelector(".carousel-item.active");
        const elements = activeSlide.querySelectorAll(
          ".hero-title, .hero-description, .mda-button"
        );
        elements.forEach((el) => {
          el.style.animation = "none";
          el.offsetHeight; // Trigger reflow
          el.style.animation = null;
        });
      });
  },
};
</script>

<style scoped>
.hero-container {
  height: 100vh;
  overflow: hidden;
  position: relative;
  background-color: #000;
}

.carousel {
  height: 100%;
}

.carousel-item {
  height: 100vh;
  background-color: #000;
}

.carousel-item img {
  height: 100%;
  width: 100%;
  object-fit: cover;
  object-position: center;
  position: absolute;
  top: 0;
  left: 0;
}

.carousel-caption {
  top: 50%;
  transform: translateY(-50%);
  bottom: auto;
  text-align: left;
  padding: 0;
  width: 100%;
  left: 0;
  right: 0;
}

.content-wrapper {
  max-width: 600px;
  padding: 2rem 0;
}

.hero-title {
  font-size: 80px;
  font-weight: 700;
  line-height: 1.1;
  margin-bottom: 2rem;
  opacity: 0;
  transform: translateY(20px);
  animation: fadeInUp 0.8s ease forwards;
}

.hero-description {
  font-size: 1.1rem;
  line-height: 1.6;
  margin-bottom: 2rem;
  opacity: 0;
  transform: translateY(20px);
  animation: fadeInUp 0.8s ease 0.2s forwards;
}

.mda-button {
  background-color: transparent;
  color: #ffffff;
  border: 2px solid #ffffff;
  padding: 12px 24px;
  font-size: 1.1rem;
  font-weight: 600;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.3s ease;
  opacity: 0;
  transform: translateY(20px);
  animation: fadeInUp 0.8s ease 0.4s forwards;
}

.mda-button:hover {
  background-color: #ffffff;
  color: #004322;
  transform: translateY(-2px);
}

/* Animation keyframes */
@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Carousel transitions */
.carousel-item {
  transition: transform 0.6s ease-in-out;
}

.carousel .carousel-item-next,
.carousel .carousel-item-prev,
.carousel .carousel-item.active {
  display: flex;
}

/* Optional: Add fade effect */
.carousel-fade .carousel-item {
  opacity: 0;
  transition-duration: 0.6s;
  transition-property: opacity;
}

.carousel-fade .carousel-item.active,
.carousel-fade .carousel-item-next.carousel-item-start,
.carousel-fade .carousel-item-prev.carousel-item-end {
  opacity: 1;
}

.carousel-fade .active.carousel-item-start,
.carousel-fade .active.carousel-item-end {
  opacity: 0;
}

/* Large screens */
@media (min-width: 1400px) {
  .hero-title {
    font-size: 90px;
  }

  .content-wrapper {
    max-width: 800px;
  }
}

/* Medium screens */
@media (max-width: 992px) {
  .hero-title {
    font-size: 60px;
  }

  .content-wrapper {
    max-width: 500px;
    padding: 1.5rem 0;
  }

  .hero-description {
    font-size: 1rem;
  }
}

/* Tablet */
@media (max-width: 768px) {
  .hero-title {
    font-size: 48px;
    margin-bottom: 1.5rem;
  }

  .hero-description {
    font-size: 1rem;
    margin-bottom: 1.5rem;
  }

  .content-wrapper {
    padding: 1rem 0;
    max-width: 100%;
  }

  .carousel-caption {
    padding: 2rem 1rem;
  }

  .mda-button {
    padding: 10px 20px;
    font-size: 1rem;
  }
}

/* Mobile */
@media (max-width: 480px) {
  .hero-title {
    font-size: 36px;
    margin-bottom: 1rem;
  }

  .hero-description {
    font-size: 0.9rem;
    margin-bottom: 1rem;
    line-height: 1.4;
  }

  .content-wrapper {
    padding: 0.5rem 0;
  }
}

/* Small Mobile */
@media (max-width: 360px) {
  .hero-title {
    font-size: 32px;
    margin-top: 2rem ;
  }
}
</style>
