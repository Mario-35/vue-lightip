<template>
  <div class="lightip" :class="calcsize > 0 ? 'sized' : ''"  :lightip-position="position" :style="styles" :lightip-label="label">
    <slot></slot>
  </div>
</template>
<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Lightip",
  computed: {
    calcsize(): number {
      let width: number = 0;
      switch (this.size) {
        case "small":
          width = 0;
          break;
        case "medium":
          width = 150;
          break;
        case "large":
          width = 260;
          break;
        default:
          width = Number(this.size);
      }
      return width;
    },
    styles(): object {
      return {
        "--lightip-font-size": `${this.fontSize}px`,
        "--lightip-background-color": `${this.backgroundColor}` ,
        "--lightip-border": `${this.borderColor}`,
        "--lightip-color": `${this.color}` ,
        "--lightip-width": `${this.calcsize}px` ,
      };
    },
  },
  props: {
    color: {
      default: "#ffffff",
      type: String,
    },
    backgroundColor: {
      default:  "#000000",
      type: String,
    },
    borderColor: {
      default: "#000000",
      type: String,
    },
    size: {
      default: "small",
      type: String,
    },
    fontSize: String,
    label: String,
    position: String,
  },
});
</script>
<style scoped>
/* -------------------------------------------------------------------
  lightip
  ightweight css-only
  Just 1kb minified and gzipped
  @adam mario
----------------------------------------------------------------------
  1. Start Styles
  2. Direction Modifiers
  3. Position Modifiers
--------------------------------------------------------------------*/


/* ------------------------------------------------
  [1] Start Styles
-------------------------------------------------*/

