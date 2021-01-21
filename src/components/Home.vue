<template>
  <!-- Blogging Tabs -->
  <section>
    <div class="container">
      <ul class="nav nav-tabs nav-justified">
        <li class="nav-item">
          <a
            class="nav-link"
            @click.prevent="setActive('home')"
            :class="{ active: isActive('home') }"
            href="#home"
            >Home</a
          >
        </li>
        <li class="nav-item">
          <a
            class="nav-link"
            @click.prevent="setActive('profile')"
            :class="{ active: isActive('profile') }"
            href="#profile"
            >Profile</a
          >
        </li>
        <li class="nav-item">
          <a
            class="nav-link"
            @click.prevent="setActive('contact')"
            :class="{ active: isActive('contact') }"
            href="#contact"
            >Contact</a
          >
        </li>
      </ul>
      <div class="tab-content py-3" id="myTabContent">
        <div
          class="tab-pane fade"
          :class="{ 'active show': isActive('home') }"
          id="home"
        >
          Home content
        </div>
        <div
          class="tab-pane fade"
          :class="{ 'active show': isActive('profile') }"
          id="profile"
        >
          Profile content
        </div>
        <div
          class="tab-pane fade"
          :class="{ 'active show': isActive('contact') }"
          id="contact"
        >
          Contact content
        </div>
      </div>
    </div>
  </section>
  <!-- Blogging Tabs -->
  <section>
    <canvas id="myChart" title="My Skills"></canvas>
  </section>
  <!-- Skill Chart -->
  <!-- image slideshow  -->
  <section>
    <div class="ia-container">
      <figure>
        <img src="https://www.gstatic.com/webp/gallery3/1.png" alt="image01" />
        <input type="radio" name="radio-set" checked="checked" />
        <figcaption><span>True Colors</span></figcaption>

        <figure>
          <img
            src="https://www.gstatic.com/webp/gallery3/2_webp_ll.png"
            alt="image02"
          />
          <input type="radio" name="radio-set" />
          <figcaption><span>Honest Light</span></figcaption>

          <figure>
            <img
              src="https://www.gstatic.com/webp/gallery3/3_webp_ll.png"
              alt="image02"
            />
            <input type="radio" name="radio-set" />
            <figcaption><span>Honest Light</span></figcaption>

            <figure>
              <img
                src="https://www.gstatic.com/webp/gallery3/4_webp_a.png"
                alt="image02"
              />
              <input type="radio" name="radio-set" />
              <figcaption><span>Honest Light</span></figcaption>
            </figure>
          </figure>
        </figure>
      </figure>
    </div>
  </section>
  <!-- image slideshow  -->
  <!--  contact button -->
  <button id="contact-button" title="Go to top">Contact Me</button>
  <!-- contact button -->
  <!-- footer image -->
  <footer>
    <img
      src="../assets/footer.jpg"
      width="1200"
      height="300"
      alt="kapil-raghuwanshi-website-footer"
    />
  </footer>
  <!-- footer image -->
  <div>Made with <span role="img" aria-label="love">💙</span> in India!</div>
</template>

<script>
import Chart from "Chart.js";

export default {
  name: "Home",
  props: {},
  data() {
    activeItem: "home",
  },
  methods: {
    isActive(menuItem) {
      return this.activeItem === menuItem;
    },
    setActive(menuItem) {
      this.activeItem = menuItem;
    },
  },
  mounted() {
    var ctx = document.getElementById("myChart");
    new Chart(ctx, {
      type: "polarArea",
      data: {
        datasets: [
          {
            data: [10, 20, 30, 40, 50, 20, 10],
            backgroundColor: [
              "rgba(255, 99, 132, 0.2)",
              "rgba(54, 162, 235, 0.2)",
              "rgba(255, 206, 86, 0.2)",
            ],
            borderColor: [
              "rgba(255, 99, 132, 1)",
              "rgba(54, 162, 235, 1)",
              "rgba(255, 206, 86, 1)",
            ],
            borderWidth: 1,
          },
        ],
        // These labels appear in the legend and in the tooltips when hovering different arcs
        labels: [
          "Angulat",
          "React",
          "Vue",
          "JavaScript",
          "Typescript",
          "Node",
          "Ionic",
        ],
      },
    });
  },
};
</script>

