<template>
  <section class="gallery-page">
    <div class="container">
      <div class="row">
        <div
          class="col-xl-4 col-lg-6 col-md-6"
          v-for="item in gallery"
          :key="item.index"
        >
          <GalleryCard
            :title="item.title"
            :thumbnail="item.thumbnail"
            :category="item.category"
          />
        </div>
      </div>
      <!-- /.row -->
    </div>
    <!-- /.container -->
  </section>
  <!-- /.gallery-page -->
</template>
<script>
import GalleryCard from "~/components/GalleryCard";
import data from "~/data/data.json";
export default {
  components: {
    GalleryCard,
  },
  data() {
    return {
      gallery: data.gallery,
    };
  },
};
</script>
