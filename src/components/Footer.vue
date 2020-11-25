<template>
  <div class="footer">
    <div class="contact">
      <p>Made with <i class="fa fa-heart" style="color: red;"></i> by Fábio Mendes, consider contacting me on:</p> 
      <ul>
        <li><a href= "mailto:fabiobends@gmail.com"><i class="fa fa-envelope"></i>Email</a></li>
        <li><a href="https://github.com/fabiobends"><i class="fa fa-github"></i> Github</a></li>
        <li><a href="https://linkedin.com/in/fabiobends"><i class="fa fa-linkedin-square"></i> Linkedin</a></li>
      </ul>
    </div>
    <div class="copyright">Copyright © 2020 yoursite.com</div>
  </div>
</template>

<script>
export default {
  // props: {
  //   herosCount: {
  //     type: String,
  //     required: true,
  //   }
  // }
};
</script>

<style scoped>
.footer {
  position: absolute;
  display: flex;
  justify-content: space-between;
  left: 0;
  bottom: 0;
  align-self: bottom;
  background: white;
  color: #2c2c2c;
  width: 100vw;
  padding: 30px;
  font-size: 14px;
  border-radius: 10px;
  box-shadow: 0px -1px 1px 1px rgba(0, 0, 0, 0.015),
              0px -2px 2px 2px rgba(0, 0, 0, 0.015), 
              0px -4px 4px 4px rgba(0, 0, 0, 0.015),
              0px -8px 8px 8px rgba(0, 0, 0, 0.015);
}

ul {
  display: flex;
  justify-content: space-between;
  list-style-type: none;
}

.copyright {
  align-self: flex-end;
}

a {
  text-decoration: none;
  color: inherit;
  display: flex;
  align-items: center;
}

a:visited {
  color: inherit;
}

p {
  margin-bottom: 5px;
}

i {
  font-size: 18px;
  margin-right: 5px;
}

</style>