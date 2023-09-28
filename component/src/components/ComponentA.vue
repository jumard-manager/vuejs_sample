<template>
  <div>
    {{operatorText}}&nbsp;-&gt;&nbsp;
    <input v-model="left"/> &nbsp;{{operator}}&nbsp;
    <input v-model="right" />&nbsp;=&nbsp; 
    {{calcVal}}
  </div>
</template>
  
<script>
  export default {
    /** コンポーネント名 */
    name: 'ComponentA',
  
    /** 親からの受け取るパラメータ宣言場所  */
    props: {
      _operator: String,
    },
  
    /** 当該コンポーネント内部で動的に使う変数の宣言場所 */
    data() {
      return {
        operatorText: 'PLU',
        operator: '+',
        left: 0,
        right: 0,
      }
    },
  
    /** [props]または[data]変更を検知して自身の値を変更する。 */
    computed: {
      calcVal: function () {
        let calcOperator = this._operator.toLowerCase();
        let result = 0;
        if (calcOperator === 'plus') {
          result = parseInt(this.left) + parseInt(this.right);
        } else if (calcOperator === 'minus') {
          result =  parseInt(this.left) + parseInt(this.right);
        } else if (calcOperator === 'multiplication') {
          result =  parseInt(this.left) + parseInt(this.right);
        } else if (calcOperator === 'division') {
          result =  parseInt(this.left) + parseInt(this.right);
        } else {
          result =  '?';
        }
        this.$emit('_callback',result); 
        return result;
      }
    },
  
    /** 内部で使用するメソッドの宣言場所 */
    methods: {

    },

    /** コンポーネントがマウントされた後に呼び出される。 */
    mounted() {
      this.operatorText = this._operator.substring(0, 3).toUpperCase();
      let calcOperator = this._operator.toLowerCase();
      if (calcOperator === 'plus') {
        this.operator = '+';
      } else if (calcOperator === 'minus') {
        this.operator = '-';
      } else if (calcOperator === 'multiplication') {
        this.operator = '×';
      } else if (calcOperator === 'division') {
        this.operator = '÷';
      } else {
        this.operator = '?';
      }
    },
  }
</script>

<style>

</style>
