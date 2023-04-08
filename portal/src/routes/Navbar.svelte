<script>
//navigation menu script
import { onMount } from "svelte";

const navItems = [
  { title: "Home", href: "/" },
  { title: "About", href: "#about" },
  { title: "Team", href: "#team" },
  { title: "Portfolio", href: "#portfolio" },
  { title: "Contact", href: "#contact" },
];
</script>

<head>
    <meta charset="utf-8">
    <meta content="width=device-width, initial-scale=1.0" name="viewport">
  
    <title>KMSB S/B</title>
    <meta content="" name="description">
    <meta content="" name="keywords">
  
    <!-- Favicons -->
    <link href="static/assets/img/KMSB2-1.png" rel="icon">
    <!-- <link href="static/assets/img/apple-touch-icon.png" rel="apple-touch-icon"> -->
  
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;1,100;1,200;1,300;1,400;1,500;1,600;1,700&display=swap" rel="stylesheet">
  
    <!-- Vendor CSS Files -->
    <link href="static/assets/vendor/aos/aos.css" rel="stylesheet">
    <link href="static/assets/vendor/bootstrap/css/bootstrap.min.css" rel="stylesheet">
    <link href="static/assets/vendor/bootstrap-icons/bootstrap-icons.css" rel="stylesheet">
    <link href="static/assets/vendor/boxicons/css/boxicons.min.css" rel="stylesheet">
    <link href="static/assets/vendor/glightbox/css/glightbox.min.css" rel="stylesheet">
    <link href="static/assets/vendor/swiper/swiper-bundle.min.css" rel="stylesheet">
  
    <!-- Template Main CSS File -->
    <link href="static/assets/css/style.css" rel="stylesheet">
</head>

 <!-- ======= Header ======= -->
 <nav class="navbar">
  <div class="navbar-container container">
     <input type="checkbox" name="" id="">
      <div class="hamburger-lines">
        <span class="line line1"></span>
        <span class="line line2"></span>
        <span class="line line3"></span>
      </div>
      <h1 class="logo">KINABALU MAKERS</h1>
      <ul class="menu-items">
        {#each navItems as item}
        <li><a href="{item.href}">{item.title}</a></li>
        {/each}
      </ul>
      
  </div>
</nav>





