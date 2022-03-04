<template>
    <div class="main">
        <div @click = "cleanData" class=formDone>
            <div class="top-title">
            Персональные данные    
            </div>
            <div class="parent-info">
                    {{name1}}, {{age1}} лет
            </div>
            <div class="bottom-title">
            Дети
            </div>
            <ul>
                <li
                v-for="user in arr" 
                :key="user.name" 
                >
                    <div class="child-info">
                    {{user.name}}, {{user.age}} лет
                    </div>
                </li>
            </ul>
        </div>
        <!--personal component-->
    <div class="personal">
        <div class="title">
            Персональные данные
        </div>
        <div class="inputs">
            <div class="input-block">
                <div class="input-title">Имя</div>
                <input v-model="name1" type="text" class="text-input">
            </div>
            <div class="input-block">
                <div class="input-title">Возраст</div>
                <input v-model="age1" type="text" class="text-input">
            </div>
        </div>
    </div>
        <!--child component-->
        <div class="children">
    <div class="title-main">
      <div class="children-title">Дети (макс. 5)</div>
      <div class="add-children">
        <div class="add-children-text" @click="addSlot">Добавить ребенка</div>
      </div>
    </div>
    <div class="add-delete slot1">
      <div class="input-add">
        <div class="input-add-title">Имя</div>
        <input v-model="names[0].name" type="text" class=child-text>
      </div>
      <div class="input-add">
        <div class="input-add-title">Возраст</div>
        <input v-model="names[0].age" type="text" class="child-text">
      </div>
      <div @click ="deleteSlot1" class="delete">Удалить</div>
    </div> 
    <div class="add-delete slot2">
      <div class="input-add">
        <div class="input-add-title">Имя</div>
        <input v-model="names[1].name" type="text" class=child-text>
      </div>
      <div class="input-add">
        <div class="input-add-title">Возраст</div>
        <input v-model="names[1].age" type="text" class="child-text">
      </div>
      <div @click="deleteSlot2" class="delete">Удалить</div>
    </div> 
    <div class="add-delete slot3">
      <div class="input-add">
        <div class="input-add-title">Имя</div>
        <input v-model="names[2].name" type="text" class=child-text>
      </div>
      <div class="input-add">
        <div class="input-add-title">Возраст</div>
        <input v-model="names[2].age" type="text" class="child-text">
      </div>
      <div @click="deleteSlot3" class="delete">Удалить</div>
    </div> 
    <div class="add-delete slot4">
      <div class="input-add">
        <div class="input-add-title">Имя</div>
        <input v-model="names[3].name" type="text" class=child-text>
      </div>
      <div class="input-add">
        <div class="input-add-title">Возраст</div>
        <input v-model="names[3].age" type="text" class="child-text">
      </div>
      <div @click="deleteSlot4" class="delete">Удалить</div>
    </div> 
    <div class="add-delete slot5">
      <div class="input-add">
        <div class="input-add-title">Имя</div>
        <input v-model="names[4].name" type="text" class=child-text>
      </div>
      <div class="input-add">
        <div class="input-add-title">Возраст</div>
        <input v-model="names[4].age" type="text" class="child-text">
      </div>
      <div @click="deleteSlot5" class="delete">Удалить</div>
    </div> 
    <button @click="saveChanges" class="save">Сохранить</button>
    
  </div>
    </div>
