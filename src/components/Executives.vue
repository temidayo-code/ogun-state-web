<template>
  <div class="executives-container">
    <div class="container-fluid" style="width: 90%">
      <!-- Header Section -->
      <div class="header-section">
        <h2 class="section-title">Meet Our Executives</h2>
        <button class="view-more-btn">
          View More
          <i class="fas fa-arrow-right ms-2"></i>
        </button>
      </div>

      <!-- Images Grid -->
      <div class="executives-grid">
        <div class="executive-card">
          <img src="@/assets/images/img-meet-1.png" alt="Governor" />
          <div class="info-overlay">
            <h3 class="name">Dapo Abiodun</h3>
            <p class="position">State Governor</p>
          </div>
        </div>

        <div class="executive-card">
          <img src="@/assets/images/img-meet-2.png" alt="Deputy Governor" />
          <div class="info-overlay">
            <h3 class="name">Noimot Salako</h3>
            <p class="position">Deputy Governor</p>
          </div>
        </div>

        <div class="executive-card">
          <img src="@/assets/images/img-meet-3.png" alt="Commissioner" />
          <div class="info-overlay">
            <h3 class="name">Prof. Arigbabu</h3>
            <p class="position">Com. Of Education</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.executives-container {
  padding: 4rem 0;
}

.header-section {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 3rem;
}

.section-title {
  font-size: 32px;
  font-weight: 700;
  margin: 0;
}

.view-more-btn {
  background: transparent;
  border: none;
  color: #006400;
  font-weight: 600;
  display: flex;
  align-items: center;
  transition: transform 0.3s ease;
}

.view-more-btn:hover {
  transform: translateX(5px);
}

.executives-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  position: relative;
}

.executive-card {
  position: relative;
  overflow: hidden;
  border-radius: 8px;
  aspect-ratio: 3/4;
}

.executive-card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.info-overlay {
  position: absolute;
  bottom: -100%;
  left: -100%;
  background: rgba(255, 255, 255, 0.95);
  padding: 1.5rem;
  border-radius: 8px;
  transition: all 0.3s ease;
}

.executive-card:hover .info-overlay {
  bottom: 0;
  left: 0;
}

.name {
  font-size: 24px;
  font-weight: 700;
  margin: 0;
  color: #000;
}

.position {
  font-size: 24px;
  font-weight: 400;
  margin: 0.5rem 0 0;
  color: #333;
}

/* Tablet Breakpoint */
@media (max-width: 992px) {
  .executives-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }
}

/* Mobile Breakpoint */
@media (max-width: 768px) {
  .executives-container {
    padding: 2rem 0;
  }

  .executives-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .executive-card {
    aspect-ratio: 2/3;
  }

  .info-overlay {
    padding: 1rem;
  }

  .name {
    font-size: 20px;
  }

  .position {
    font-size: 18px;
  }

  .header-section {
    margin-bottom: 2rem;
  }
}
</style>
