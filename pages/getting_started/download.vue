<template>
  <div>
    <h1>Download</h1>
    <client-only>
      <p class="bottom-border">
        NEOMO can import compiled CSS and JavaScript, source code via
        <strong class="text-strong">download</strong>, provide
        <strong class="text-strong">cdn</strong>, and include it as a package
        manager such as <strong class="text-strong">npm, yarn</strong>.
      </p>
    </client-only>

    <div class="tab">
      <div class="columns">
        <div class="column size-12">
          <ul class="tab-content outset-neomo">
            <li id="content-1" class="tab-content--list">
              <div class="tab-content--title"><h2>Download</h2></div>
              <div class="tab-content--text">
                <client-only>
                  <p>
                    Download to use NEOMO's
                    <strong class="text-strong">CSS</strong> and
                    <strong class="text-strong">JS</strong>.
                  </p></client-only
                >
                <button
                  class="button normal outset-neomo"
                  onclick="location.href='https://github.com/neomorphism/neomo/archive/refs/tags/v2.0.3.zip'"
                >
                  <strong class="text-strong">Download</strong>
                </button>
              </div>
            </li>
            <li id="content-2" class="tab-content--list">
              <div class="tab-content--title"><h2>CDN</h2></div>
              <div class="tab-content--text">
                <client-only>
                  <p>
                    <nuxt-content :document="cdn" />
                  </p>
                </client-only>
              </div>
            </li>
            <li id="content-3" class="tab-content--list">
              <div class="tab-content--title"><h2>Package</h2></div>
              <div class="tab-content--text">
                <client-only>
                  <p>npm, yarn package</p>
                  <p>
                    <nuxt-content :document="doc" />
                  </p>
                </client-only>
              </div>
            </li>
          </ul>
          <ul class="tab-list tab-right">
            <li><a id="tab-1" class="current">Download</a></li>
            <li><a id="tab-2">CDN</a></li>
            <li><a id="tab-3">Package</a></li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const doc = await $content(params.slug || "download/package").fetch();
    const cdn = await $content(params.slug || "download/cdn").fetch();
    return {
      doc,
      cdn,
    };
  },
};
</script>

<style>
.button {
  margin-top: 20px;
}
</style>
