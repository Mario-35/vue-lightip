<template>
  <div role="lightip" :style="{'--lightip-font-size': `${fontSize}px`, '--lightip-color': `${color}` , '--lightip-background-color': `${backgroundColor}` , '--lightip-border': `${borderColor}` }" :lightip-position="position" :lightip-label="label">
    <slot></slot>
  </div>
</template>
<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'Lightip',
  props: {
    color: {
      default: '#ffffff',
      type: String,
    },
    backgroundColor: {
      default:  '#000000',
      type: String,
    },
    borderColor: {
      default: '#000000',
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

[lightip-label][role~="lightip"] {
    position: relative;
  }
  
  [lightip-label][role~="lightip"]::before,
  [lightip-label][role~="lightip"]::after {
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
  
  [lightip-label][role~="lightip"]::before {
    background-size: 100% auto !important;
    content: "";
  }
  
  [lightip-label][role~="lightip"]::after {
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
  
  [lightip-label][role~="lightip"]:hover::before,
  [lightip-label][role~="lightip"]:hover::after,
  [lightip-label][role~="lightip"]:focus::before,
  [lightip-label][role~="lightip"]:focus::after {
    opacity: 1;
    pointer-events: auto;
  }
  
  
  
  /* ------------------------------------------------
    [2] Position Modifiers
  -------------------------------------------------*/
  
  [role~="lightip"][lightip-position|="top"]::before {
    border-left: 8px solid transparent;
    border-right: 8px solid transparent;
    border-top: 8px solid var(--lightip-border, rgba(17, 17, 17, .9));
    margin-bottom: 4px;
  }
  
  [role~="lightip"][lightip-position|="top"]::after {
    margin-bottom: 11px;
  }
  
  [role~="lightip"][lightip-position|="top"]::before {
    transform: translate3d(-50%, 0, 0);
    bottom: 100%;
    left: 50%;
  }
  
  [role~="lightip"][lightip-position|="top"]:hover::before {
    transform: translate3d(-50%, -5px, 0);
  }
  
  [role~="lightip"][lightip-position|="top"]::after {
    transform: translate3d(-50%, 0, 0);
    bottom: 100%;
    left: 50%;
  }
  
  [role~="lightip"][lightip-position="top"]:hover::after {
    transform: translate3d(-50%, -5px, 0);
  }
  
  /* ------------------------------------------------
    [2.1] Top Left
  -------------------------------------------------*/
  [role~="lightip"][lightip-position="top-left"]::after {
    transform: translate3d(calc(-100% + 16px), 0, 0);
    bottom: 100%;
  }
  
  [role~="lightip"][lightip-position="top-left"]:hover::after {
    transform: translate3d(calc(-100% + 16px), -5px, 0);
  }
  
  
  /* ------------------------------------------------
    [2.2] Top Right
  -------------------------------------------------*/
  [role~="lightip"][lightip-position="top-right"]::after {
    transform: translate3d(calc(0% + -16px), 0, 0);
    bottom: 100%;
  }
  
  [role~="lightip"][lightip-position="top-right"]:hover::after {
    transform: translate3d(calc(0% + -16px), -5px, 0);
  }
  
  
  /* ------------------------------------------------
    [2.3] Bottom
  -------------------------------------------------*/
  [role~="lightip"][lightip-position|="bottom"]::before {
    border-left: 8px solid transparent;
    border-right: 8px solid transparent;
    border-bottom: 8px solid var(--lightip-border, rgba(17, 17, 17, .9));
    margin-top: 4px;
  }
  
  [role~="lightip"][lightip-position|="bottom"]::after {
    margin-top: 11px;
  }
  
  [role~="lightip"][lightip-position|="bottom"]::before {
    transform: translate3d(-50%, -10px, 0);
    bottom: auto;
    left: 50%;
    top: 100%;
  }
  
  [role~="lightip"][lightip-position|="bottom"]:hover::before {
    transform: translate3d(-50%, 0, 0);
  }
  
  [role~="lightip"][lightip-position|="bottom"]::after {
    transform: translate3d(-50%, -10px, 0);
    top: 100%;
    left: 50%;
  }
  
  [role~="lightip"][lightip-position="bottom"]:hover::after {
    transform: translate3d(-50%, 0, 0);
  }
  
  
  /* ------------------------------------------------
    [2.4] Bottom Left
  -------------------------------------------------*/
  [role~="lightip"][lightip-position="bottom-left"]::after {
    transform: translate3d(calc(-100% + 16px), -10px, 0);
    top: 100%;
  }
  
  [role~="lightip"][lightip-position="bottom-left"]:hover::after {
    transform: translate3d(calc(-100% + 16px), 0, 0);
  }
  
  
  /* ------------------------------------------------
    [2.5] Bottom Right
  -------------------------------------------------*/
  [role~="lightip"][lightip-position="bottom-right"]::after {
    transform: translate3d(calc(0% + -16px), -10px, 0);
    top: 100%;
  }
  
  [role~="lightip"][lightip-position="bottom-right"]:hover::after {
    transform: translate3d(calc(0% + -16px), 0, 0);
  }
  
  
  /* ------------------------------------------------
    [2.6] Left
  -------------------------------------------------*/
  [role~="lightip"][lightip-position="left"]::before,
  [role~="lightip"][lightip-position="left"]::after {
    bottom: auto;
    left: auto;
    right: 100%;
    top: 50%;
    transform: translate3d(10px, -50%, 0);
  }
  
  [role~="lightip"][lightip-position="left"]::before {
    border-left: 8px solid var(--lightip-border, rgba(17, 17, 17, .9));
    border-top: 8px solid transparent;
    border-bottom: 8px solid transparent;
    margin-right: 4px;
  }
  
  [role~="lightip"][lightip-position="left"]::after {
    margin-right: 11px;
  }
  
  [role~="lightip"][lightip-position="left"]:hover::before,
  [role~="lightip"][lightip-position="left"]:hover::after {
    transform: translate3d(0, -50%, 0);
  }
  
  
  /* ------------------------------------------------
    [2.7] Right
  -------------------------------------------------*/
  [role~="lightip"][lightip-position="right"]::before,
  [role~="lightip"][lightip-position="right"]::after {
    bottom: auto;
    left: 100%;
    top: 50%;
    transform: translate3d(-10px, -50%, 0);
  }
  
  [role~="lightip"][lightip-position="right"]::before {
    border-right: 8px solid var(--lightip-border, rgba(17, 17, 17, .9));
    border-top: 8px solid transparent;
    border-bottom: 8px solid transparent;
    margin-left: 4px;
  }
  
  [role~="lightip"][lightip-position="right"]::after {
    margin-left: 11px;
  }
  
  [role~="lightip"][lightip-position="right"]:hover::before,
  [role~="lightip"][lightip-position="right"]:hover::after {
    transform: translate3d(0, -50%, 0);
  }
  
  /* ------------------------------------------------
    [3] Size
  -------------------------------------------------*/
  [role~="lightip"][lightip-size="small"]::after {
    white-space: initial;
    width: 80px;
  }
  
  [role~="lightip"][lightip-size="medium"]::after {
    white-space: initial;
    width: 150px;
  }
  
  [role~="lightip"][lightip-size="large"]::after {
    white-space: initial;
    width: 260px;
  }
</style>
