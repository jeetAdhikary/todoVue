<template>
    <transition name="modal">
    <div class="modal-mask">
      <div class="modal-wrapper">
        <div class="modal-container">

          <div class="modal-header">
            <slot name="header">
             The Selected Option is :
            </slot>
          </div>

          <div class="modal-body">
            <slot name="body">
              {{selectedOption}}
            </slot>
          </div>

          <div class="modal-footer">
            <slot name="footer">
              <button  class="button" @click="$emit('close')">
                Close Me !
              </button>
            </slot>
          </div>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
    name : 'OptionModal',
    props : {
        selectedOption : String
    }
}
</script>

<style>
    .modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(167, 167, 167, 0.5);
  display: table;
  transition: opacity .3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.modal-container {
  width: 300px;
  margin: 0px auto;
  padding: 20px 30px;
  background-color: #20222b;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
  transition: all .3s ease;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.modal-header {
  margin-top: 0;
  color: #a5afd7;
  font-weight: 500;
  font-size: 2rem;
}

.modal-body {
  margin: 20px 0;
    color: #a5afd7;
  font-weight: 500;
  font-size: 2rem;
}


/*
 * The following styles are auto-applied to elements with
 * transition="modal" when their visibility is toggled
 * by Vue.js.
 *
 * You can easily play with the modal transition by editing
 * these styles.
 */

.modal-enter {
  opacity: 0;
}

.modal-leave-active {
  opacity: 0;
}

.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>
