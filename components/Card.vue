<template>
  <section>
    <div style="margin-top:2rem;">
      <article class="card block">
        <div class="card-image">
          <figure class="image is-fullheight">
            <img :src="imgsrc" @click="isImageModal = true" />
          </figure>
        </div>
      </article>
    </div>
    <b-modal :active.sync="isImageModal">
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
      isImageModal: false
    };
  }
};
</script>
<style scoped>
.modalimg {
  width: auto;
  max-height: 80vh;
  margin: auto;
}
</style>