.lightip {
    position: relative;
  }
  
  .lightip::before,
  .lightip::after {
    transform: translate3d(0, 0, 0);
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
    will-change: transform;
    opacity: 0;
    pointer-events: none;
    transition: all .18s ease-in-out 0s;
    position: absolute;
    box-sizing: border-box;
    z-index: 10;
    transform-origin: top;
  }
  
  .lightip::before {
    background-size: 100% auto !important;
    content: "";
  }
  
  .lightip::after {
    background:  var(--lightip-background-color, rgba(17, 17, 17, 0.842));
    border: 1px solid var(--lightip-border, rgba(17, 17, 17, .9));
    border-radius: 4px;
    color: var(--lightip-color, #ffffff);
    content: attr(lightip-label);
    font-size: var(--lightip-font-size, 12px);
    text-transform: none;
    padding: .5em 1em;
    white-space: nowrap;
    box-sizing: content-box;
  }
  
  .lightip:hover::before,
  .lightip:hover::after,
  .lightip:focus::before,
  .lightip:focus::after {
    opacity: 1;
    pointer-events: auto;
  }
  
  
  
  /* ------------------------------------------------
    [2] Position Modifiers
  -------------------------------------------------*/
  
.lightip[lightip-position|="top"]::before {
    border-left: 8px solid transparent;
    border-right: 8px solid transparent;
    border-top: 8px solid var(--lightip-border, rgba(17, 17, 17, .9));
    margin-bottom: 4px;
  }
  
.lightip[lightip-position|="top"]::after {
    margin-bottom: 11px;
  }
  
.lightip[lightip-position|="top"]::before {
    transform: translate3d(-50%, 0, 0);
    bottom: 100%;
    left: 50%;
  }
  
.lightip[lightip-position|="top"]:hover::before {
    transform: translate3d(-50%, -5px, 0);
  }
  
.lightip[lightip-position|="top"]::after {
    transform: translate3d(-50%, 0, 0);
    bottom: 100%;
    left: 50%;
  }
  
.lightip[lightip-position="top"]:hover::after {
    transform: translate3d(-50%, -5px, 0);
  }
  
  /* ------------------------------------------------
    [2.1] Top Left
  -------------------------------------------------*/
.lightip[lightip-position="top-left"]::after {
    transform: translate3d(calc(-100% + 16px), 0, 0);
    bottom: 100%;
  }
  
.lightip[lightip-position="top-left"]:hover::after {
    transform: translate3d(calc(-100% + 16px), -5px, 0);
  }
  
  
  /* ------------------------------------------------
    [2.2] Top Right
  -------------------------------------------------*/
.lightip[lightip-position="top-right"]::after {
    transform: translate3d(calc(0% + -16px), 0, 0);
    bottom: 100%;
  }
  
.lightip[lightip-position="top-right"]:hover::after {
    transform: translate3d(calc(0% + -16px), -5px, 0);
  }
  
  
  /* ------------------------------------------------
    [2.3] Bottom
  -------------------------------------------------*/
.lightip[lightip-position|="bottom"]::before {
    border-left: 8px solid transparent;
    border-right: 8px solid transparent;
    border-bottom: 8px solid var(--lightip-border, rgba(17, 17, 17, .9));
    margin-top: 4px;
  }
  
.lightip[lightip-position|="bottom"]::after {
    margin-top: 11px;
  }
  
.lightip[lightip-position|="bottom"]::before {
    transform: translate3d(-50%, -10px, 0);
    bottom: auto;
    left: 50%;
    top: 100%;
  }
  
.lightip[lightip-position|="bottom"]:hover::before {
    transform: translate3d(-50%, 0, 0);
  }
  
.lightip[lightip-position|="bottom"]::after {
    transform: translate3d(-50%, -10px, 0);
    top: 100%;
    left: 50%;
  }
  
.lightip[lightip-position="bottom"]:hover::after {
    transform: translate3d(-50%, 0, 0);
  }
  
  
  /* ------------------------------------------------
    [2.4] Bottom Left
  -------------------------------------------------*/
.lightip[lightip-position="bottom-left"]::after {
    transform: translate3d(calc(-100% + 16px), -10px, 0);
    top: 100%;
  }
  
.lightip[lightip-position="bottom-left"]:hover::after {
    transform: translate3d(calc(-100% + 16px), 0, 0);
  }
  
  
  /* ------------------------------------------------
    [2.5] Bottom Right
  -------------------------------------------------*/
.lightip[lightip-position="bottom-right"]::after {
    transform: translate3d(calc(0% + -16px), -10px, 0);
    top: 100%;
  }
  
.lightip[lightip-position="bottom-right"]:hover::after {
    transform: translate3d(calc(0% + -16px), 0, 0);
  }
  
  
  /* ------------------------------------------------
    [2.6] Left
  -------------------------------------------------*/
.lightip[lightip-position="left"]::before,
.lightip[lightip-position="left"]::after {
    bottom: auto;
    left: auto;
    right: 100%;
    top: 50%;
    transform: translate3d(10px, -50%, 0);
  }
  
.lightip[lightip-position="left"]::before {
    border-left: 8px solid var(--lightip-border, rgba(17, 17, 17, .9));
    border-top: 8px solid transparent;
    border-bottom: 8px solid transparent;
    margin-right: 4px;
  }
  
.lightip[lightip-position="left"]::after {
    margin-right: 11px;
  }
  
.lightip[lightip-position="left"]:hover::before,
.lightip[lightip-position="left"]:hover::after {
    transform: translate3d(0, -50%, 0);
  }
  
  
  /* ------------------------------------------------
    [2.7] Right
  -------------------------------------------------*/
.lightip[lightip-position="right"]::before,
.lightip[lightip-position="right"]::after {
    bottom: auto;
    left: 100%;
    top: 50%;
    transform: translate3d(-10px, -50%, 0);
  }
  
.lightip[lightip-position="right"]::before {
    border-right: 8px solid var(--lightip-border, rgba(17, 17, 17, .9));
    border-top: 8px solid transparent;
    border-bottom: 8px solid transparent;
    margin-left: 4px;
  }
  
.lightip[lightip-position="right"]::after {
    margin-left: 11px;
  }
  
.lightip[lightip-position="right"]:hover::before,
.lightip[lightip-position="right"]:hover::after {
    transform: translate3d(0, -50%, 0);
  }
  
  /* ------------------------------------------------
    [3] Size
  -------------------------------------------------*/
.sized::after {
    white-space: initial;
    width: var(--lightip-width);
  }
  
</style>
