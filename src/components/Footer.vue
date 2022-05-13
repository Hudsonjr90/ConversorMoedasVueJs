<template>
  <footer>
    <div class="footer-container">
      <img src="" alt="Logo" class="zoom" />
      <div class="social-media">
        <a href="">
          <i class="fab fa-facebook-f"></i
        ></a>
        <a href="">
          <i class="fab fa-twitter"></i
        ></a>
        <a href="">
          <i class="fab fa-instagram"></i
        ></a>
        <a href="">
          <i class="fab fa-linkedin-in"></i
        ></a>
      </div>
      <p class="rights-text">
        Copyright ©️ 2022 HK™<br />Todos os direitos reservados a Hudson Kennedy
      </p>
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style>
footer {
    background: #f1f1f1;  
    padding: 20px 0;
    width: 100%;
    text-align: center;
    margin-top: 40px;
}

.footer-container {
	max-width: 1300px;
	margin: auto;
	padding: 0 20px;
}

.footer-container img {
    width: 50px;
}

.footer-container .social-media {
	margin: 20px 0;
}

.footer-container .social-media a {
	color: #001a21;
	margin-right: 25px;
	font-size: 22px;
	text-decoration: none;
	transition: .3s linear;
}

.footer-container .social-media a:hover {
	color: #f46767;
}

.footer-container p {
    font-weight: 700;
}
</style>