<template>
  <div>
    <!-- Header Start -->
    <header class="header neomo">
      <!-- Header-logo Start -->
      <div class="ml-1 header-logo">
        <a class="header-logo--link" href="/">
          <div class="header-logo--icon">
            <img
              lazy-src="~/static/blacklogo.png"
              src="~/static/blacklogo.png"
              width="48"
              height="48"
              alt="logo"
            />
          </div>
          <div class="header-logo--name">
            <img
              lazy-src="~/static/blacklogo.png"
              src="~/static/logoname.png"
              width="150"
              height="39"
              alt="logo name"
            />
          </div>
        </a>
      </div>
      <!-- Header-logo End -->

      <!-- Header-version Start -->
      <div class="header-version">v2.0.3</div>
      <!-- Header-version End -->

      <div class style="display: flex; position: relative">
        <!-- Header-searchbar Start -->
        <input
          class="input header-searchbar inset-neomo"
          type="text"
          placeholder="Search Neomo"
          @input="updateInput"
        />
        <div id="search-box" class="card outset-neomo">
          <div>
            <p id="search-result">No results found for "{{ inputText }}"</p>
          </div>
          <p id="search-title--start">Getting Started</p>
          <ul id="search-start" class="nav-column">
            <li v-for="item in startedResult" :key="item.id">
              <a class="nav-link" :href="item[1]">{{ item[0] }}</a>
            </li>
          </ul>
          <p id="search-title--layout">Layout</p>
          <ul id="search-layout" class="nav-column search-layout">
            <li v-for="item in layoutResult" :key="item.id">
              <a class="nav-link" :href="item[1]">{{ item[0] }}</a>
            </li>
          </ul>
          <p id="search-title--comp">Components</p>
          <ul id="search-comp" class="nav-column">
            <li v-for="item in compResult" :key="item.id">
              <a class="nav-link" :href="item[1]">{{ item[0] }}</a>
            </li>
          </ul>
          <p id="search-title--content">Content</p>
          <ul id="search-content" class="nav-column">
            <li v-for="item in contentResult" :key="item.id">
              <a class="nav-link" :href="item[1]">{{ item[0] }}</a>
            </li>
          </ul>
          <p id="search-title--form">Form</p>
          <ul id="search-form" class="nav-column">
            <li v-for="item in formResult" :key="item.id">
              <a class="nav-link" :href="item[1]">{{ item[0] }}</a>
            </li>
          </ul>
          <p id="search-title--helper">Helpers</p>
          <ul id="search-helper" class="nav-column">
            <li v-for="item in helperResult" :key="item.id">
              <a class="nav-link" :href="item[1]">{{ item[0] }}</a>
            </li>
          </ul>
        </div>
        <!-- Header-searchbar End -->
      </div>

      <!-- Header-menu Start -->
      <button
        data-modal-id="header-modal"
        class="modal-button outset-neomo header-menu--button"
        style="cursor: pointer"
        aria-label="header button"
      >
        <i class="fas fa-bars"></i>
      </button>
      <div
        data-modal-id="header-modal"
        class="modal"
        style="overflow-y: hidden"
      >
        <div class="modal-content--sm outset-neomo modal-menu--content">
          <span class="modal-close">&times;</span>
          <div id="main-leftnav--hidden" class="container content-nav--hidden">
            <Modalnav />
          </div>
        </div>
      </div>
      <!-- Header-menu End -->
    </header>
    <!-- Header End -->

    <div id="main-layout" class="colunm neomo">
      <!-- Left Navigation Start -->
      <div id="main-leftnav" class="container content-nav pt-3">
        <Leftnav />
      </div>
      <!-- Left Navigation End -->

      <!-- main Start -->
      <main class="pb-0 main-border">
        <div class="main">
          <nuxt />
        </div>
      </main>
      <!-- Contents End -->
    </div>
  </div>
</template>

<script>
/* eslint-disable */
import Leftnav from "@/components/Leftnav.vue";
import Modalnav from "@/components/Modalnav.vue";

