<script>
export default {};

const track = document.getElementsByClassName(".imageTrack");

window.onmousedown = (e) => {
  track.dataset.mouseDownAt = e.clientX;
};
window.onmousemove = (e) => {
  const mouseDelta = parseFloat(track.dataset.mouseDownAt) - e.clientX;
  maxdelta = window.innerWidth / 2;

  const percentage = (mouseDelta / maxdelta) * 100;
};
</script>

<template>
  <div class="wrapper">
    <div class="imageTrack" data-mouse-down-at="0">
      <img
        src="https://plus.unsplash.com/premium_photo-1711279433915-d1d87c42c795?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyfHx8ZW58MHx8fHx8"
        alt=""
      />
      <img
        src="https://plus.unsplash.com/premium_photo-1711279433915-d1d87c42c795?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyfHx8ZW58MHx8fHx8"
        alt=""
      />
      <img
        src="https://plus.unsplash.com/premium_photo-1711279433915-d1d87c42c795?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyfHx8ZW58MHx8fHx8"
        alt=""
      />
      <img
        src="https://plus.unsplash.com/premium_photo-1711279433915-d1d87c42c795?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyfHx8ZW58MHx8fHx8"
        alt=""
      />
      <img
        src="https://plus.unsplash.com/premium_photo-1711279433915-d1d87c42c795?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyfHx8ZW58MHx8fHx8"
        alt=""
      />
      <img
        src="https://plus.unsplash.com/premium_photo-1711279433915-d1d87c42c795?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyfHx8ZW58MHx8fHx8"
        alt=""
      />
      <img
        src="https://plus.unsplash.com/premium_photo-1711279433915-d1d87c42c795?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyfHx8ZW58MHx8fHx8"
        alt=""
      />
      <img
        src="https://plus.unsplash.com/premium_photo-1711279433915-d1d87c42c795?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyfHx8ZW58MHx8fHx8"
        alt=""
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
  .imageTrack {
    display: flex;
    gap: 4rem;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(0, -50%);
    img {
      width: 40vmin;
      height: 56vmin;
      object-fit: cover;
      object-position: center;
    }
  }
}
</style>
