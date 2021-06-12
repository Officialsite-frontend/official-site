<template>
  <div>
    <h1>Introduction</h1>
    <client-only>
      <p class="bottom-border">
        Get started with NEOMO, a
        <strong class="text-strong">UI framework</strong> for
        <strong class="text-strong">neomorphism</strong> design. <br /><a
          href="/"
          >v2.0.3 Docs</a
        >
        kindly provide you with the usage and example code.
      </p>
    </client-only>

    <div class="tab">
      <div class="columns">
        <div class="column size-12">
          <ul class="tab-content outset-neomo">
            <li id="content-1" class="tab-content--list">
              <div class="tab-content--title"><h2>What is NEOMO?</h2></div>
              <div class="tab-content--text">
                <client-only>
                  <p>
                    NEOMO is a
                    <strong class="text-strong">UI framework</strong> designed
                    with <strong class="text-strong">neomorphism</strong>. To
                    use neomorphism, which has emerged as a new design trend,
                    developers have the
                    <strong class="text-strong">inconvenience</strong> of going
                    through
                    <strong class="text-strong">customizing</strong>
                    themselves.<br />
                  </p>
                  <p>
                    <strong class="text-strong">To reduce</strong> the
                    inconvenience above, NEOMO provides UI designed with
                    neomorphism. NEOMO is developed with the
                    <strong class="text-strong">goal</strong> of providing
                    various example codes.
                  </p>
                </client-only>
              </div>
            </li>
            <li id="content-2" class="tab-content--list">
              <div class="tab-content--title"><h2>License</h2></div>
              <div class="tab-content--text">
                <client-only>
                  <p>
                    NEOMO's license is
                    <strong class="text-strong">MIT license</strong>. You can
                    check it out on
                    <a
                      href="https://github.com/neomorphism/neomo/blob/main/LICENSE"
                      >github</a
                    >
                    .
                  </p>
                </client-only>
              </div>
            </li>
            <li id="content-3" class="tab-content--list">
              <div class="tab-content--title"><h2>Community</h2></div>
              <div class="tab-content--text">
                <client-only>
                  <p>
                    You can be a
                    <strong class="text-strong">developer</strong> at the same
                    time as a NEOMO user. <br />Use a variety of methods to
                    <strong class="text-strong">contribute</strong> to NEOMO.
                  </p></client-only
                >
                <ul class="commu-list">
                  <li>
                    <a href="https://github.com/neomorphism/neomo/issues"
                      >Github</a
                    >
                  </li>
                  <li>
                    <a href="https://www.instagram.com/neomoui/">Instagram</a>
                  </li>
                  <li>
                    <a href="https://www.facebook.com/neomoui">Facebook</a>
                  </li>
                </ul>
              </div>
            </li>
            <li id="content-4" class="tab-content--list">
              <div class="tab-content--title"><h2>Preview</h2></div>
              <div class="tab-content--text">
                <client-only>
                  <p>
                    You can see
                    <strong class="text-strong">all components</strong> at once!
                  </p></client-only
                >
                <button
                  class="button outset-neomo normal header-freedemo"
                  onclick="window.open('https://neomorphism.github.io/')"
                >
                  <strong>Preview</strong>
                </button>
              </div>
            </li>
          </ul>
          <ul class="tab-list tab-right">
            <li><a id="tab-1" class="current">NEOMO?</a></li>
            <li><a id="tab-2">License</a></li>
            <li><a id="tab-3">Community</a></li>
            <li><a id="tab-4">Preview</a></li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
a {
  color: #2a6fc9;
}
.commu-list li {
  margin-top: 7px;
}
</style>
