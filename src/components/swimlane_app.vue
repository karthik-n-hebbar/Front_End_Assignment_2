<template>
  <body>
    <!-- <div class="swimlane">
      <h1>Most-watched films</h1>
      <div class="swimlane-slide">
        <div
          v-for="(movie, index) in firstSixImages"
          :key="index"
          class="image-container"
        >
          <img :src="movie.src" :alt="movie.title" />
          <div class="newTag" :style="{ display: isMovieNew(movie) }">
            <p>NEW</p>
          </div>
          <h3>{{ movie.title }}</h3>
        </div>
      </div>
      <div class="swinlane-slider">
        <img
          src="@/assets/Vector.png"
          id="slider-vector"
          alt=""
          style="height: 63px; width: 35px"
        />
      </div>
    </div> -->

    <div class="swimlane">
      <h1>Most-watched films</h1>
      <div class="swimlane-slide" ref="slide">
        <div
          v-for="(movie, index) in firstSixImages"
          :key="index"
          class="image-container"
          @mouseover="toggleSliderOnLast(index)"
          @mouseleave="toggleSliderOnLast(-1)"
        >
          <img :src="movie.src" :alt="movie.title" />
          <div class="newTag" :style="{ display: isMovieNew(movie) }">
            <p>NEW</p>
          </div>
          <h3>{{ movie.title }}</h3>
        </div>
      </div>
      <div
        class="swinlane-slider"
        :style="{ visibility: showSlider ? 'visible' : 'hidden' }"
        @mouseover="toggleSlider(true)"
        @mouseleave="toggleSlider(false)"
      >
        <img
          src="@/assets/Vector.png"
          id="slider-vector"
          alt=""
          style="height: 63px; width: 35px"
        />
      </div>
    </div>
  </body>
</template>

