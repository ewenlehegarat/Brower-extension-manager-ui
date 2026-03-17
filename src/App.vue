<script>
  import json from './assets/data.json'
  import Card from './components/card.vue'

  export default {
    components: { Card },
    data() {
      return {
        myData: json
      }
    }
  }
</script>

<template>
  <nav>
    <img src="./assets/images/logo.svg" alt="logo image" class="logo_image">
    <div class="icon_div">
      <img src="./assets/images/icon-moon.svg" alt="moon icon">
    </div>
  </nav>

  <header>
    <h1 class="text_preset_1">Extensions List</h1>
    <div class="filter">
      <button>All</button>
      <button>Active</button>
      <button>Inactive</button>
    </div>
  </header>

  <main>
    <card
      v-for="item in myData"
      :key="item.id"
      :item="item"
    />
  </main>
</template>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@0,100..900;1,100..900&family=Red+Hat+Text:ital,wght@0,300..700;1,300..700&display=swap');

  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Noto Sans';
  }
  
  :root{
    --Neutral-0: #FBFDFE;
    --Neutral-100: #EEEEEE;
    --Neutral-200: #D6E2F5;
    --Neutral-300: #C6C6C6;
    --Neutral-600: #535868;
    --Neutral-700: #2F364B;
    --Neutral-800: #202535;
    --Neutral-900: #091540;

    --Red-400: #F25C54;
    --Red-500: #DE4840;
    --Red-700: #C7231A;

    --Light-Gradient: linear-gradient(180deg, #EBF2FC 0%, #EEFBF9 100%);
    --Dark-Gradient: linear-gradient(180deg, #04091F 0%, #091540 100%);
  }

  body{
    background: var(--Light-Gradient);
    background-repeat: no-repeat;
    padding: 20px 16px 64px 16px;

    .text_preset_1{
      font-weight: bold;
      font-size: 34px;
      line-height: 100%;
      letter-spacing: -1px;
    }
    .text_preset_2{
      font-weight: bold;
      font-size: 20px;
      line-height: 120%;
      letter-spacing: -0.2px;
    }
    .text_preset_3, .text_preset_4{
      font-weight: 400;
      font-size: 20px;
      line-height: 140%;
      letter-spacing: -0.3px;
    }
    .text_preset_5{
      font-weight: 400;
      font-size: 16px;
      line-height: 140%;
      letter-spacing: -0.5px;
    }
    .text_preset_6{
      font-weight: 500;
      font-size: 16px;
      line-height: 140%;
      letter-spacing: -0.5px;
    }
  }

  #app{
    display: flex;
    flex-direction: column;
    gap: 40px;
  }

  nav{
    padding: 8px 12px;
    background-color: var(--Neutral-0);
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-radius: 10px;

    .icon_div{
      width: 50px;
      height: 50px;
      border-radius: 12px;
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: var(--Neutral-100);
    }
  }

  header{
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 24px;

    .filter{
      display: flex;
      align-items: center;
      gap: 12px;

      button{
        padding: 8px 20px 10px 20px;
        background-color: var(--Neutral-0);
        border: 1px solid var(--Neutral-200);
        border-radius: 50px;
        cursor: pointer;
      }
      button:hover{
        opacity: 70%;
      }
    }
  }

  main{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 12px;

    .card{
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      background-color: var(--Neutral-0);
      padding: 20px;
      height: 200px;
      border-radius: 20px;
      border: 1px solid var(--Neutral-200);
      box-shadow: 0 2px 2px 0 #C2CEE1, 0 1px 5px 1px #C2CEE1;

      .extension_info{
        display: flex;
        gap: 16px;

        .extension_details{
          display: flex;
          flex-direction: column;
          gap: 8px;
        }
      }
      .extension_actions{
        display: flex;
        justify-content: space-between;
        align-items: center;

        button{
          padding: 8px 16px;
          border-radius: 50px;
          background-color: var(--Neutral-0);
          border: 1px solid var(--Neutral-300);
          background-color: var();
        }
        .toggle_button{
          width: 36px;
          height: 20px;
          background-color: var(--Red-700);
          border-radius: 50px;
          display: flex;
          justify-content: end;
          align-items: center;
          padding: 2px;
          
          .circle{
            background-color: var(--Neutral-0);
            width: 16px;
            height: 16px;
            border-radius: 50%;
            box-shadow: 0 1px 3px 0 #0A0D12, 0 1px 2px -1px #0A0D12;
          }
        }
      }
    }
  }

  @media screen  and (min-width: 768px){
    main{
      .card{
        width: 346px;
      }
    }
    header{
      flex-direction: row;
      justify-content: space-between;
    }
  }
  @media screen  and (min-width: 1440px){
    main{
      .card{
        width: 382px;
      }
    }
  }
</style>