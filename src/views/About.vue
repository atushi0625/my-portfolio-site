<template>
    <div class="about">
        <h1>これはアバウトページです</h1>
      <Profile />
      <Introduction/>
    </div>
</template>

<script>
import Profile from '../components/Profile.vue';
import Introduction from '../components/Introduction.vue';
                //  コンポーネントディレクトリはもう一段階上なので.が一つ足りなかった
export default {
    name: "About",
    components:{
      Profile,
      Introduction
    },
    data(){
        return
    }
}
</script>