<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div class="content">


    <button @click="modalOpen">Modal</button>

    <div class="modal-wrap" v-show="modalCheck" @click="modalOpen">
      <div class="modal-container" @click.stop="">
        <h3>Modal Title</h3>
        <p><strong>Modal Content</strong> Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.</p>
        <div class="modal-btn">
          <button @click="modalOpen">닫기</button>
          <button @click="modalOpen">확인</button>
        </div>
      </div>
    </div>


  </div>
  <div class="content2"></div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      modalCheck: false,
    }
  },
  watch: {
    modalCheck: function () {
      const html = document.querySelector('.html-overflow');
      if( this.modalCheck === true ){
        html.style.overflow = 'hidden'
      } else {
        html.style.overflow = 'auto'
      }
    },
  },
  methods: {
    modalOpen() {
      this.modalCheck = !this.modalCheck
    }
  }
}
</script>

<style>
html {
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}
html::-webkit-scrollbar {
  display: none; /* Chrome, Safari, Opera*/
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.content {
  margin: 30px;
  height: 232px;
}
.content2 {
  height: 100vh;
  background: #eee;
}
button {
  transition: all .3s ease-out;
  cursor: pointer;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 120px;
  height: 50px;
  border-radius: 10px;
  background: #42b983;
  color: #f3f5f7;
  border: none;
  font-size: 20px;
  font-weight: 500;
}
button:hover {
  background: #3aa273;
}



/* Modal */
.modal-wrap {
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.4);
}
.modal-container {
  position: relative;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 550px;
  background: #fff;
  border-radius: 10px;
  padding: 20px;
  box-sizing: border-box;
}
h3 {
  font-size: 30px;
  padding: 20px 0;
  border-bottom: 1px solid #ddd;
  margin: 0;
}
p {
  padding: 20px 0;
}
.modal-btn {
  padding-top: 10px;
  display: flex;
  gap: 10px;
}
.modal-btn button {
  width: 100%;
}
.modal-btn button:first-child {
  background: #78a691;
}
.modal-btn button:last-child {
  background: #3d735b;
}
</style>
