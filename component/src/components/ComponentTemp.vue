<template>
  <div>
    <h2>{{title}}</h2>
    <!-- <div>{{uuid}}</div> -->
  </div>
</template>

<script>
import { v4 as uuid } from 'uuid';

export default {
  /**コンポーネント名 */
  name: 'ComponentTemp',

  /** 外部追加コンポーネント宣言場所  */
  components: {

  },

  /** 親からの受け取るパラメータ宣言場所  */
  props: {
    param1: String,
  },

  /** 当該コンポーネント内部で動的に使う変数の宣言場所 */
  data() {
    return {
      title: 'Operator (plus / minus / multiplication / division)',
      uuid: uuid(),
    }
  },

  /** [props]または[data]変更を検知して自身の値を変更する。 */
  computed: {

  },

  /** [props]または[data]特定の値を変更を検知して何らかの処理をする。 */
  watch:{

  },

  /** 内部で使用するメソッドの宣言場所 */
  methods: {

  },

  /** ＝＝＝＝＝＝＝＝＝＝＝＝＝＝ **/
  /** 以下、ライフサイクル制御機能 **/
  /** ＝＝＝＝＝＝＝＝＝＝＝＝＝＝ **/

  /** インスタンスが初期化されるときに呼び出される。 */
  beforeCreate() {
    console.log('Called beforeCreate.');
  },

  /** インスタンスがすべての状態関連オプションの処理を終了した後に呼び出される。 */
  created() {
    console.log('Called created.');
  },

  /** コンポーネントがマウントされる直前に呼び出される。 */
  beforeMount() {
    console.log('Called beforeMount.');
  },

  /** コンポーネントがマウントされた後に呼び出される。 */
  mounted() {
    console.log('Called mounted.');
  },

  /** DOM ツリーを更新しようとする直前に呼び出される。 */
  beforeUpdate() {
    console.log('Called beforeUpdate.');
  },

  /** DOM ツリーを更新した後に呼び出される。 */
  updated() {
    console.log('Called updated.');
  },

  /** コンポーネントインスタンスがアンマウントされる直前に呼び出される。 */
  beforeUnmount() {
    console.log('Called beforeUnmount.');
  },

  /** コンポーネントがアンマウントされた後に呼び出される。 */
  unmounted() {
    console.log('Called unmounted.');
  },

  /** 子孫コンポーネントから伝搬するエラーをキャプチャーしたときに呼び出される。 */
  errorCaptured(err, instance, info){
    console.log('Called errorCaptured.');
    console.log(err);
    console.log(instance);
    console.log(info);
  },

}
</script>

<style>

</style>
