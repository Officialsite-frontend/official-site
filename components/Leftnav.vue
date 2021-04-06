<template>
  <!-- Left Navigation Start -->
  <div class="navbar">
    <!-- Overview list start -->
    <button class="toggle-button" onclick="NavbarToggle()" @click="ToggleIcon">
      Overview
      <i class="fa fa-caret-down"></i>
    </button>
    <div class="toggle-content">
      <a href="#">Link 1</a>
      <a href="#">Link 2</a>
      <a href="#">Link 3</a>
    </div>
    <!-- Overview list end -->

    <!-- Customize list start -->
    <button class="toggle-button" onclick="NavbarToggle()" @click="ToggleIcon">
      Customize
      <i class="fa fa-caret-down"></i>
    </button>
    <div class="toggle-content">
      <a href="#">Link 1</a>
      <a href="#">Link 2</a>
      <a href="#">Link 3</a>
    </div>
    <!-- Customize list end -->

    <!-- Components list start -->
    <button class="toggle-button" onclick="NavbarToggle()" @click="ToggleIcon">
      Components
      <i class="fa fa-caret-down"></i>
    </button>
    <div class="toggle-content">
      <a href="#">Alert</a>
      <a href="#">Badge</a>
      <a href="#">Breadcrumb</a>
      <a href="#">Button</a>
      <a href="#">Card</a>
      <a href="#">Columns</a>
      <a href="#">Component</a>
      <a href="#">Dropdown</a>
      <a href="#">Icon</a>
      <a href="#">Modal</a>
      <a href="#">Navbar</a>
      <a href="#">Navigation</a>
      <a href="#">Pagination</a>
      <a href="#">Progressbar</a>
      <a href="#">Select</a>
      <a href="#">Spinner</a>
      <a href="#">Tab</a>
      <a href="#">Toast</a>
      <a href="#">Tooltip</a>
    </div>
    <!-- Components list start -->

    <!-- Content list start -->
    <button class="toggle-button" onclick="NavbarToggle()" @click="ToggleIcon">
      Content
      <i class="fa fa-caret-down"></i>
    </button>
    <div class="toggle-content">
      <a href="#">Content</a>
      <a href="#">table</a>
    </div>
    <!-- Content list end -->

    <!-- Form list start -->
    <button class="toggle-button" onclick="NavbarToggle()" @click="ToggleIcon">
      Form
      <i class="fa fa-caret-down"></i>
    </button>
    <div class="toggle-content">
      <a href="#">Checkbox</a>
      <a href="#">File</a>
      <a href="#">Input</a>
      <a href="#">Label</a>
      <a href="#">Radio</a>
      <a href="#">Range</a>
    </div>
    <!-- Form list start -->

    <!-- Helpers list start -->
    <button class="toggle-button" onclick="NavbarToggle()" @click="ToggleIcon">
      Helpers
      <i class="fa fa-caret-down"></i>
    </button>
    <div class="toggle-content">
      <a href="#">Helper</a>
      <a href="#">Typography</a>
    </div>
    <!-- Helpers list start -->

    <!-- Layout list start -->
    <button class="toggle-button" onclick="NavbarToggle()" @click="ToggleIcon">
      Layout
      <i class="fa fa-caret-down"></i>
    </button>
    <div class="toggle-content">
      <a href="#">Layout</a>
    </div>
    <!-- Layout list start -->
  </div>
  <!-- Left Navigation End-->
</template>

<script>
/* eslint-disable */
export default {
  methods: {
    ToggleIcon() {
      var toggle = document.getElementsByClassName('toggle-button')
      var i

      for (i = 0; i < toggle.length; i++) {
        if (toggle[i] === event.target) {
          if (toggle[i].childNodes[1].classList[1] === 'fa-caret-down') {
            toggle[i].childNodes[1].className = 'fa fa-caret-up'
          } else if (toggle[i].childNodes[1].classList[1] === 'fa-caret-up') {
            toggle[i].childNodes[1].className = 'fa fa-caret-down'
          }
        }
      }
    },
  },
}
</script>

<style>
/* Left Navigation Start */
.navbar {
  width: 250px;
  position: sticky;
  z-index: 1;
  left: 0;
  overflow-x: hidden;
  padding-top: 20px;
  padding-left: 20px;
}
.navbar .toggle-content a {
  padding-bottom: 10px;
}
.navbar .fa-caret-down {
  float: right;
  padding-right: 8px;
}
.navbar .fa-caret-up {
  float: right;
  padding-right: 8px;
}
</style>
