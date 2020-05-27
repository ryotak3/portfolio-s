<template>
  <section>
    <div style="margin-top:2rem;">
      <div class="card-image" @click="isImageModal = true">
        <figure class="image">
          <img v-lazy="imgObj" class="thumbimg" alt />
        </figure>
      </div>
    </div>
    <b-modal :active.sync="isImageModal" :width="modalwidth">
      <figure class="image">
        <img class="modalimg" :src="imgsrc" />
      </figure>
    </b-modal>
  </section>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      default: ''
    },
    id: {
      type: String,
      default: ''
    },
    date: {
      type: String,
      default: ''
    },
    imgsrc: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
      isImageModal: false,
      imgObj: {
        src: this.imgsrc
      },
      modalwidth: 1280
    };
  }
};
</script>
<style scoped>
.thumbimg {
  max-height: 30vh;
  width: auto;
  margin: 0 auto;
}
.modalimg {
  width: auto;
  max-height: 90vh;
  margin: 0 auto;
}
</style>
