<template>
  <div class="offcanvas" :class="offcanvasPosition" tabindex="-1" :id="offcanvaslId"
    :aria-labelledby="'offcanvaslId' + Label">
    <div class="offcanvas-header">
      <h5 class="offcanvas-title" :id="offcanvaslId + 'Label'">
        <slot name="offcanvasHeader">Offcanvas</slot>
      </h5>
      <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
    </div>
    <div class="offcanvas-body">
      <slot name="offcanvasBody">
        <div>
          Some text as placeholder. In real life you can have the elements you have chosen. Like, text, images, lists,
          etc.
        </div>
        <p>Use <code>Offcanvas.getOrCreateInstance('#modalId').show() or .hide()</code> to trigger via an @onclick
          function </p>
        <p>Remember to import the required <code>Offcanvas</code> bootstrap modules</p>
        <div class="dropdown mt-3">
          <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown">
            Dropdown button
          </button>
          <ul class="dropdown-menu">
            <li><a class="dropdown-item" href="#">Action</a></li>
            <li><a class="dropdown-item" href="#">Another action</a></li>
            <li><a class="dropdown-item" href="#">Something else here</a></li>
          </ul>
        </div>
      </slot>
    </div>
  </div>
</template>


<script>
import { AppState } from '../AppState';
import { computed, onMounted } from 'vue';

export default {
  props: {
    offcanvaslId: { type: String, required: true },
    offcanvaslPosition: { type: String, default: 'offcanvas-start' },
    showHeader: { type: Boolean, default: true },
    showFooter: { type: Boolean, default: false }
  },
  setup() {
    return {}
  }
};
</script>


<style lang="scss" scoped></style>