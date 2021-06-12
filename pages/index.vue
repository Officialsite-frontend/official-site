<template>
  <div class="neomo">
    <!-- Video-Start -->
    <div class="main-body">
      <div style="width: 70vw; margin: auto">
        <div class="video-wrap">
          <iframe
            id="video"
            title="neomo"
            width="100%"
            height="315"
            loading="lazy"
            src="https://www.youtube.com/embed/rST1gd_9Zl4?&autoplay=1&loop=1&playlist=rST1gd_9Zl4"
            frameborder="0"
            allow="encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
          ></iframe>
        </div>
      </div>
      <!-- Video-End -->

      <!-- Logo Start-->
      <div>
        <img
          lazy-src="mainlogo.png"
          src="mainlogo.png"
          width="343"
          height="350"
          alt="mainlogo"
        />
      </div>
      <!-- Logo End-->

      <div class="content">
        <span class="font">WELCOME TO</span>
        <p class="font-name">NEOMO</p>
        <div class="mt-10">
          <p class="font-content">
            <strong>NEOMO</strong> is a
            <strong>reactive framework</strong> designed to help developers
            develop web and app designs with <strong>neomorphism</strong>.
          </p>
          <p class="font-content mt-5">
            <strong>Try using it right now.</strong>
          </p>
        </div>
      </div>

      <!-- Button Start -->
      <div>
        <button
          class="button outset-neomo content-btn--outset"
          onclick="location.href='/getting_started/introduction'"
        >
          <span class="ma-0 content-btn--font">GET STARTED</span>
        </button>
        <button
          class="button outset-neomo content-btn--outset"
          onclick="location.href='https://github.com/neomorphism/neomo/archive/refs/tags/v2.0.3.zip'"
        >
          <span class="ma-0 content-btn--font">DOWNLOAD</span>
          <span class="content-btn--version"> v2.0.3 </span>
        </button>
      </div>
      <!-- Button End -->
    </div>
    <!-- Footer Start -->
    <footer class="footer">
      <div>
        <div class="footer-icon">
          <a
            href="https://github.com/neomorphism/neomo"
            aria-label="github"
            target="_blank"
            rel="noopener noreferrer"
          >
            <i class="fab fa-github fa-3x footer-button"></i>
          </a>
          <a
            href="https://www.facebook.com/neomoui"
            aria-label="facebook"
            target="_blank"
            rel="noopener noreferrer"
          >
            <i class="fab fa-facebook fa-3x footer-button"></i>
          </a>
          <a
            href="https://www.instagram.com/neomoui/"
            aria-label="instagram"
            target="_blank"
            rel="noopener noreferrer"
          >
            <i class="fab fa-instagram fa-3x footer-button"></i>
          </a>
        </div>

        <div class="mb-0 footer-font">
          Designed and built with all the love in the world by the
          <a
            class="mt-3"
            href="https://github.com/neomorphism/neomo"
            target="_blank"
            rel="noopener noreferrer"
            >AST
          </a>
          with the help of
          <a
            href="https://github.com/neomorphism/neomo"
            target="_blank"
            rel="noopener noreferrer"
            >Our Contributors</a
          >.

          <p class="mt-5">Currently v2.0.3.</p>
          <p class="pb-10">
            Released under the
            <a
              href="https://github.com/neomorphism/neomo/blob/main/LICENSE"
              target="_blank"
              rel="noopener noreferrer"
              >MIT License.</a
            >
          </p>
        </div>
      </div>
    </footer>
    <!-- Footer End -->
  </div>
</template>

<script>
export default {};
</script>

<style>
/* body Custom CSS Start */
.main-body {
  text-align: center;
  height: auto;
  margin: 0;
  background-color: #eff8ff;
  padding: 80px 0 80px 0;
}
.content {
  margin-bottom: 50px;
}

/* font Custom CSS Start */
.font {
  font-size: 2.5rem;
  color: rgb(117, 117, 117);
}
.font-name {
  font-weight: 900;
  font-size: 5rem;
  margin-top: 5px;
  margin-bottom: 0;
}
.font-content {
  font-size: 1.2rem;
  color: black;
}

/* Button Custom CSS Start */
.content-btn--font {
  font-size: 1.2rem;
}
.content-btn--version {
  margin: 7px 0 0 5px;
  font-size: 0.7rem;
  font-weight: 700;
  color: #0063e4 !important;
}
.content-btn--outset {
  width: 230px;
  min-height: 60px;
  margin: 10px 50px 0 50px;
  color: #0063e4 !important;
  border-radius: 100px;
  border: none;
}
.content-btn--outset:focus {
  outline: 0;
}
.content-btn--outset:hover {
  border: none;
  background: var(--neomo);
  box-shadow: inset 5px 5px 9px #cad3da, inset -5px -5px 9px #ebf1f5 !important;
}
.content-video {
  margin: 0 0 3rem 0;
}

/* Footer CSS Start */
.footer {
  background: #212121;
  color: rgb(177, 177, 177);
  text-align: center;
  bottom: 0;
  width: 100%;
}
.footer a {
  color: #8a8a8a;
}
.footer p {
  color: rgb(177, 177, 177);
  margin-bottom: 5px;
}
.footer-button {
  margin: 0 1rem;
  background: none;
  border: none;
  color: rgb(153, 153, 153);
  cursor: pointer;
}
.footer-button:hover {
  color: #c5c5c5 !important;
}
.footer-icon {
  display: inline-block;
  margin-top: 40px;
  margin-bottom: 40px;
}
.footer-icon > a {
  color: rgb(209, 209, 209);
}

#main-layout {
  margin: 56px 0 0 0 !important;
}
.main {
  width: 100vw;
  padding: 0;
}
button:hover {
  color: blue !important;
}

.header-menu--button {
  display: none !important;
}

/* Left Navigation Start */
.navbar {
  display: none;
}

/* Lightbar Start */
.right-bar {
  display: none;
}

/* Video Start */
.video-wrap {
  position: relative;
  padding-bottom: 56.25%;
  width: 100%;
  height: 0;
  overflow: hidden;
  margin: 0 auto;
}
.video-wrap iframe,
.video-wrap object,
.video-wrap embed {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

@media screen and (max-width: 500px) {
  .content {
    width: 90vw;
    margin: auto;
  }
}
</style>
