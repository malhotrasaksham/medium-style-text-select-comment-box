<template>
  <div class="popup" :style="{top: offsetTop, left: offsetLeft}" ref="popup">
    <span @click="AlertSelectedText">Comment</span>
  </div>
</template>
<script>
export default {
  data() {
    return {
      popupInitialTopOffset: 0,
      popupInitialLeftOffset: 0,
      offsetTop: 0,
      offsetLeft: "-999em",
      selectedText: undefined
    };
  },
  methods: {
    ListenToDocumentSelection() {
      let sel = window.getSelection();
      setTimeout(_ => {
        if (sel && !sel.isCollapsed) {
          this.selectedText = sel.toString();
          if (sel.rangeCount) {
            let range = sel.getRangeAt(0).cloneRange();
            if (range.getBoundingClientRect) {
              var rect = range.getBoundingClientRect();
              let left = rect.left + (rect.right - rect.left) / 2;
              let top = rect.top;

              this.offsetTop = top - this.popupInitialTopOffset - 30 + "px";

              this.offsetLeft = left - this.popupInitialLeftOffset / 2 + "px";
            }
          }
        } else {
          this.offsetLeft = "-999em";
        }
      }, 0);
    },
    AlertSelectedText() {
      alert(`"${this.selectedText}" posted as comment`);
    }
  },
  mounted() {
    this.popupInitialTopOffset = this.$refs.popup.offsetHeight;
    this.popupInitialLeftOffset = this.$refs.popup.offsetWidth;
    console.log(this.popupInitialTopOffset, this.popupInitialLeftOffset);
    window.addEventListener("mouseup", this.ListenToDocumentSelection);
  },
  destroyed() {
    window.removeEventListener("mouseup", this.ListenToDocumentSelection);
  }
};
</script>
<style scoped>
.popup {
  position: absolute;
  color: #FFF;
  background-color: #000;
  padding: 10px;
  border-radius: 5px;
  transform-origin: center, center;
  cursor: pointer;
}
.popup:after {
  content: "";
  border-bottom: 5px solid #000;
  border-right: 5px solid #000;
  border-top: 5px solid transparent;
  border-left: 5px solid transparent;
  position: absolute;
  top: calc(100% - 5px);
  transform: rotate(45deg);
  left: calc(50% - 3px);
}
</style>