export default {
  data() {
    return {
      inputText: "",
      searchStarted: [
        ["introduction", "/getting_started/introduction"],
        ["download", "/getting_started/download"],
        [`modifiers syntax`, "/getting_started/modifiers"],
      ],
      searchLayout: [["columns", "/layout/columns"]],
      searchComp: [
        ["alert", "/components/alert"],
        ["badge", "/components/badge"],
        ["breadcrumb", "/components/breadcrumb"],
        ["button", "/components/button"],
        ["card", "/components/card"],
        ["dropdown", "/components/dropdown"],
        ["icon", "/components/icon"],
        ["modal", "/components/modal"],
        ["navbar", "/components/navbar"],
        ["navigation", "/components/navigation"],
        ["pagination", "/components/pagination"],
        ["progressbar", "/components/progressbar"],
        ["select", "/components/select"],
        ["spinner", "/components/spinner"],
        ["tab", "/components/tab"],
        ["toast", "/components/toast"],
        ["tooltip", "/components/tooltip"],
      ],
      searchForm: [
        ["checkbox", "/form/checkbox"],
        ["file", "/form/file"],
        ["input", "/form/input"],
        ["labels", "/form/labels"],
        ["radio", "/form/radio"],
        ["range", "/form/range"],
        ["switches", "/form/switches"],
      ],
      searchContent: [["table", "/content/table"]],
      searchHelper: [
        [`colored links`, "/helpers/coloredLinks"],
        ["typography", "/helpers/typography"],
      ],

      startedResult: [],
      layoutResult: [],
      compResult: [],
      contentResult: [],
      formResult: [],
      helperResult: [],
      components: {
        Leftnav,
        Modalnav,
      },
    };
  },
  methods: {
    updateInput(event) {
      const updatedText = event.target.value;
      this.inputText = updatedText;
      if (this.inputText !== "") {
        document.getElementById("search-box").style.display = "block";
        document.getElementById("search-title--start").style.display = "none";
        document.getElementById("search-title--layout").style.display = "none";
        document.getElementById("search-title--comp").style.display = "none";
        document.getElementById("search-title--content").style.display = "none";
        document.getElementById("search-title--form").style.display = "none";
        document.getElementById("search-title--helper").style.display = "none";
        document.getElementById("search-result").style.display = "block";

        const textEx = this.inputText.replace(/([.?*+^$[\]\\(){}|-])/g, "\\$1");
        const value = new RegExp(textEx, "i");
        let i;

        this.startedResult = [];
        this.layoutResult = [];
        this.compResult = [];
        this.contentResult = [];
        this.formResult = [];
        this.helperResult = [];

        for (i = 0; i < this.searchStarted.length; i++) {
          if (value.exec(this.searchStarted[i][0])) {
            this.startedResult.push(this.searchStarted[i]);
            document.getElementById("search-start").style.display = "block";

            if (this.startedResult.length > 0) {
              document.getElementById("search-result").style.display = "none";
              document.getElementById("search-title--start").style.display =
                "block";
            }
          }
        }
        for (i = 0; i < this.searchLayout.length; i++) {
          if (value.exec(this.searchLayout[i][0])) {
            this.layoutResult.push(this.searchLayout[i]);
            document.getElementById("search-layout").style.display = "block";

            if (this.layoutResult.length > 0) {
              document.getElementById("search-result").style.display = "none";
              document.getElementById("search-title--layout").style.display =
                "block";
            }
          }
        }
        for (i = 0; i < this.searchComp.length; i++) {
          if (value.exec(this.searchComp[i][0])) {
            this.compResult.push(this.searchComp[i]);
            document.getElementById("search-comp").style.display = "block";

            if (this.compResult.length > 0) {
              document.getElementById("search-result").style.display = "none";
              document.getElementById("search-title--comp").style.display =
                "block";
            }
          }
        }
        for (i = 0; i < this.searchContent.length; i++) {
          if (value.exec(this.searchContent[i][0])) {
            this.contentResult.push(this.searchContent[i]);
            document.getElementById("search-content").style.display = "block";

            if (this.contentResult.length > 0) {
              document.getElementById("search-result").style.display = "none";
              document.getElementById("search-title--content").style.display =
                "block";
            }
          }
        }
        for (i = 0; i < this.searchForm.length; i++) {
          if (value.exec(this.searchForm[i][0])) {
            this.formResult.push(this.searchForm[i]);
            document.getElementById("search-form").style.display = "block";

            if (this.formResult.length > 0) {
              document.getElementById("search-result").style.display = "none";
              document.getElementById("search-title--form").style.display =
                "block";
            }
          }
        }
        for (i = 0; i < this.searchHelper.length; i++) {
          if (value.exec(this.searchHelper[i][0])) {
            this.helperResult.push(this.searchHelper[i]);
            document.getElementById("search-helper").style.display = "block";

            if (this.helperResult.length > 0) {
              document.getElementById("search-result").style.display = "none";
              document.getElementById("search-title--helper").style.display =
                "block";
            }
          }
        }
      } else {
        document.getElementById("search-box").style.display = "none";
      }
    },
  },
  mounted() {
    copyToClipboard();
    window.addEventListener("click", function (event) {
      if (
        !event.target.closest("#search-box") &&
        !event.target.matches(".header-searchbar")
      ) {
        document.getElementById("search-box").style.display = "none";
        document.getElementsByClassName("header-searchbar")[0].value = "";
      }
    });
  },
};
</script>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  margin: 0;
  max-width: 100%;
}

