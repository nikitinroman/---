<template>
  <div class="bigDiv">
    <a name="footer"></a>
    <a href="https://vk.com/nikitin__roman" target="_blank"><div class="innerDiv">Вконтакте</div></a>
    <a href="https://www.instagram.com/nikitoss420/" target="_blank"><div class="innerDiv">Инстаграм</div></a>
    <a href="https://t.me/nikitoss420" target="_blank"><div class="innerDiv">Телеграм</div></a>
    <a href="mailto:nikitin.roman2000@yandex.ru?subject=Приглашаем Вас на стажировку"><div class="innerDiv">Почта</div></a>
    <a href="https://github.com/nikitinroman" target="_blank"><div class="innerDiv">Гитхаб</div></a>
  </div>
</template>

<script>
export default {
name: "Footer"
}
</script>

<style scoped>
.bigDiv{
  display: flex;
  justify-content: flex-end;
  height: 5vh;
  width: 100%;
  margin-top: -45px;
}
.innerDiv{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 80px;
  height: 40px;
  border-radius: 7px;
  margin-right: 25px;
  transition: 1s;
}
.innerDiv:hover{
  background-color: darkgrey;
}
a{
  color: #3a201e;
  text-decoration: none;
}
</style>
