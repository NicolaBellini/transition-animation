<script>
export default {
  data() {
    return {
      images: [
        "https://plus.unsplash.com/premium_photo-1711279433915-d1d87c42c795?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyfHx8ZW58MHx8fHx8",
        "https://images.unsplash.com/photo-1717321677309-8916f9b0a1d6?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwzfHx8ZW58MHx8fHx8",
        "https://images.unsplash.com/photo-1687785929471-316cb4f1eb57?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDF8fHxlbnwwfHx8fHw%3D",
        "https://images.unsplash.com/photo-1698933787104-3f91cf25909c?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDd8fHxlbnwwfHx8fHw%3D",
        "https://images.unsplash.com/photo-1697299262049-e9b5fa1e9761?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE4fHx8ZW58MHx8fHx8",
        "https://images.unsplash.com/photo-1717364742946-77a41248020a?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
        "https://images.unsplash.com/photo-1662698721165-01ea389ed345?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDV8fHxlbnwwfHx8fHw%3D",
        "https://images.unsplash.com/photo-1636071659663-ec2b71f83a79?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE5fHx8ZW58MHx8fHx8",
      ],
    };
  },
  mounted() {
    const track = document.getElementById("imageTrack");

    window.onmousedown = (e) => {
      track.dataset.mouseDownAt = e.clientX;
    };

    window.onmousemove = (e) => {
      if (track.dataset.mouseDownAt === "0") return;

      const mouseDelta = parseFloat(track.dataset.mouseDownAt) - e.clientX;
      const maxDelta = window.innerWidth / 2;

      const percentage = (mouseDelta / maxDelta) * -100,
        nextPercentageUnconstrained =
          parseFloat(track.dataset.prevPercentage) + percentage,
        nextPercentage = Math.max(
          Math.min(nextPercentageUnconstrained, 0),
          -100
        );

      track.dataset.percentage = nextPercentage;

      track.animate(
        { transform: `translate(${nextPercentage}%, -50%)` },
        { duration: 1200, fill: "forwards" }
      );

      for (const image of track.getElementsByClassName("image")) {
        image.animate(
          { objectPosition: `${nextPercentage + 100}% center` },
          { duration: 1200, fill: "forwards" }
        );
      }
    };

    window.onmouseup = () => {
      track.dataset.mouseDownAt = "0";
      track.dataset.prevPercentage = track.dataset.percentage;
    };
  },
};
</script>

<template>
  <div class="wrapper">
    <div id="imageTrack" data-mouse-down-at="0" data-prev-percentage="0">
      <img
        v-for="(image, index) in images"
        :key="index"
        :src="image"
        alt=""
        draggable="false"
        class="image"
      />
    </div>
  </div>
</template>

<style scoped lang="scss">
.wrapper {
  height: 100vh;
  width: 100vw;
  background-color: black;
  margin: 0;
  overflow: hidden;
  position: relative;
  #imageTrack {
    display: flex;
    gap: 4rem;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(0, -50%);
    .image {
      width: 40vmin;
      height: 56vmin;
      object-fit: cover;
      object-position: 100% center;
    }
  }
}
</style>