html {
  height: 100%;
  scroll-behavior: smooth;
  background: var(--neomo);
}
body {
  margin: 0;
  height: 100%;
  font-family: "Open Sans", sans-serif !important;
}
/* Header CSS Start */
.header {
  display: flex;
  height: 64px;
  border-bottom: 0.1px solid rgb(233, 233, 233);
  width: 100%;
  position: fixed;
  top: 0;
  background-color: white;
  z-index: 2;
  padding-left: 7vw;
  padding-right: 7vw;
}
.header-logo--link {
  padding: 8px 0 0 8px;
  min-width: 200px;
  display: flex;
  height: 48px;
}
.header-logo--icon {
  margin: auto;
  max-height: 48px;
  max-width: 48px;
}
.header-logo--name {
  margin: 5px 0 0 2px;
  max-height: 48px;
  max-width: 150px;
}
.header-version {
  max-width: 10px;
  margin: auto;
  margin-left: 20px;
  color: #707070;
  font-size: 0.86rem;
}
.header-searchbar {
  padding-left: 1.2rem;
  border: none;
  border-radius: 10px;
  margin: 11px;
  width: 300px;
}
.header-searchbar:focus {
  box-shadow: inset -3px -3px 7px #ffffffe5,
    inset 3px 3px 7px rgba(6, 93, 243, 0.288) !important;
}

.header-menu--button {
  display: none;
  min-width: 48px;
  width: 48px;
  height: 48px;
  margin-top: 8px;
}

.header-freedemo {
  height: 43px !important;
  margin: 10px 1rem 0 0 !important;
  color: #224aff !important;
}

.header-freedemo button:hover {
  color: blue !important;
}

.modal-menu--content {
  margin: 0;
  width: 350px;
  z-index: 10;
}

.content-nav--hidden .navbar {
  width: 100vw;
  padding: 0;
  position: relative !important;
}
.content-nav--hidden .card {
  box-shadow: none !important;
  padding: 0;
}

/* serch-box Start */
#search-box {
  display: none;
  position: absolute;
  top: 66px;
  padding: 8px;
  width: 300px;
  right: 10px;
}

#search-start,
#search-layout,
#search-comp,
#search-content,
#search-form,
#search-helper {
  display: none;
}
#search-box .nav-link {
  padding: 0.5rem 0.5rem 0.5rem 1.5rem;
  font-size: 0.9rem;
}
#search-box .nav-link:hover {
  color: blue;
}
#search-title--start,
#search-title--layout,
#search-title--comp,
#search-title--content,
#search-title--form,
#search-title--helper {
  font-size: 1rem;
  color: rgb(43, 43, 43);
  margin-left: 0.5rem;
  font-weight: 700;
  display: none;
}
.search-result {
  display: none;
  font-size: 0.9rem;
}

/* Content CSS Start */
#main-layout {
  margin: 56px 0 0 0 !important;
  height: 100vh;
  flex: 1 1 auto;
  max-width: 100%;
}
.main {
  width: 55vw;
  margin: auto;
  padding: 20px 50px 50px 50px;
  height: 100%;
}

#main-leftnav,
#main-leftnav--hidden {
  left: 0;
}

a,
a:link,
a:visited,
a:active,
a:hover,
hr {
  margin: auto;
  text-decoration: none;
}

.container {
  margin-top: 0;
}

