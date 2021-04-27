<template>
  <div class="container">
    <SideBar
      @show-prev-slide="showPrevSlide()"
      @show-next-slide="showNextSlide()"
    />
    <Content
      :slider-index="sliderIndex"
      :slider-items="sliderItems"
      @set-index="showSlide"
    />

  </div>
</template>
<script>
    import SideBar from "../components/SideBar";
    import Content from "../components/Content";

    export default {
        name: 'App',
        components: {
            SideBar, Content
        },
        data() {
            return {
                sliderIndex: 0,
                sliderItems: [
                    {id: 0, number: "I", img: "img1.jpg"},
                    {id: 1, number: "II", img: "img2.jpg"},
                    {id: 2, number: "III", img: "img3.jpg"},
                    {id: 3, number: "IV", img: "img4.jpg"},
                ]
            }
        },
        methods: {
            showNextSlide() {
                if (this.sliderIndex <= (this.sliderItems.length)) {
                    if (this.sliderIndex === this.sliderItems.length - 1) {
                        this.sliderIndex = 0
                    } else {
                        this.sliderIndex++
                    }
                }
            },
            showPrevSlide() {
                if (this.sliderIndex >= 0) {
                    if (this.sliderIndex === 0) {
                        this.sliderIndex = this.sliderItems.length
                    }
                    this.sliderIndex--
                }
            },
            showSlide(i) {
                this.sliderIndex = i
            }

        }
    }
</script>
<style>
</style>