<script>
import Oppenheimer from "@/assets/Oppenheimer.png";
import PastLives from "@/assets/Past Lives.png";
import PoliteSociety from "@/assets/Polite Society.png";
import Robots from "@/assets/Robots.png";
import Sanctuary from "@/assets/Sanctuary.png";
import TalkToMe from "@/assets/Talk To Me.png";
import AboutMyFather from "@/assets/About My Father.png";
import Air from "@/assets/Air.png";
import AreYouThereGod from "@/assets/Are You There God.png";
import GuardiansOfTheGalaxy from "@/assets/Guardians of the Galaxy Volume 3.png";
import BigGeorgeForeman from "@/assets/Big George Foreman.png";
import BeauIsAfraid from "@/assets/Beau Is Afraid.png";
export default {
  name: "swinlane_app",
  components: {},
  data() {
    return {
      // movies: [
      //   {
      //     id: 1,
      //     title: "Oppenheimer",
      //     imageLink: "@/assets/Oppenheimer.png",
      //     isNew: false,
      //   },
      //   {
      //     id: 2,
      //     title: "Past Lives",
      //     imageLink: "@/assets/Past Lives.png",
      //     isNew: false,
      //   },
      //   {
      //     id: 3,
      //     title: "Polite Society",
      //     imageLink: "@/assets/Polite Society.png",
      //     isNew: false,
      //   },
      //   {
      //     id: 4,
      //     title: "Robots",
      //     imageLink: "@/assets/Robots.png",
      //     isNew: false,
      //   },
      //   {
      //     id: 5,
      //     title: "Sanctuary",
      //     imageLink: "@/assets/Sanctuary.png",
      //     isNew: false,
      //   },
      //   {
      //     id: 6,
      //     title: "Talk To Me",
      //     imageLink: "@/assets/Talk To Me.png",
      //     isNew: false,
      //   },
      //   {
      //     id: 7,
      //     title: "About My Father",
      //     imageLink: "@/assets/About My Father.png",
      //     isNew: true,
      //   },
      //   {
      //     id: 8,
      //     title: "Air",
      //     imageLink: "@/assets/Air.png",
      //     isNew: false,
      //   },
      //   {
      //     id: 9,
      //     title: "Are You There God? It’s Me, Margaret.",
      //     imageLink: "@/assets/Are You There God.png",
      //     isNew: true,
      //   },
      //   {
      //     id: 10,
      //     title: "Guardians of the Galaxy: Volume 3",
      //     imageLink: "@/assets/Guardians of the Galaxy Volume 3.png",
      //     isNew: false,
      //   },
      //   {
      //     id: 11,
      //     title: "Big George Foreman",
      //     imageLink: "@/assets/Big George Foreman.png",
      //     isNew: false,
      //   },
      //   {
      //     id: 12,
      //     title: "Beau Is Afraid",
      //     imageLink: "@/assets/Beau Is Afraid.png",
      //     isNew: false,
      //   },
      // ],
      showSlider: false,
      movie_images: [
        { src: Oppenheimer, title: "Oppenheimer", isNew: true },
        { src: PastLives, title: "Past Lives", isNew: false },
        { src: PoliteSociety, title: "Polite Society", isNew: false },
        { src: Robots, title: "Robots", isNew: false },
        { src: Sanctuary, title: "Sanctuary", isNew: false },
        { src: TalkToMe, title: "Talk To Me", isNew: false },
        { src: AboutMyFather, title: "About My Father", isNew: true },
        { src: Air, title: "Air", isNew: false },
        { src: AreYouThereGod, title: "Are You There God", isNew: true },
        {
          src: GuardiansOfTheGalaxy,
          title: "Guardians of the Galaxy Volume 3",
          isNew: false,
        },
        { src: BigGeorgeForeman, title: "Big George Foreman", isNew: false },
        { src: BeauIsAfraid, title: "Beau Is Afraid", isNew: false },
      ],
    };
  },
  mounted() {},
  methods: {
    isMovieNew(movie) {
      return movie.isNew ? "block" : "none";
    },
    toggleSlider(value) {
      this.showSlider = value;
    },
    toggleSliderOnLast(index) {
      this.showSlider = index !== this.firstSixImages.length - 1;
    },
  },
  computed: {
    firstSixImages() {
      return this.movie_images.slice(0, 6);
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Dancing+Script&family=Noto+Sans:ital,wght@0,100..900;1,100..900&display=swap");
* {
  margin: 0px;
  padding: 0px;
}
body {
  background: rgba(68, 68, 68, 1);
  color: rgba(255, 255, 255, 1);
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.swimlane {
  width: 1320px;
  height: 469px;
  position: relative;
}

.swimlane-slide {
  width: 1320px;
  height: 400px;
  display: flex;
  justify-content: space-between;
  position: relative;
  bottom: -16px;
}

img {
  width: 210px;
  height: 307px;
  border-radius: 10px;
}

.image-container {
  background: var(--Elements-Piano-Black, rgba(28, 28, 30, 1));
  border-radius: 10px;
  position: relative;
  cursor: pointer;
  background: linear-gradient(90deg, #1c1c1e 33.33%, #121212 65.62%);
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
  transition: transform 0.3s ease;
  width: 210px;
  height: 400px;
}

.image-container:hover {
  transform: scale(1.075);
  box-shadow: 10px 10px 10px 10px rgba(150, 150, 150, 0.25);
}

.image-container h3 {
  font-family: Noto Sans;
  font-size: 14.5px;
  margin-left: 16px;
  margin-top: 42px;
}

.newTag {
  width: 43px;
  height: 21px;
  background: rgba(255, 159, 10, 1);
  text-align: center;
  justify-items: center;
  margin-left: 16px;
  margin-top: 8px;
  margin-bottom: 8px;
  border-radius: 3px;
  position: absolute;
  display: none;
}

.newTag p {
  font-family: Noto Sans;
  font-weight: 800;
  letter-spacing: 0.1em;
  text-align: center;
  font-size: 12px;
  line-height: 25px;
  color: var(--Elements-Piano-Black, rgba(28, 28, 30, 1));
  width: 100%;
  height: 100%;
}
.swinlane-slider {
  width: 110px;
  height: 432px;
  position: absolute;
  bottom: 0;
  right: 0;
  background: linear-gradient(
    265.54deg,
    #060606 3.35%,
    rgba(6, 6, 6, 0.7) 96.15%
  );
  display: grid;
  justify-items: center;
  align-items: center;
  border-radius: 10px;
}
</style>
