<template>
  <div class="modal fade" :id="modalId" tabindex="-1" :aria-labelledby="modalId + 'Label'" aria-hidden="true">
    <div class="modal-dialog" :class="modalSize">
      <div class="modal-content">
        <div class="modal-header">
          <h1 class="modal-title fs-5" :id="modalId + 'Label'">
            <slot name="modalHeader"></slot>
          </h1>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <slot name="modalBody">
            <p>Use <code>Modal.getOrCreateInstance('#modalId').show() or .hide()</code> to trigger via an @onclick
              function</p>
            <p>Remember to import the required <code>Modal</code> bootstrap modules</p>
          </slot>
        </div>
        <div class="modal-footer">
          <slot name="modalFooter">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary">Save changes</button>
          </slot>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import { AppState } from '../AppState';
import { computed, onMounted } from 'vue';

export default {
  props: {
    modalId: { type: String, required: true },
    modalSize: { type: String, default: '' },
    showHeader: { type: Boolean, default: true },
    showFooter: { type: Boolean, default: false }
  },
  setup() {
    return {}
  }
};
</script>


<style lang="scss" scoped></style>