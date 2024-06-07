<script>
export default {};
document.addEventListener("DOMContentLoaded", () => {
  const boxes = document.querySelectorAll(".box");
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add("visible");
      } else if (!entry.isIntersecting) {
        entry.target.classList.remove("visible");
      }
    });
  });

  boxes.forEach((box) => observer.observe(box));
});
</script>

<template>
  <div class="box-wrapper d-flex flex-column align-items-center">
    <div class="box d-flex justify-content-center align-items-center m-3">
      box
    </div>
    <div class="box d-flex justify-content-center align-items-center m-3">
      box
    </div>
    <div class="box d-flex justify-content-center align-items-center m-3">
      box
    </div>
    <div class="box d-flex justify-content-center align-items-center m-3">
      box
    </div>
    <div class="box d-flex justify-content-center align-items-center m-3">
      box
    </div>
    <div class="box d-flex justify-content-center align-items-center m-3">
      box
    </div>
    <div class="box d-flex justify-content-center align-items-center m-3">
      box
    </div>
    <div class="box d-flex justify-content-center align-items-center m-3">
      box
    </div>
    <div class="box d-flex justify-content-center align-items-center m-3">
      box
    </div>
    <div class="box d-flex justify-content-center align-items-center m-3">
      box
    </div>
    <div class="box d-flex justify-content-center align-items-center m-3">
      box
    </div>
    <div class="box d-flex justify-content-center align-items-center m-3">
      box
    </div>
  </div>
</template>

<style scoped lang="scss">
@keyframes appear {
  from {
    opacity: 0;
    transform: scale(0.5);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}
.box {
  height: 100px;
  width: 100px;
  background-color: red;
  opacity: 0; /* Start hidden */
  transform: scale(0.5); /* Start scaled down */
  transition: opacity 0.5s, transform 0.5s; /* Smooth transition for appearance */
}
.box.visible {
  opacity: 1; /* Become visible */
  transform: scale(1); /* Return to original size */
  animation: appear 0.5s linear; /* Apply the animation */
}
</style>
