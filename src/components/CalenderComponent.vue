<template>
   <div class="container">
    <div class="wrapper">
      <header>
        <p class="currentDate">{{ currentDate }}</p>
        <div class="icons">
          <span class="material-symbols-rounded" @click="changeMonth(-1)">chevron_left</span>
          <span class="material-symbols-rounded" @click="changeMonth(1)">chevron_right </span>
        </div>
      </header>

      <div class="calender">
        <ul class="weeks">
         <li v-for="(week, index) in weeksValue" :key="index">
          {{ week }}
        </li>
        </ul>
        <ul class="days">
          <li>1</li>
          <li>2</li>
          <li>3</li>
          <li>4</li>
          <li>5</li>
          <li>6</li>
          <li>7</li>
          <li>8</li>
          <li>9</li>
          <li>10</li>
          <li>11</li>
          <li>12</li>
          <li>13</li>
          <li>14</li>
          <li>15</li>
          <li>16</li>
          <li>17</li>
          <li>18</li>
          <li>19</li>
          <li>21</li>
          <li>22</li>
          <li>23</li>
          <li>24</li>
          <li>25</li>
          <li>26</li>
          <li>27</li>
          <li>28</li>
          <li>29</li>
          <li>30</li>
          <li>31</li>
        </ul>
      </div>
    </div>
   </div>
</template>

<script>
import { ref } from 'vue'
export default {
  name: 'HelloWorld',
  setup(){

    let weeksValue = ref([
      'Sun', 'Mon', 'Tues ', 'Wed ', 'Thurs ', 'Fri ', 'Sat'
    ]);

    let monthsValue = ref([
    'January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'
    ])

    let date =ref( new Date())
    let currentMonth = ref(  new Date().getMonth() )
    let currentYear = ref(new Date().getFullYear())
    let currentDate = ref('');

    const loadCalender = () =>{
      currentDate.value = `${monthsValue.value[currentMonth.value]} ${currentYear.value}`
      console.warn("Current Month =>",currentDate.value)
    }

    const changeMonth = (changedIndex) =>{
      currentMonth.value += changedIndex;

      if (currentMonth.value < 0 || currentMonth.value > 11) {
        const date = new Date(currentYear.value, currentMonth.value);
        currentYear.value = date.getFullYear();
        currentMonth.value = date.getMonth();
      } else {
        const date = new Date();
      }
      
      loadCalender();
      console.log("Current Month Value=>", currentMonth.value)
    }

    loadCalender();
    console.log(`${date.value},${currentMonth.value},${currentYear.value}`)

    return {
      weeksValue,
      date,
      currentMonth,
      currentYear,
      currentDate,
      monthsValue,
      changeMonth
    }
  }
 
}
</script>

<style >
  .wrapper{
    justify-content: center;
    align-items: center;

    background: #fff;
    border-radius: 1rem;
  }

  header{
    display: flex;
    align-items: center;
    justify-content: space-between;

    padding: 25px 30px 10px;
  }

  header .currentDate{
    font-size: 1.5rem;
    font-weight: 700;
}

  header .icons span{
    height: 40px;
    width: 40px;
    font-size: 2rem;

    cursor: pointer;
    text-align: center;
    line-height: 40px;

    border-radius: 50%;
}

 .calender{
  /* display: inline-block; */
  width: 450px;
  justify-content: center;
  align-items: center;
 }

 .calender ul{
  display: flex;
  list-style: none;
  text-align: center;

  flex-wrap: wrap;
 }

 .calender ul li{
  list-style: none;
  width: calc(100% / 7);
  margin-bottom: 1.3rem;
 }

 .calender .days li{
    margin-top: 30px;
    position: relative;
    cursor: pointer;
    z-index: 1;
}
</style>
