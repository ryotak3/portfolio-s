<template>
  <section>
    <div style="margin-top:2rem;">
      <article class="card block">
        <div class="card-image" @click="isImageModal = true">
          <figure class="image">
            <img v-lazy="imgObj" alt />
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
      isImageModal: false,
      imgObj: {
        src: this.imgsrc
      }
    };
  }
};
</script>
<style scoped>
.card {
  background-color: #222222;
}
.modalimg {
  width: auto;
  max-height: 90vh;
  margin: auto;
}
</style>
