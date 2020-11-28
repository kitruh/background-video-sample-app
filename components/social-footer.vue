<template>
  <div class="social-footer">
    <div class="social-icons-wrapper">
      <div class="social-icon-wrapper">
        <a target="_blank" href="https://www.linkedin.com/in/max-hunter/"><img class="linkedIn" src="~assets/linked-in-vector.png"/></a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'social-footer',
};
</script>

<style scoped>
.social-footer {
  background-color: #e3e3e3;
  position:relative;
  display:flex;
  align-items: center;
  justify-content: center;
  height:10em;
}
.linkedIn{
  width:25px;
}
.social-icon-wrapper{
  height:50px;
  width:50px;
  background-color:#2E2742;
  display:flex;
  justify-content: center;
  align-items: center;
}
@media screen and (max-width: 992px) {
.social-footer {
  height:5em;
}
}
</style>
