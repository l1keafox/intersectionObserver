<template>
  <div class="font-noto">
    <h1>Hello World</h1>
    <section class="hidden2">
      <h2>Hello Mom</h2>
      <p>This is my Website?</p>
    </section>
    <section class="hidden2">
      <h2>My cats</h2>
      <div class="logos flex">
        <div class="logo hidden2">
          <img
            src="https://images.unsplash.com/photo-1579168765467-3b235f938439?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=688&q=80"
            alt=""
          />
        </div>
        <div class="logo hidden2">
          <img
            src="https://images.unsplash.com/photo-1579168765467-3b235f938439?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=688&q=80"
            alt=""
          />
        </div>
        <div class="logo hidden2">
          <img
            src="https://images.unsplash.com/photo-1579168765467-3b235f938439?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=688&q=80"
            alt=""
          />
        </div>
        <div class="logo hidden2">
          <img
            src="https://images.unsplash.com/photo-1579168765467-3b235f938439?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=688&q=80"
            alt=""
          />
        </div>
      </div>
    </section>
    <section class="hidden2">
      <h2>Yo</h2>
      <p>Yoyoyo</p>
    </section>
    <section class="hidden2">
      <h2>Family</h2>
      <p>Is waht I am</p>
    </section>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  mounted() {
    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        console.log(entry, entry.isIntersecting);
        if (entry.isIntersecting) {
          entry.target.classList.add("show");
        } else {
          entry.target.classList.remove("show");
        }
      });
    });
    const hidden = document.querySelectorAll(".hidden2");
    hidden.forEach((el) => observer.observe(el));
    console.log(hidden);
  },
};
</script>

<style>
body {
  background-color: rgb(20, 20, 20);
  color: rgb(250, 250, 250);
  padding: 0;
  margin: 0;
}
section {
  display: grid;
  place-items: center;
  align-content: center;
  min-height: 100vh;
}
.hidden2 {
  opacity: 0;
  filter: blur(5px);
  transition: all 1s;
  transform: translateX(-100%);
}
.show {
  opacity: 1;
  filter: blur(0);
  transform: translateX(0);
}
.logo{
  width:200px;
}
.logo:nth-child(2){
  transition-delay:  200ms;
}
.logo:nth-child(3){
  transition-delay:  400ms;
}
.logo:nth-child(4){
  transition-delay:  600ms;
}
</style>