<style scoped>
p {
  font-size: 25px;
}

/* contact button */
#contact-button {
  position: fixed;
  bottom: 20px;
  right: 30px;
  z-index: 99;
  font-size: 18px;
  border: none;
  outline: none;
  background-color: red;
  color: white;
  cursor: pointer;
  padding: 15px;
  border-radius: 4px;
}

#contact-button:hover {
  background-color: #555;
}
/* contact button */
/* image slideshow */
.ia-container {
  width: 685px;
  margin: 20px auto;
  overflow: hidden;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.08);
  border: 7px solid rgba(255, 255, 255, 0.6);
}
.ia-container figure {
  position: absolute;
  top: 0;
  left: 50px; /* width of visible piece */
  width: 335px;
  box-shadow: 0 0 0 1px rgba(255, 255, 255, 0.6);
  transition: all 0.3s ease-in-out;
}
.ia-container > figure {
  position: relative;
  left: 0 !important;
}
.ia-container img {
  display: block;
  width: 100%;
}
.ia-container input {
  position: absolute;
  top: 0;
  left: 0;
  width: 50px; /* just cover visible part */
  height: 100%;
  cursor: pointer;
  border: 0;
  padding: 0;
  opacity: 0;
  z-index: 100;
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
}
.ia-container input:checked {
  width: 5px;
  left: auto;
  right: 0px;
}
.ia-container input:checked ~ figure {
  left: 335px;
  transition: all 0.7s ease-in-out;
}
.ia-container figcaption {
  width: 100%;
  height: 100%;
  background: rgba(87, 73, 81, 0.1);
  position: absolute;
  top: 0px;
  transition: all 0.2s linear;
}

.ia-container figcaption span {
  position: absolute;
  top: 40%;
  margin-top: -30px;
  right: 20px;
  left: 20px;
  overflow: hidden;
  text-align: center;
  background: rgba(87, 73, 81, 0.3);
  line-height: 20px;
  font-size: 18px;
  opacity: 0;
  text-transform: uppercase;
  letter-spacing: 4px;
  font-weight: 700;
  padding: 20px;
  color: #fff;
  text-shadow: 1px 1px 1px rgba(0, 0, 0, 0.1);
}
.ia-container input:checked + figcaption,
.ia-container input:checked:hover + figcaption {
  background: rgba(87, 73, 81, 0);
}
.ia-container input:checked + figcaption span {
  transition: all 0.4s ease-in-out 0.5s;
  opacity: 1;
  top: 50%;
}
.ia-container #ia-selector-last:checked + figcaption span {
  transition-delay: 0.3s;
}
.ia-container input:hover + figcaption {
  background: rgba(87, 73, 81, 0.03);
}
.ia-container input:checked ~ figure input {
  z-index: 1;
}
@media screen and (max-width: 720px) {
  .ia-container {
    width: 540px;
  }

  .ia-container figure {
    left: 40px;
    width: 260px;
  }

  .ia-container input {
    width: 40px;
  }

  .ia-container input:checked ~ figure {
    left: 260px;
  }

  .ia-container figcaption span {
    font-size: 16px;
  }
}

@media screen and (max-width: 520px) {
  .ia-container {
    width: 320px;
  }

  .ia-container figure {
    left: 20px;
    width: 180px;
  }

  .ia-container input {
    width: 20px;
  }

  .ia-container input:checked ~ figure {
    left: 180px;
  }

  .ia-container figcaption span {
    font-size: 12px;
    letter-spacing: 2px;
    padding: 10px;
    margin-top: -20px;
  }
}
/* image slideshow */
</style>