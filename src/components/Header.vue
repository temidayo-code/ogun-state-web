<template>
  <div class="header-wrapper" :class="{ 'nav-hidden': isHidden }">
    <div class="container-fluid bg-white p-0" style="width: 90%">
      <div class="header-container px-3">
        <nav class="navbar navbar-expand-md bg-body-tertiary p-0">
          <div class="container-fluid py-3">
            <a class="navbar-brand d-flex p-0" href="#">
              <div>
                <img
                  src="../assets/images/logo.png"
                  alt="Bootstrap"
                  class="logo-img"
                />
              </div>
              <div
                class="logo-text ms-2 d-none d-md-block"
                style="color: #2c9960"
              >
                Ogun State <br />
                Government
              </div>
            </a>
            <button
              class="navbar-toggler"
              type="button"
              data-bs-toggle="collapse"
              data-bs-target="#navbarSupportedContent"
              aria-controls="navbarSupportedContent"
              aria-expanded="false"
              aria-label="Toggle navigation"
            >
              <span class="navbar-toggler-icon"></span>
            </button>
            <div
              class="collapse navbar-collapse justify-content-center"
              id="navbarSupportedContent"
            >
              <ul class="navbar-nav mb-2 mb-lg-0">
                <li class="nav-item">
                  <a class="nav-link me-3 active" aria-current="page" href="#"
                    >Home</a
                  >
                </li>
                <li class="nav-item dropdown">
                  <a
                    class="nav-link me-3 dropdown-toggle"
                    href="#"
                    role="button"
                    data-bs-toggle="dropdown"
                    aria-expanded="false"
                  >
                    Service
                  </a>
                  <ul class="dropdown-menu">
                    <li><a class="dropdown-item" href="#">Action</a></li>
                    <li>
                      <a class="dropdown-item" href="#">Another action</a>
                    </li>
                    <li><hr class="dropdown-divider" /></li>
                    <li>
                      <a class="dropdown-item" href="#">Something else here</a>
                    </li>
                  </ul>
                </li>
                <li class="nav-item">
                  <a class="nav-link me-3" href="#">About</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link me-3" href="#">News</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#">Contact</a>
                </li>

                <button class="quick-link-btn d-md-none">Quick Link</button>
              </ul>
            </div>
            <button class="quick-link-btn d-none d-md-block">Quick Link</button>
          </div>
        </nav>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isHidden: false,
      lastScrollPosition: 0,
      scrollTimeout: null,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },

  methods: {
    handleScroll() {
      // Clear the existing timeout
      if (this.scrollTimeout) {
        clearTimeout(this.scrollTimeout);
      }

      // Hide navbar while scrolling
      const currentScrollPosition = window.pageYOffset;
      if (currentScrollPosition > this.lastScrollPosition) {
        this.isHidden = true;
      } else if (currentScrollPosition < this.lastScrollPosition) {
        this.isHidden = true;
      }
      this.lastScrollPosition = currentScrollPosition;

      // Show navbar after scrolling stops (after 150ms of no scroll)
      this.scrollTimeout = setTimeout(() => {
        this.isHidden = false;
      }, 500);
    },
  },
};
</script>

<style scoped>
.quick-link-btn {
  background-color: #006400;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 25px;
  transition: background-color 0.3s ease;
}

.quick-link-btn:hover {
  scale: 1.05;
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
}

.navbar-collapse {
  flex-grow: 2;
}

.header-wrapper {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  transition: transform 0.3s ease-in-out;
}

.nav-hidden {
  transform: translateY(-100%);
}

.nav-link {
  position: relative;
  padding: 1.5rem 1rem !important;
  color: #333;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: #006400;
}

.nav-link::before {
  content: "";
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 0;
  height: 3px;
  background-color: #006400;
  transition: all 0.3s ease;
  transform: translateX(-50%);
}

.nav-link:hover::before,
.nav-link.active::before {
  width: 100%;
  height: 3px;
  background-color: #006400 !important;
}

.nav-link.active {
  font-weight: 700;
  color: #006400 !important;
}

.container-fluid {
  padding: 0 !important;
}

.navbar {
  padding: 0 !important;
}

.nav-link {
  color: #333;
  transition: color 0.3s ease;
}

.logo-img {
  width: 50px;
  margin: 6px 0;
}

@media (min-width: 768px) {
  .logo-img {
    width: 70px;
    margin: 0;
  }
}
</style>