</template>
<script>
export default {
    name:'Main',
    
    data(){
        return {
        name1:'',
        age1:'',
        visibleSlot1: false,
        visibleSlot2: false,
        visibleSlot3: false,
        visibleSlot4: false,
        visibleSlot5: false,
        names:[
        {name:'',age:''},
        {name:'',age:''},
        {name:'',age:''},
        {name:'',age:''},
        {name:'',age:''}
        ],
        arr:[]
        }
    },
    methods:{
    addSlot(){
      const child = document.querySelector('.add-children')
      const slot1 = document.querySelector('.slot1')
      const slot2 = document.querySelector('.slot2')
      const slot3 = document.querySelector('.slot3')
      const slot4 = document.querySelector('.slot4')
      const slot5 = document.querySelector('.slot5')
      if(this.visibleSlot1 == false){
        slot1.style.visibility = 'visible'
        slot1.style.position = 'relative'
        this.visibleSlot1 = true
      }
      else if(this.visibleSlot2 == false){
        slot2.style.visibility = 'visible'
        slot2.style.position = 'relative'
        this.visibleSlot2 = true
        }
      else if(this.visibleSlot3 == false){
        slot3.style.visibility = 'visible'
        slot3.style.position = 'relative'
        this.visibleSlot3 = true
      }
      else if(this.visibleSlot4 == false){
        slot4.style.visibility = 'visible'
        slot4.style.position = 'relative'
        this.visibleSlot4 = true
      }
      else if(this.visibleSlot5 == false){
        slot5.style.visibility = 'visible'
        slot5.style.position = 'relative'
        this.visibleSlot5 = true
      }
      if(this.visibleSlot1==true&&this.visibleSlot2==true&&this.visibleSlot3==true&&this.visibleSlot4==true&&this.visibleSlot5==true){
        child.style.visibility = 'hidden' 
      }
    },
    deleteSlot1(){
      const child = document.querySelector('.add-children')
      const slot1 = document.querySelector('.slot1')
      slot1.style.visibility = 'hidden'
      slot1.style.position = 'absolute'
      this.visibleSlot1 = false
      child.style.visibility = 'visible'
      this.names[0].name = ''
      this.names[0].age = ''
    },
    deleteSlot2(){
      const child = document.querySelector('.add-children')
      const slot2 = document.querySelector('.slot2')
      slot2.style.visibility = 'hidden'
      slot2.style.position = 'absolute'
      this.visibleSlot2 = false
      child.style.visibility = 'visible' 
      this.names[1].name = ''
      this.names[1].age = ''
    },
    deleteSlot3(){
      const child = document.querySelector('.add-children')
      const slot3 = document.querySelector('.slot3')
      slot3.style.visibility = 'hidden'
      slot3.style.position = 'absolute'
      this.visibleSlot3 = false
      child.style.visibility = 'visible' 
      this.names[2].name = ''
      this.names[2].age = ''
    },
    deleteSlot4(){
      const child = document.querySelector('.add-children')
      const slot4 = document.querySelector('.slot4')
      slot4.style.visibility = 'hidden'
      slot4.style.position = 'absolute'
      this.visibleSlot4 = false
      child.style.visibility = 'visible' 
      this.names[3].name = ''
      this.names[3].age = ''
    },
    deleteSlot5(){
      const child = document.querySelector('.add-children')
      const slot5 = document.querySelector('.slot5')
      slot5.style.visibility = 'hidden'
      slot5.style.position = 'absolute'
      this.visibleSlot5 = false
      child.style.visibility = 'visible' 
      this.names[4].name = ''
      this.names[4].age = ''
    },
    saveChanges(){
      const done = document.querySelector('.formDone')
      const parent = document.querySelector('.parent-info')
      const children = document.querySelector('.children')  
      for(let i=0; i < this.names.length; i++){
        if(this.names[i].name != ''){
          this.arr.push(this.names[i])
          
        }
      }
      console.log(this.arr)
        children.style.visibility = 'hidden'
        done.style.visibility = 'visible'
        if(this.name1==''){
            parent.style.visibility = 'hidden'
        }else{
            parent.style.visibility = 'visible'
        }
      const slot1 = document.querySelector('.slot1')
      slot1.style.visibility = 'hidden'
      slot1.style.position = 'absolute'
      const slot2 = document.querySelector('.slot2')
      slot2.style.visibility = 'hidden'
      slot2.style.position = 'absolute'
      const slot3 = document.querySelector('.slot3')
      slot3.style.visibility = 'hidden'
      slot3.style.position = 'absolute'
      const slot4 = document.querySelector('.slot4')
      slot4.style.visibility = 'hidden'
      slot4.style.position = 'absolute'
      const slot5 = document.querySelector('.slot5')
      slot5.style.visibility = 'hidden'
      slot5.style.position = 'absolute'
      const child = document.querySelector('.add-children')
      child.style.visibility = 'visible'
      this.visibleSlot1 = false
      this.visibleSlot2 = false
      this.visibleSlot3 = false
      this.visibleSlot4 = false
      this.visibleSlot5 = false
    },
    cleanData(){
        const children = document.querySelector('.children') 
        const done = document.querySelector('.formDone')  
        for(let i = 0; i< this.names.length; i++){
            if(this.names[i].name != ''){
                this.names[i].name = ''
                this.names[i].age = ''
                this.arr= []
            }
        }
        this.name1 = ''
        this.age1 = ''
        children.style.visibility = 'visible'
        done.style.visibility = 'hidden'
    }    
  },
}
</script>
<style lang="css" scoped>
.main{
    min-height: 80vh;
    flex-direction: column;
    display:flex;
    width:33%;
    min-width:418px;
    margin: 0 32% 20px 32%;
}
.formDone{
    visibility:hidden;
    height:60%;
    width:620px;
    background: #FFF;
    color: rgba(4, 3, 73, 0.48);
    position: absolute;
    z-index: 99;
    top:105px;
}
ul{
    margin: 0;
    padding: 0;
}
li{
    list-style-type: none;
}
.top-title{
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    margin-bottom: 20px;
}
.parent-info{
    font-weight: bold;
    font-size: 16px;
    line-height: 24px;
    margin-bottom:60px;
}
.bottom-title{
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
}
.child-info{
    padding: 10px 20px;
    width: fit-content;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top:20px;
    background: #F1F1F1;
    border-radius: 5px;
    font-weight: bold;
    font-size: 16px;
    line-height: 24px;
}
/* personal */
.personal{
    margin-top:30px;
    display: flex;
    flex-direction: column;
    justify-content: center;
}
.title{
    font-weight: 500;
    font-size: 16px;
    margin-bottom: 20px;
}
.inputs{
    display: flex;
    flex-direction: column;
}
.text-input{
    width: 99%;
    height: 24px;
    border: none;
}
.input-block{
    padding-left: 16px;
    display:flex;
    flex-direction: column;
    justify-content: center;
    border: 1px solid #F1F1F1;
    border-radius: 4px;
    width:97%;
    min-width:400px;
    height:56px;
    margin-bottom: 10px;
}
.input-title{
    color: rgba(4, 3, 73, 0.48);
    font-size: 13px;
    line-height: 16px;
    display: flex;
    justify-content: left;
}
/* children */
.children{
  margin-top:24px;
}
.title-main{
  margin-bottom: 10px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.children-title{
  font-weight: 500;
  font-size: 16px;
}
.add-children{
  cursor: pointer;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  width: 204px;
  height: 44px;
  color: #bb4741;
  border: 2px solid #bb4741;
  border-radius: 100px;
}
.add-children-text{
  font-weight: normal;
  font-size: 14px;
  line-height: 24px;
  margin-left:5px;
}
.add-delete{
  display: flex;
  flex-direction: row;
  margin-bottom:10px;
}
.input-add{
  padding-left:16px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-right: 18px;
  width: 40%;
  height: 56px;
  border: 1px solid #F1F1F1;
  border-radius: 4px;
}
.input-add-title{
  font-size: 13px;
  line-height: 16px;
  color: rgba(17, 17, 17, 0.48);
}
.child-text{
  width:97%;
  height: 24px;
  border:none;
}
.delete{
  cursor: pointer;
  font-weight: normal;
  font-size: 14px;
  line-height: 24px;
  color: #bb4741;
  display: flex;
  align-items: center;
}
.save{
  cursor: pointer;
  margin-top: 20px;
  width: 118px;
  height: 44px;
  border: none;
  background:#bb4741;
  color: #FFFFFF;
  border-radius: 100px;
  font-family: Montserrat;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 24px;
}
.slot1 {
  visibility:hidden;
  position:absolute;
  left:0;
}
.slot2 {
  visibility:hidden;
  position:absolute;
  left:0;
}
.slot3 {
  visibility:hidden;
  position:absolute;
  left:0;
}
.slot4 {
  visibility:hidden;
  position:absolute;
  left:0;
}
.slot5 {
  visibility:hidden;
  position:absolute;
  left:0;
}


</style>