h1 {
  font-size: 3rem;
  font-weight: 100;
  padding-top: 30px;
  padding-bottom: 20px;
  background: linear-gradient(
    90deg,
    rgba(113, 132, 255, 1) 15%,
    rgba(47, 25, 255, 0.9192051820728291) 45%
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
p {
  line-height: 1.4;
  margin-top: 10px;
  margin-bottom: 10px;
  color: #696969;
  font-size: 1rem;
}
h2 {
  margin-top: 20px;
  margin-bottom: 20px;
  color: #575757;
}
.bottom-border {
  padding-bottom: 50px;
  margin-bottom: 50px;
  border-bottom: thin solid rgba(0, 0, 0, 0.07);
}
.text-strong {
  background: none;
  padding: 0;
  color: rgb(95, 95, 95);
  font-weight: bold;
}
.content-tab--only {
  display: none !important;
}
.nuxt-content pre {
  margin: 0;
  margin-bottom: 1rem;
  border: none;
  line-height: 18px;
  background: rgb(223, 237, 255) !important;
  display: flex;
  justify-content: space-between;
  position: relative;
  font-size: 12px;
}
pre .copy-btn i {
  opacity: 0.4;
}
.copy-btn {
  padding: 10px;
  cursor: pointer;
  border: none;
  border-radius: 100%;
  width: 3rem;
  height: 3rem;
  background: rgb(223, 237, 255);
  box-shadow: -3px -3px 7px #ffffffe5, 3px 3px 5px #3981fd49 !important;
}
.copy-btn:hover {
  border: none;
  box-shadow: inset -3px -3px 7px #ffffffe5,
    inset 3px 3px 5px rgba(54, 122, 240, 0.288) !important;
}
.copy-btn.modal-button {
  min-width: auto;
  padding: 10px;
}
pre .modal-content--sm {
  font-size: 0.9rem;
  font-family: "Jeju Gothic", sans-serif;
  display: flex;
  justify-content: space-between;
  margin: auto;
  margin-top: 20%;
}
pre .modal-content--sm p {
  margin-left: 2rem;
}
pre .modal-content--sm span {
  margin: auto 1rem;
  font-size: 1.3rem;
}
.nuxt-content code {
  font-family: consolas;
  margin-top: 12px;
}
.code-exam {
  padding: 10px 80px 40px 80px;
  margin-bottom: 40px;
}
.expanded {
  visibility: hidden;
  max-height: 0;
  opacity: 0;
  transition: all 0.2s linear;
}
.button i {
  padding: 10px;
}
.button-exam {
  float: right;
  padding: 0;
  border-radius: 100%;
}
.neomo .tab ul.tab-list li {
  margin-bottom: 2rem;
}
.neomo .tab ul.tab-list li a.current {
  color: rgb(6, 93, 255);
}
.neomo .tab ul.tab-list li a:hover {
  color: rgb(6, 93, 255);
}

@media screen and (max-width: 1430px) {
  .content-nav {
    display: none !important;
  }
  .header-menu--button {
    display: block !important;
  }
  .main {
    width: 85%;
  }
}
@media screen and (max-width: 800px) {
  .header {
    justify-content: space-between;
  }
  .header-version {
    display: none;
  }
  .header-logo {
    margin: 0;
    width: 48px;
  }
  .header-logo--link {
    min-width: 0;
    padding: 8px 0;
  }
  .header-logo--icon {
    margin: 0;
  }
  .header-logo--name {
    display: none;
  }
  .header-searchbar {
    width: 50vw;
  }
  #search-box {
    width: 50vw;
    margin: auto;
  }
  p {
    font-size: 0.8rem;
  }

  .tab {
    border: none;
    margin: 0;
    padding: 0;
  }
  .tab-content {
    box-shadow: none !important;
  }
  .tab ul.tab-content {
    width: 95vw;
    padding: 0;
  }
  .tab ul.tab-content li.tab-content--list,
  .main {
    padding: 0;
  }
  .code-exam {
    padding: 10px 20px 40px 20px;
  }
  .neomo .tab ul.tab-list li {
    margin-bottom: 1rem;
  }
  .tab ul.tab-right li {
    margin: 5px;
  }
  .badge {
    display: inline-block;
  }
  .breadcrumb {
    overflow-x: scroll;
  }
  .breadcrumb ul {
    padding: 5px;
  }
  .card {
    overflow-x: scroll;
  }
  .card-margin {
    margin: 0;
  }
}

:root {
  --bs-font-monospace: SFMono-Regular, Menlo, Monaco, Consolas,
    "Liberation Mono", "Courier New", monospace;
}
</style>
