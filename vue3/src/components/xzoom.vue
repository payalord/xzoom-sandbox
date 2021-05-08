<template>
  <div style="text-align: center">
    <div
      v-if="images.length"
      style="border: 1px solid #ccc; display: inline-block; line-height: 0"
    >
      <img
        class="xzoom"
        :src="images[0].preview"
        :xoriginal="images[0].original"
      />
    </div>

    <div v-if="images.length > 1" style="margin-top: 10px">
      <a
        v-for="(i, k) in images"
        :key="'xzoom-gallery-' + k"
        :href="i.original"
        style="display: inline-block"
      >
        <img
          class="xzoom-gallery"
          width="68"
          :src="i.thumb"
          :xpreview="i.preview"
        />
      </a>
    </div>
  </div>
</template>

<script>
import jQuery from "jquery";
const $ = jQuery;
window.$ = window.jQuery = jQuery;
require("xzoom");

export default {
  name: "xzoom",
  props: {
    images: {
      type: Array,
      default: () => [],
      required: true,
    },
    options: {
      type: Object,
      default: () => {},
    },
  },
  mounted() {
    this.$nextTick(() => {
      $(".xzoom, .xzoom-gallery").xzoom(this.options);
    });
  },
};
</script>

<style>
/* Compatibility styles for frameworks like bootstrap, foundation e.t.c */
.xzoom-source img,
.xzoom-preview img,
.xzoom-lens img {
  display: block;
  max-width: none;
  max-height: none;
  -webkit-transition: none;
  -moz-transition: none;
  -o-transition: none;
  transition: none;
}
/* --------------- */

/* xZoom Styles below */
.xzoom-container {
  display: inline-block;
}

.xzoom-thumbs {
  text-align: center;
  margin-bottom: 10px;
}

.xzoom {
  -webkit-box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.5);
  -moz-box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.5);
  box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.5);
}
.xzoom2,
.xzoom3,
.xzoom4,
.xzoom5 {
  -webkit-box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.5);
  -moz-box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.5);
  box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.5);
}

/* Thumbs */
.xzoom-gallery,
.xzoom-gallery2,
.xzoom-gallery3,
.xzoom-gallery4,
.xzoom-gallery5 {
  border: 1px solid #cecece;
  margin-left: 5px;
  margin-bottom: 10px;
}

.xzoom-source,
.xzoom-hidden {
  display: block;
  position: static;
  float: none;
  clear: both;
}

/* Everything out of border is hidden */
.xzoom-hidden {
  overflow: hidden;
}

/* Preview */
.xzoom-preview {
  border: 1px solid #888;
  background: #2f4f4f;
  box-shadow: -0px -0px 10px rgba(0, 0, 0, 0.5);
}

/* Lens */
.xzoom-lens {
  border: 1px solid #555;
  box-shadow: -0px -0px 10px rgba(0, 0, 0, 0.5);
  cursor: crosshair;
}

/* Loading */
.xzoom-loading {
  background-position: center center;
  background-repeat: no-repeat;
  border-radius: 100%;
  opacity: 0.7;
  background: url(../assets/images/xloading.gif);
  width: 48px;
  height: 48px;
}

/* Additional class that applied to thumb when it is active */
.xactive {
  -webkit-box-shadow: 0px 0px 3px 0px rgba(74, 169, 210, 1);
  -moz-box-shadow: 0px 0px 3px 0px rgba(74, 169, 210, 1);
  box-shadow: 0px 0px 3px 0px rgba(74, 169, 210, 1);
  border: 1px solid #4aaad2;
}

/* Caption */
.xzoom-caption {
  position: absolute;
  bottom: -43px;
  left: 0;
  background: #000;
  width: 100%;
  text-align: left;
}

.xzoom-caption span {
  color: #fff;
  font-family: Arial, sans-serif;
  display: block;
  font-size: 0.75em;
  font-weight: bold;
  padding: 10px;
}
</style>
