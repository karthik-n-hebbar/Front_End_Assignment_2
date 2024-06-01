<template>
  <body>
    <div class="swimlane">
      <h1>Most-watched films</h1>
      <div class="swimlane-slide">
        <div class="image-container">
          <img src="@/assets/Oppenheimer.png" alt="" />
          <p>Oppenheimer</p>
        </div>
        <div class="image-container">
          <img src="@/assets/Past Lives.png" alt="" />
          <p>Past Lives</p>
        </div>
        <div class="image-container">
          <img src="@/assets/Polite Society.png" alt="" />
          <p>Polite Society</p>
        </div>
        <div class="image-container">
          <img src="@/assets/Robots.png" alt="" />
          <p>Robots</p>
        </div>
        <div class="image-container">
          <img src="@/assets/Sanctuary.png" alt="" />
          <p>Sanctuary</p>
        </div>
        <div class="image-container">
          <img src="@/assets/Talk To Me.png" alt="" />
          <p>Talk To Me</p>
        </div>
      </div>
    </div>
  </body>
</template>

<script>
export default {
  name: "swinlane_app",
  components: {},
  data() {
    return {
      movies: [
        {
          id: 1,
          title: "Oppenheimer",
          imageLink: "@/assets/Oppenheimer.png",
          isNew: false,
        },
        {
          id: 2,
          title: "Past Lives",
          imageLink: "@/assets/Past Lives.png",
          isNew: false,
        },
        {
          id: 3,
          title: "Polite Society",
          imageLink: "@/assets/Polite Society.png",
          isNew: false,
        },
        {
          id: 4,
          title: "Robots",
          imageLink: "@/assets/Robots.png",
          isNew: false,
        },
        {
          id: 5,
          title: "Sanctuary",
          imageLink: "@/assets/Sanctuary.png",
          isNew: false,
        },
        {
          id: 6,
          title: "Talk To Me",
          imageLink: "@/assets/Talk To Me.png",
          isNew: false,
        },
        {
          id: 7,
          title: "About My Father",
          imageLink: "@/assets/About My Father.png",
          isNew: true,
        },
        {
          id: 8,
          title: "Air",
          imageLink: "@/assets/Air.png",
          isNew: false,
        },
        {
          id: 9,
          title: "Are You There God? It’s Me, Margaret.",
          imageLink: "@/assets/Are You There God.png",
          isNew: true,
        },
        {
          id: 10,
          title: "Guardians of the Galaxy: Volume 3",
          imageLink: "@/assets/Guardians of the Galaxy Volume 3.png",
          isNew: false,
        },
        {
          id: 11,
          title: "Big George Foreman",
          imageLink: "@/assets/Big George Foreman.png",
          isNew: false,
        },
        {
          id: 12,
          title: "Beau Is Afraid",
          imageLink: "@/assets/Beau Is Afraid.png",
          isNew: false,
        },
      ],
    };
  },
  mounted() {
    this.movies.forEach((movie) => {
      console.log(movie.imageLink);
    });
  },
  methods: {},
};
</script>

<style>
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
  height: 450px;
}

.swimlane-slide {
  width: 1320px;
  height: 400px;
  display: flex;
  justify-content: space-between;
  position: relative;
  bottom: -22px;
}

img {
  width: 210px;
  height: 307px;
  border-radius: 10px;
}

.image-container {
  background: var(--Elements-Piano-Black, rgba(28, 28, 30, 1));
  border-radius: 10px;
}

.image-container p {
  font-family: Noto Sans;
  font-size: 14.5px;
  margin-left: 16px;
  margin-top: 48px;
}

.slider-container {
  position: relative;
  width: 80%;
}

.slider-container h2 {
  margin-left: 10px;
}

.slider {
  display: flex;
  overflow: hidden;
}

.slider-item {
  min-width: 200px;
  margin: 0 10px;
  text-align: center;
  position: relative; /* Added for new badge positioning */
}

.slider-item img {
  width: 100%;
  border-radius: 10px;
}

.slider-item p {
  margin-top: 5px;
}

.new-badge {
  background-color: red;
  color: white;
  padding: 5px;
  border-radius: 5px;
  font-size: 12px;
  position: absolute;
  top: 10px;
  right: 10px;
}

.prev,
.next {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  border: none;
  padding: 10px;
  cursor: pointer;
}

.prev {
  left: 0;
}

.next {
  right: 0;
}
</style>
