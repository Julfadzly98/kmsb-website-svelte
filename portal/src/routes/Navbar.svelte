<script>
	import { page } from "$app/stores"; 
    import { onMount } from "svelte";

      // Show mobile icon and display menu
    let showMobileMenu = false;

    const navs = [
        {
            title: "Home",
            href: "/",
            class:"nav-link scrollto active"
            
        },
        {
            title: "Team",
            href: "#team",
            class:"nav-link scrollto"
        },
        {
            title: "Portfolio",
            href: "#cta",
            class:"nav-link scrollto"
        },
        {
            title: "Contact",
            href: "#contact",
            class:"nav-link scrollto"
        },
    ]

    // Mobile menu click event handler
    const handleMobileIconClick = () => (showMobileMenu = !showMobileMenu);

    // Media match query handler
    // @ts-ignore
    const mediaQueryHandler = e => {
    // Reset mobile state
    if (!e.matches) {
        showMobileMenu = false;
    }
    };

    // Attach media query listener on mount hook
    onMount(() => {
    const mediaListener = window.matchMedia("(max-width: 767px)");

    mediaListener.addListener(mediaQueryHandler);
    });

    $: routeId = $page.route.id;
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
    <link href="https://fonts.googleapis.com/css?family=Open+Sans:300,300i,400,400i,600,600i,700,700i|Raleway:300,300i,400,400i,500,500i,600,600i,700,700i|Poppins:300,300i,400,400i,500,500i,600,600i,700,700i" rel="stylesheet">
  
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
 <header id="header" class="d-flex align-items-center">
    <div class="container d-flex align-items-center justify-content-between">

      <!-- svelte-ignore a11y-invalid-attribute -->
      <h1 class="logo"><a href="#">Kinabalu Makers</a></h1>
      <!-- Uncomment below if you prefer to use an image logo -->
      <!-- <a href="index.html" class="logo"><img src="assets/img/logo.png" alt="" class="img-fluid"></a>-->

          <nav id="navbar" class="navbar">
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <div on:click={handleMobileIconClick} class={`mobile-icon${showMobileMenu ? ' active' : ''}`}>
                <div class="middle-line"></div>
            </div>
            <ul class={`navbar-list${showMobileMenu ? ' mobile' : ''}`}>
                {#each navs as { title, href }}
                <li>
                    <a {href} class:active={routeId == href} {title}>{title}</a>
                </li>
                {/each}
            </ul>

          </nav><!-- .navbar -->

    </div>
</header>

<style>


  .mobile-icon {
    width: 25px;
    height: 14px;
    position: relative;
    cursor: pointer;
  }

  .mobile-icon:after,
  .middle-line {
    content: "";
    position: absolute;
    width: 100%;
    height: 2px;
    background-color: #fff;
    transition: all 0.4s;
    transform-origin: center;
  }

  .mobile-icon:before,
  .middle-line {
    top: 0;
  }

  .mobile-icon:after,
  .middle-line {
    bottom: 0;
  }



  .middle-line {
    margin: auto;
  }

  .mobile-icon:hover:before,
  .mobile-icon:hover:after,
  .mobile-icon.active:before,
  .mobile-icon.active:after,
  .mobile-icon.active .middle-line {
    width: 100%;
  }

  .mobile-icon.active:before,
  .mobile-icon.active:after {
    top: 50%;
    transform: rotate(-45deg);
  }

  .mobile-icon.active .middle-line {
    transform: rotate(45deg);
  }

  .navbar-list {
    display: none;
    width: 50%;
    justify-content: space-between;
    margin: 0;
    padding: 0 40px;
  }

  .navbar-list.mobile {
    background-color: rgba(0, 0, 0, 0.849);
    position: fixed;
    display: block;
    height: calc(100% - 70px);
    bottom: 0;
    right: 0;
  }

  @media only screen and (min-width: 767px) {
    .mobile-icon {
      display: none;
    }

    .navbar-list {
      display: flex;
      padding: 0;
    }

    .navbar-list a {
      display: inline-flex;
    }
  }
</style>




