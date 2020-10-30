<template>
  <div class="hello">
    <div class="date-picker" v-on:click="showDatePicker">
      {{ choiceMonth ? choiceMonth + " " + now : ''}} 
    </div>
    <div class="dateoption" id="f_date" v-if="isShow">
        <div class="formdate">
          <div class="year"> 
            <div class="btn"  @click="prev" ><</div>
            <div class="" >{{ now }}</div>
            <div class="btn"  @click="next" >></div>
          </div>
          <div class="date">
            <!-- <div v-bind:key="d" v-for="d in date" class="btnDate">{{ d }}</div> -->
            <div v-bind:key="m" v-for="m in month" @click="choose(m)" class="btnMonth">{{ m }}</div>
          </div>
        </div>
    </div>
    <router-link :to="{ path: '/direc', query: {myprop: query}}">Direc</router-link>
  </div>
 
</template>

<script>
export default {
  name: 'HelloWorld',
  
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      isShow : false,
      isHide : true,
      now: 2020,
      date : [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17,18,19,20,21,22,23,24,25,26,27,28,29,30],
      month : ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
      choiceMonth : null,
      isDisable: true,
      query: 'abc'
    }
  },
  // mounted : function() {
  //     window.onclick = function(event){
  //       let modal = document.getElementById("f_date");
  //       console.log(event.target," ",modal);
  //       if (event.target === modal) {
  //          console.log(modal);
  //         modal.style.display = "none";
  //       }
  //     }
  // },
  methods: {
    showDatePicker : function () {
      this.isShow = !this.isShow;
      this.isHide = !this.isHide;
      console.log(this.now);
    },
    next : function () {
      const current = new Date().getFullYear();
      if (current > this.now) {
        this.now++;
      }
    },
    prev : function () {
      this.now--;
    },
    choose : function (month) {
      this.choiceMonth = month;
      this.isShow = false;
    }
  }
}

      
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .date-picker {
    background-color: beige;
    width: 360px;
    height: 40px;
    border-radius: 15px;
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .dateoption {
    background-color: rgb(250, 250, 250);
    min-width: 360px;
    max-width: 250px;
    height: auto;
    position: relative;
    display: inline-block;
    top: 40px;
    padding: 10px;
    border-radius: 15px;
    border: 1px solid gray;
  }

  .prevyear {
    display: none;
  }

  .nextyear {
    display: none;
  }

  .btn {
    cursor: pointer;
    width: 25px;
    height: 25px;
    border-radius: 5px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 5px 0 5px;
  }

  .btn:hover {
    background-color: rgb(224, 221, 221);
  }

  .date {
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-start;
    margin-top: 10px;
  }

  .date .btnDate {
    width: 13px;
    height: 13px;
    background-color: white;
    display: flex;
    color: white;
    justify-content: center;
    align-items: center;
    padding: 0;
    margin: 5px;
    cursor: pointer;
    border-radius: 5px;
    padding: 5px;
    font-size: 12px;
  }

  .btnDate:hover {
    background-color: rgb(199, 199, 199);
  }

  .year {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .btnMonth {
    background: white;
    max-width: 100px;
    min-width: 72px;
    padding: 0 5px;
    margin: 0px 0px 5px 5px;
    height: 30px;
    cursor: pointer;
    border-radius: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 13px;
    border: 1px solid gray;
  }

  .btnMonth:hover {
    background-color: rgb(228, 222, 222);
  }


</style>
