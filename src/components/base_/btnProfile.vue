<template>
  <div class="btnProfileWrap">
    <div class="nameProfile">
      <h6 class="mb-0 mr-3">{{ name }}</h6>
    </div>
    <div class="photoProfile">
      <img :src="userLogin.image">
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'BtnProfile',
  computed: {
    name () {
      let nama = ''
      if (!localStorage.role_id) {
        nama = this.userLogin.rental_name
        return nama
      }
      nama = this.userLogin.fullname
      return nama
    },
    ...mapState([
      'userLogin'
    ])
  }
}
</script>

<style lang="scss" scoped>
.btnProfileWrap{
  margin-right: 120px;
  height: 100%;
  display: flex;
  align-items: center;
  z-index: 20;
  cursor: pointer;
  .nameProfile {
    align-items: flex-end;
    h6 {
      color: white;
      white-space: nowrap;
    }
  }
  .photoProfile {
    background-color: aquamarine;
    width: 60px;
    height: 60px;
    border-radius: 100%;
    overflow: hidden;
    margin-top: 5px;
    margin-left: 5px;
    top: 0;
    right: 20px;
    cursor: pointer;
    img{
      object-fit: cover;
      width: 100%;
      height: 100%;
    }
  }
}
</style>
