<template>
  <div class="main">
    <hr/>
    <h3>Form</h3>
    <hr/>
    <form @submit="onSubmitEvent">
      <table>
        <thead>
          <tr><th>Type</th><th>Output</th><th>Value</th></tr>
        </thead>
        <tbody>
          <tr>
            <td>input/text</td>
            <td><input type='text' v-model="inputText" /></td>
            <td>{{inputText}}</td>
          </tr>
          <tr>
            <td>input/checkbox</td>
            <td><input type='checkbox' v-model="inputCheckbox" /></td>
            <td>{{inputCheckbox}}</td>
          </tr>
          <tr>
            <td>input/color</td>
            <td><input type='color' v-model="inputColor" /></td>
            <td>{{inputColor}}</td>
          </tr>
          <tr>
            <td>input/date</td>
            <td><input type='date' v-model="inputDate" /></td>
            <td>{{inputDate}}</td>
          </tr>
          <tr>
            <td>input/datetime-local</td>
            <td><input type='datetime-local' v-model="inputDatetimeLocal" /></td>
            <td>{{inputDatetimeLocal}}</td>
          </tr>
          <tr>
            <td>input/email</td>
            <td><input type='email' v-model="inputEmail" /></td>
            <td>{{inputEmail}}</td>
          </tr>
          <tr>
            <td>input/image</td>
            <td><input type='image' :src="inputImage" width="20" height="20" alt="18NG" /></td>
            <td><input type='button' value='Change' 
              @click="()=>{inputImage===require('@/assets/cloud_1.png')?inputImage=require('@/assets/cloud_2.png'):inputImage=require('@/assets/cloud_1.png')}" /></td>
          </tr>
          <tr>
            <td>input/month</td>
            <td><input type='month' v-model="inputMonth" /></td>
            <td>{{inputMonth}}</td>
          </tr>
          <tr>
            <td>input/number</td>
            <td><input type='number' v-model="inputNumber" /></td>
            <td>{{inputNumber}}</td>
          </tr>
          <tr>
            <td>input/password</td>
            <td><input type='password' v-model="inputPassword" /></td>
            <td>{{inputPassword}}</td>
          </tr>
          <tr>
            <td>input/radio</td>
            <td>
              <div v-for="item in radioItems" :key="item.value"  :style="`display:inline;`">
                <input type="radio" :id="item.value" name='AB' :value="item.value" 
                  @click="(e)=>{inputRadio=e.target.value;}" 
                  :checked="inputRadio===item.value"/>
                <label :htmlFor="item.value">{{item.label}}</label>
              </div>
            </td>
            <td>{{inputRadio}}</td>
          </tr>
          <tr>
            <td>input/range</td>
            <td><input type='range' min="0" max="99" v-model="inputRange" /></td>
            <td>{{inputRange}}</td>
          </tr>
          
          <tr>
            <td>input/file</td>
            <td><input type='file' @change="upFile"/></td>
            <td>{{fileInfo}}</td>
          </tr>
          <tr>
            <td>input/button</td>
            <td><input type='button' value='Button' @click="onClickButtonEvent" /></td>
            <td>None</td>
          </tr>
          <tr>
            <td>input/submit</td>
            <td><input type='submit' value='Submit' /></td>
            <td>None</td>
          </tr>
          <tr>
            <td>select</td>
            <td>
              <select v-model="select">
                <option value="a">AAA</option>
                <option value="b">BBB</option>
              </select>
            </td>
            <td>{{select}}</td>
          </tr>
          <tr>
            <td>textarea</td>
            <td><textarea v-model="textArea"></textarea></td>
            <td>{{textArea}}</td>
          </tr>
        </tbody>
      </table>
      <hr/>
    </form>   
  </div>    
</template>

<script>

export default {
  name: 'App',
  components: {
    
  },
  data() {
    return {
      inputText: 'text', 
      inputCheckbox: true, 
      inputColor: '#e66465', 
      inputDate: '2023-03-14', 
      inputDatetimeLocal: '2023-03-14T19:30', 
      inputEmail: 'abcde@zzzzz.com', 
      inputImage: require('@/assets/cloud_1.png'), 
      inputMonth: '2023-03', 
      inputNumber: '110', 
      inputPassword: 'password', 
      radioItems: [{label:'A',value:'a'},{label:'B',value:'b'}],
      inputRadio: 'b', 
      inputRange: 55,
      inputFiles: [],
      select: 'a',
      textArea: 'Line1\nLine2'
    }
  },
  methods: {
    onSubmitEvent: function() {
      alert('Detected onSubmit Event.');
    },
    onClickButtonEvent: function() {
      alert('Detected onClickButton Event.');
    },
    upFile: function(e) {
      this.inputFiles = [];
      this.inputFiles.push(e.target.files[0]);
    }
  },
  computed: {
    fileInfo: function () {
      return this.inputFiles[0]?this.inputFiles[0].name:'None';
    },
  }
}
</script>

<style>
.main {
  text-align: left;
  margin: 30px;
}
</style>
