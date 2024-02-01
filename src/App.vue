
<script setup>


    import {ref} from "vue";

    let showModal=ref(false)

    let newNote=ref("")//Two way binding

    const note=ref([])

    const toggleModal=()=>{
      showModal.value=!showModal.value
    }





</script>








<template>
  <main>
    <div class="over" v-if="showModal">
      <div class="modal">
        
        <textarea v-model="newNote" name="note" id="note" cols="60" rows="10"></textarea>
        <button class="modal-button">Add your Note</button>
        <button class="close-button" @click=toggleModal>Close</button>
      </div>
    </div>
    <div class="container">
      <header>
        <h1>NoteBlitz</h1>
        <button @click=toggleModal>+</button>
      </header>
      <div class="cards-container">
        <div class="card">
          <p class="main-text">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Consequuntur rerum itaque, molestias magni non quisquam eius sapiente ratione eligendi, sed, quidem ut tenetur dolores voluptates nostrum deserunt! Id, velit explicabo!
          
          </p>

          <p class="date">29/01/2024</p>
        
        </div>
        <div class="card">
          <p class="main-text">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Consequuntur rerum itaque, molestias magni non quisquam eius sapiente ratione eligendi, sed, quidem ut tenetur dolores voluptates nostrum deserunt! Id, velit explicabo!
          
          </p>

          <p class="date">29/01/2024</p>
        
        </div>
      </div>
    </div>
  </main>
</template>


<style scoped>
    
    main{
      height:100vh;
      width:100vw;
      background-color: #ffffff;
    }

    .container{
      max-width: 1000px;
      padding: 10px;
      margin: 0 auto;
    }

    header{
      display: flex;
      justify-content:space-between;
      align-items: center;
    }

    h1{
      font-weight: 700;
      font-style: oblique;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      color: cornflowerblue

    }

    header button{
      border:none;
      padding:12px;
      width:50px;
      height:50px;
      cursor:pointer;
      background:linear-gradient(#cccccc,#dddddd);
      border-radius: 75%;
    }

    .cards-container{
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
    }

    .card{
      width: 240px;
      height: 240px;
      background-color: rgb(255, 191, 73);
      border-radius: 2.5px;
      display: flex;
      padding-top: 32px;
      padding-bottom: 32px;
      padding-left: 16px;
      padding-right: 16px;
      flex-direction: column;
      justify-content: space-between;
      margin-right: 20px;
      margin-bottom: 20px;
      margin-top: 15px;
      color: black;
      align-content: center;

    }
    .main-text{
      background: none;
      font-size: 10px;
      text-align: justify;
      text-overflow: clip;
    }

    .date{
      font-size: 12px;
      font-weight: bold;
    }

    .over{
      position: absolute;
      width:100%;
      height:100%;
      background-color: rgba(0, 0, 0, 0.7);
      z-index: 6;
      padding: 180px 180px 480px 480px;
      align-items: center;
      justify-content: center;
    }

    .modal{
      width: 500px;
      background-color: azure;
      border-radius: 8px;
      padding: 32px;
      display: flex;
      position: relative;
      flex-direction: column;
      justify-self: center;
    }
    
    .modal-button{
      padding: 10px 20px;
      font-size: 20px;
      margin-top:10px;
      background: linear-gradient(to top right ,blue,navy,blueviolet);
      color:white;
      cursor: pointer;
    }

    .close-button{
      background-color: darkred;
      padding: 10px 20px;
      margin-top: 10px;
      color:white;
      font-size:20px;
      cursor: pointer;
    }
</style>
