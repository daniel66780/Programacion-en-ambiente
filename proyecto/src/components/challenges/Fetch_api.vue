<template>
    <!-- <img src="https://pbs.twimg.com/profile_images/1540810647604183046/OhYhwdAi_400x400.jpg"/> -->
     <div class="bg-dark"></div>
    <div class="indecision-container">
        <input type="text" placeholder="Ask a question..." v-model="question"/>
        <!-- <p> Recuerda finalizar con el signo de interrogacion (?)</p>  -->
    </div> 
    <div>
        <h2>{{question}}</h2>
        <h1> SI, no, ... Pensando... </h1> 
        <button  @click="callFetch()">No.</button>
        <ul>
            <li>
            <span>{{apiData}}</span>
            <span>{{ans}}</span>


            <img :src='img'/>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    data(){
      return {
        question: "",
        apiData: {},
        img: "",
        ans: ""
      }
    },
    watch: {
        question(value, oldValue){
            console.log(value, oldValue)
            this.question.includes('?')? this.callFetch():null
        
        }

    },
    methods:{
        async callFetch(){
            const api= await fetch('https://yesno.wtf/api')
            const data= await api.json();
            this.apidData= data
            this.img=data.image
            this.ans=data.answer
            console.log(data)
        }
    }
}

</script>
<style scoped>
    
</style>