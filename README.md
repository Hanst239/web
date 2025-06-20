<!DOCTYPE html>
<html lang="es">
    <?php include("php/conexion.php"); ?>

<head>
    <meta charset="utf-8">
    <title>Joseline & Dustin - Sitio Web de Boda</title>
    <meta content="width=device-width, initial-scale=1.0" name="viewport">
    <meta content="Boda, Joseline, Dustin" name="keywords">
    <meta content="Sitio web para la boda de Joseline y Dustin" name="description">

    <!-- Favicon -->
    <link href="img/favicon.ico" rel="icon">

    <!-- Google Web Fonts -->
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Montserrat:wght@400;600&display=swap" rel="stylesheet"> 

    <!-- Font Awesome -->
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.10.0/css/all.min.css" rel="stylesheet">

    <!-- Libraries Stylesheet -->
    <link href="lib/owlcarousel/assets/owl.carousel.min.css" rel="stylesheet">
    <link href="lib/lightbox/css/lightbox.min.css" rel="stylesheet">

    <!-- Customized Bootstrap Stylesheet -->
    <link href="css/style.css" rel="stylesheet">
    

    <style>
        /* Colores personalizados */
        :root {
            --gold: #D4AF37;
            --gold-light: #F5D98F;
            --gold-dark: #B8860B;
            --green: #2E8B57;
            --green-light: #5F9E6E;
            --green-dark: #1E5631;
            --white: #FFFFFF;
            --black: #000000;
        }

        /* Sobreescribir colores principales */
        .bg-primary {
            background-color: var(--gold) !important;
        }
        
        .text-primary {
            color: var(--gold) !important;
        }
        
        .btn-primary {
            background-color: var(--gold);
            border-color: var(--gold);
        }
        
        .btn-primary:hover {
            background-color: var(--gold-dark);
            border-color: var(--gold-dark);
        }
        
        .btn-outline-primary {
            color: var(--gold);
            border-color: var(--gold);
        }
        
        .btn-outline-primary:hover {
            background-color: var(--gold);
            color: var(--white);
        }
        
        /* Navbar */
        .navbar-dark {
            background-color: var(--green) !important;
        }
        
        /* Backgrounds */
        .bg-secondary {
            background-color: var(--green) !important;
            color: var(--white) !important;
        }
        
        .bg-dark {
            background-color: var(--green-dark) !important;
        }
        
        .bg-gallery {
            background: linear-gradient(rgba(46, 139, 87, 0.9), rgba(46, 139, 87, 0.9)), url('img/gallery-bg.jpg');
            background-size: cover;
            background-position: center;
        }
        
        /* Textos */
        .text-muted {
            color: var(--white) !important;
        }
        
        /* Countdown */
        #countdown {
            font-size: 1.5rem;
            font-weight: bold;
            margin: 20px 0;
            color: var(--gold);
        }

        .countdown-container {
            display: flex;
            justify-content: center;
            gap: 10px;
            flex-wrap: wrap;
        }

        .countdown-box {
            text-align: center;
            min-width: 70px;
        }

        .countdown-number {
            font-size: 1.8rem;
            font-weight: bold;
            display: block;
            color: var(--gold);
        }

        .countdown-label {
            font-size: 0.8rem;
            text-transform: uppercase;
            color: var(--white);
        }

        @media (max-width: 768px) {
            .countdown-box {
                min-width: 60px;
            }
            
            .countdown-number {
                font-size: 1.5rem;
            }
            
            .countdown-label {
                font-size: 0.7rem;
            }
        }

        /* Estilos para la confirmación */
        #invitacionContainer {
            background: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
        }

        #qrCode {
            width: 180px;
            height: 180px;
            margin: 20px auto;
            background: white;
            padding: 15px;
            border-radius: 10px;
            border: 2px solid var(--gold);
        }

        #confirmarForm {
            background: rgba(30, 86, 49, 0.7);
            padding: 25px;
            border-radius: 8px;
        }

        .form-control {
            color: white !important;
        }

        .form-control::placeholder {
            color: #ccc !important;
        }
    </style>
    
</head>

<body data-spy="scroll" data-target=".navbar" data-offset="51">
    <!-- Navbar Start -->
    <nav class="navbar fixed-top shadow-sm navbar-expand-lg navbar-dark py-3 py-lg-0 px-lg-5">
        <a href="index.html" class="navbar-brand d-block d-lg-none">
            <h1 class="font-secondary text-white mb-n2">Joseline <span class="text-primary">&</span> Dustin</h1>
        </a>
        <button type="button" class="navbar-toggler" data-toggle="collapse" data-target="#navbarCollapse">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse justify-content-between" id="navbarCollapse">
            <div class="navbar-nav ml-auto py-0">
                <a href="#home" class="nav-item nav-link active">Inicio</a>
                <a href="#story" class="nav-item nav-link">Historia</a>
                <a href="#gallery" class="nav-item nav-link">Galería</a>
            </div>
            <a href="index.php" class="navbar-brand mx-5 d-none d-lg-block">
                <h1 class="font-secondary text-white mb-n2">Joseline <span class="text-primary">&</span> Dustin</h1>
            </a>
            <div class="navbar-nav mr-auto py-0">
                <a href="#event" class="nav-item nav-link">Evento</a>
                <a href="#rsvp" class="nav-item nav-link">Mi invitación</a>
            </div>
        </div>
    </nav>
    <!-- Navbar End -->

    <!-- Carousel Start - Modificado a solo 2 fotos -->
    <div class="container-fluid p-0 mb-5 pb-5" id="home">
        <div id="header-carousel" class="carousel slide carousel-fade" data-ride="carousel">
            <div class="carousel-inner">
                <!-- Foto 1 (activa por defecto) -->
                <div class="carousel-item position-relative active" style="height: 100vh; min-height: 400px;">
                    <img class="position-absolute w-100 h-100" src="img/principal.jpg" style="object-fit: cover;">
                    <div class="carousel-caption d-flex flex-column align-items-center justify-content-center">
                        <div class="p-3" style="max-width: 900px;">
                            <h1 class="display-1 font-secondary text-white mt-n3 mb-md-4">Joseline & Dustin</h1>
                            <div class="d-inline-block border-top border-bottom border-light py-3 px-4">
                                <h3 class="text-uppercase font-weight-normal text-white m-0" style="letter-spacing: 2px;">Nos casamos</h3>
                            </div>
                            <div id="countdown" class="text-center mt-4"></div>
                        </div>
                    </div>
                </div>
                
                <!-- Foto 2 -->
                <div class="carousel-item position-relative" style="height: 100vh; min-height: 400px;">
                    <img class="position-absolute w-100 h-100" src="img/principal2.jpg" style="object-fit: cover;">
                    <div class="carousel-caption d-flex flex-column align-items-center justify-content-center">
                        <div class="p-3" style="max-width: 900px;">
                            <h1 class="display-1 font-secondary text-white mt-n3 mb-md-4">Joseline & Dustin</h1>
                            <div class="d-inline-block border-top border-bottom border-light py-3 px-4">
                                <h3 class="text-uppercase font-weight-normal text-white m-0" style="letter-spacing: 2px;">Nos casamos</h3>
                            </div>
                            <div id="countdown" class="text-center mt-4"></div>
                        </div>
                    </div>
                </div>
            </div>
            <a class="carousel-control-prev justify-content-start" href="#header-carousel" data-slide="prev">
                <div class="btn btn-primary px-0" style="width: 68px; height: 68px;">
                    <span class="carousel-control-prev-icon mt-3"></span>
                </div>
            </a>
            <a class="carousel-control-next justify-content-end" href="#header-carousel" data-slide="next">
                <div class="btn btn-primary px-0" style="width: 68px; height: 68px;">
                    <span class="carousel-control-next-icon mt-3"></span>
                </div>
            </a>
        </div>
    </div>
    <!-- Carousel End -->

    <!-- Video Modal Start -->
    <div class="modal fade" id="videoModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog" role="document">
            <div class="modal-content">
                <div class="modal-body">
                    <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                        <span aria-hidden="true">×</span>
                    </button>        
                    <!-- 16:9 aspect ratio -->
                    <div class="embed-responsive embed-responsive-16by9">
                        <iframe class="embed-responsive-item" src="" id="video"  allowscriptaccess="always" allow="autoplay"></iframe>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <!-- Video Modal End -->

    <!-- Story Start - Manteniendo las 5 fotos -->
   <div class="container-fluid py-5" id="story">
    <div class="container pt-5 pb-3">
        <div class="section-title position-relative text-center">
            <h6 class="text-uppercase text-primary mb-3" style="letter-spacing: 3px;">Historia</h6>
            <h1 class="font-secondary display-4">Nuestra Historia de Amor</h1>
            <i class="far fa-heart text-dark"></i>
        </div>
        <div class="container timeline position-relative p-0">
            <!-- Primer Encuentro -->
            <div class="row mb-5">
                <div class="col-md-6 text-center text-md-right mb-4 mb-md-0">
                    <div class="story-img-container">
                        <img class="img-fluid" src="img/principal5.jpg" alt="Primer Encuentro">
                    </div>
                </div>
                <div class="col-md-6 text-center text-md-left">
                    <div class="h-100 d-flex flex-column justify-content-center bg-secondary p-4 ml-md-3">
                        <h4 class="mb-2">Primer Encuentro</h4>
                        <p class="text-uppercase mb-2">01 Ene 2050</p>
                        <p class="m-0">Un momento mágico que comenzó todo.</p>
                    </div>
                </div>
            </div>
            
            <!-- Primera Cita -->
            <div class="row mb-5 flex-md-row-reverse">
                <div class="col-md-6 text-center text-md-left mb-4 mb-md-0">
                    <div class="story-img-container">
                        <img class="img-fluid" src="img/principal3.jpg" alt="Primera Cita">
                    </div>
                </div>
                <div class="col-md-6 text-center text-md-right">
                    <div class="h-100 d-flex flex-column justify-content-center bg-secondary p-4 mr-md-3">
                        <h4 class="mb-2">Primera Cita</h4>
                        <p class="text-uppercase mb-2">01 Ene 2050</p>
                        <p class="m-0">Una noche inolvidable bajo las estrellas.</p>
                    </div>
                </div>
            </div>
            
            <!-- Propuesta -->
            <div class="row mb-5">
                <div class="col-md-6 text-center text-md-right mb-4 mb-md-0">
                    <div class="story-img-container">
                        <img class="img-fluid" src="img/principal2.jpg" alt="Propuesta">
                    </div>
                </div>
                <div class="col-md-6 text-center text-md-left">
                    <div class="h-100 d-flex flex-column justify-content-center bg-secondary p-4 ml-md-3">
                        <h4 class="mb-2">Propuesta</h4>
                        <p class="text-uppercase mb-2">01 Ene 2050</p>
                        <p class="m-0">Un instante que selló nuestro futuro.</p>
                    </div>
                </div>
            </div>
            
            <!-- Compromiso -->
            <div class="row mb-5 flex-md-row-reverse">
                <div class="col-md-6 text-center text-md-left mb-4 mb-md-0">
                    <div class="story-img-container">
                        <img class="img-fluid" src="img/principal4.jpg" alt="Compromiso">
                    </div>
                </div>
                <div class="col-md-6 text-center text-md-right">
                    <div class="h-100 d-flex flex-column justify-content-center bg-secondary p-4 mr-md-3">
                        <h4 class="mb-2">Compromiso</h4>
                        <p class="text-uppercase mb-2">01 Ene 2050</p>
                        <p class="m-0">Un paso más hacia nuestra unión.</p>
                    </div>
                </div>
            </div>
            
            <!-- Preparativos -->
            <div class="row">
                <div class="col-md-6 text-center text-md-right mb-4 mb-md-0">
                    <div class="story-img-container">
                        <img class="img-fluid" src="img/principal2.jpg" alt="Preparativos">
                    </div>
                </div>
                <div class="col-md-6 text-center text-md-left">
                    <div class="h-100 d-flex flex-column justify-content-center bg-secondary p-4 ml-md-3">
                        <h4 class="mb-2">Preparativos</h4>
                        <p class="text-uppercase mb-2">01 Ene 2050</p>
                        <p class="m-0">Los preparativos para nuestro gran día.</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>

<style>
    /* Estilos para la sección de Historia */
    .story-img-container {
        height: 350px; /* Altura fija para todas las imágenes */
        overflow: hidden;
        border-radius: 8px;
        box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        position: relative;
    }
    
    .story-img-container img {
        width: 100%;
        height: 100%;
        object-fit: cover; /* Asegura que la imagen cubra todo el espacio */
        transition: transform 0.5s ease;
    }
    
    .story-img-container:hover img {
        transform: scale(1.05);
    }
    
    .timeline .row {
        margin-bottom: 30px;
    }
    
    .bg-secondary {
        border-radius: 8px;
        height: 350px; /* Misma altura que las imágenes */
    }
    
    @media (max-width: 767.98px) {
        .story-img-container,
        .bg-secondary {
            height: 250px; /* Altura más pequeña para móviles */
        }
        
        .flex-md-row-reverse {
            flex-direction: column-reverse !important;
        }
    }
</style>
    <!-- Story End -->

    <!-- Gallery Start - Manteniendo las 5 fotos -->
    <div class="container-fluid bg-gallery" id="gallery" style="padding: 120px 0; margin: 90px 0;">
    <div class="section-title position-relative text-center" style="margin-bottom: 120px;">
        <h6 class="text-uppercase text-primary mb-3" style="letter-spacing: 3px;">Galería</h6>
        <h1 class="font-secondary display-4 text-white">Nuestra Galería de Fotos</h1>
        <i class="far fa-heart text-white"></i>
    </div>
    <div class="owl-carousel gallery-carousel">
        <div class="gallery-item">
            <div class="gallery-img-container">
                <img class="img-fluid" src="img/principal.jpg" alt="">
                <a href="img/principal.jpg" data-lightbox="gallery">
                    <i class="fa fa-2x fa-plus text-white"></i>
                </a>
            </div>
        </div>
        <div class="gallery-item">
            <div class="gallery-img-container">
                <img class="img-fluid" src="img/principal2.jpg" alt="">
                <a href="img/principal2.jpg" data-lightbox="gallery">
                    <i class="fa fa-2x fa-plus text-white"></i>
                </a>
            </div>
        </div>
        <div class="gallery-item">
            <div class="gallery-img-container">
                <img class="img-fluid" src="img/principal3.jpg" alt="">
                <a href="img/principal3.jpg" data-lightbox="gallery">
                    <i class="fa fa-2x fa-plus text-white"></i>
                </a>
            </div>
        </div>
        <div class="gallery-item">
            <div class="gallery-img-container">
                <img class="img-fluid" src="img/principal4.jpg" alt="">
                <a href="img/principal4.jpg" data-lightbox="gallery">
                    <i class="fa fa-2x fa-plus text-white"></i>
                </a>
            </div>
        </div>
        <div class="gallery-item">
            <div class="gallery-img-container">
                <img class="img-fluid" src="img/principal5.jpg" alt="">
                <a href="img/principal5.jpg" data-lightbox="gallery">
                    <i class="fa fa-2x fa-plus text-white"></i>
                </a>
            </div>
        </div>
    </div>
</div>

<style>
    /* Estilos para la galería */
    .gallery-item {
        padding: 0 15px;
    }
    
    .gallery-img-container {
        height: 400px; /* Altura fija para todas las imágenes */
        overflow: hidden;
        position: relative;
        border-radius: 8px;
        box-shadow: 0 5px 15px rgba(0,0,0,0.2);
    }
    
    .gallery-img-container img {
        width: 100%;
        height: 100%;
        object-fit: cover; /* Asegura que la imagen cubra todo el espacio manteniendo proporciones */
        transition: transform 0.3s ease;
    }
    
    .gallery-img-container:hover img {
        transform: scale(1.05);
    }
    
    .gallery-img-container a {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        opacity: 0;
        transition: opacity 0.3s ease;
    }
    
    .gallery-img-container:hover a {
        opacity: 1;
    }
    
    @media (max-width: 768px) {
        .gallery-img-container {
            height: 300px; /* Altura más pequeña para móviles */
        }
    }
</style>
    <!-- Gallery End -->

    <!-- Event Start - Modificado con principal4 y principal3 -->
    <div class="container-fluid py-5" id="event">
    <div class="container py-5">
        <div class="section-title position-relative text-center">
            <h6 class="text-uppercase text-primary mb-3" style="letter-spacing: 3px;">Evento</h6>
            <h1 class="font-secondary display-4">Nuestra Boda</h1>
            <i class="far fa-heart text-dark"></i>
        </div>
        <div class="row justify-content-center">
            <div class="col-md-6 text-center">
                <h5 class="font-weight-normal text-white mb-3 pb-3">Únete a nosotros en este día especial.</h5>
            </div>
        </div>
        <div class="row">
            <!-- Ceremonia Religiosa -->
            <div class="col-md-6 border-right border-primary">
                <div class="text-center text-md-right mr-md-3 mb-4 mb-md-0">
                    <div class="event-img-container">
                        <img class="img-fluid" src="img/principal4.jpg" alt="Ceremonia Religiosa">
                    </div>
                    <h4 class="mb-3 mt-4">La Ceremonia Religiosa</h4>
                    <p class="mb-2">Santuario de la Inmaculada Concepción</p>
                    <p class="mb-0">Sábado 13 Dic 2025, 5:00 PM CST</p>
                </div>
            </div>
            
            <!-- Recepción -->
            <div class="col-md-6">
                <div class="text-center text-md-left ml-md-3">
                    <div class="event-img-container">
                        <img class="img-fluid" src="img/principal3.jpg" alt="Recepción">
                    </div>
                    <h4 class="mb-3 mt-4">Recepción</h4>
                    <p class="mb-2">Salón Dorado</p>
                    <p class="mb-0">6:30 PM CST</p>
                </div>
            </div>
        </div>
    </div>
</div>

<style>
    /* Estilos para la sección de Evento */
    .event-img-container {
        height: 400px; /* Altura fija para ambas imágenes */
        overflow: hidden;
        border-radius: 8px;
        box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        position: relative;
    }
    
    .event-img-container img {
        width: 100%;
        height: 100%;
        object-fit: cover; /* Asegura que la imagen cubra todo el espacio */
        transition: transform 0.5s ease;
    }
    
    .event-img-container:hover img {
        transform: scale(1.03);
    }
    
    .border-primary {
        border-color: var(--gold) !important;
    }
    
    @media (max-width: 767.98px) {
        .event-img-container {
            height: 300px; /* Altura más pequeña para móviles */
        }
        
        .border-right {
            border-right: none !important;
            border-bottom: 2px solid var(--gold);
            padding-bottom: 30px;
            margin-bottom: 30px;
        }
    }
    
    @media (min-width: 768px) {
        .text-md-right {
            padding-right: 30px;
        }
        .text-md-left {
            padding-left: 30px;
        }
    }
</style>
    <!-- Event End -->

    <!-- Confirmación Start -->
    <div class="container-fluid py-5" id="confirmacion">
    <div id="rsvp" class="text-center" style="
        background: linear-gradient(rgba(30, 86, 49, 0.95), rgba(30, 86, 49, 0.95));
        border-radius: 15px;
        box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        padding: 3rem;
        margin: 2rem auto;
        max-width: 800px;
        border: 3px solid var(--gold);
        position: relative;
        overflow: hidden;
    ">
        <!-- Detalle decorativo dorado -->
        <div style="
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--gold-dark), var(--gold), var(--gold-dark));
        "></div>
        
        <!-- Formulario de confirmación -->
        <div class="invitacion-publica card shadow" style="background-color: white; border: 3px solid goldenrod; max-width: 600px; margin: 0 auto; font-family: 'Playfair Display', serif; padding: 2rem; color: goldenrod; position: relative;">
  <!-- Decoración de esquinas -->
  <div style="position:absolute; top:0; left:0; width:40px; height:40px; border-top:4px solid goldenrod; border-left:4px solid goldenrod;"></div>
  <div style="position:absolute; top:0; right:0; width:40px; height:40px; border-top:4px solid goldenrod; border-right:4px solid goldenrod;"></div>
  <div style="position:absolute; bottom:0; left:0; width:40px; height:40px; border-bottom:4px solid goldenrod; border-left:4px solid goldenrod;"></div>
  <div style="position:absolute; bottom:0; right:0; width:40px; height:40px; border-bottom:4px solid goldenrod; border-right:4px solid goldenrod;"></div>

  <!-- Encabezado -->
  <h2 class="text-center" style="font-style: italic; font-size: 1.2rem; margin-bottom: 1rem;">"Todo el mundo debería tener amor verdadero, y debería durar como mínimo toda la vida"</h2>

  <!-- Nombres -->
  <h1 class="text-center" style="font-size: 2.5rem; font-weight: bold; margin-bottom: 0.5rem;">Joseline & Dustin</h1>

  <!-- Texto de invitación -->
  <p class="text-center" style="font-weight: 600; font-size: 1rem;">TENEMOS EL HONOR DE INVITAR A USTED Y SU APRECIABLE FAMILIA A LA CEREMONIA RELIGIOSA QUE SE LLEVARÁ A CABO EL DÍA</p>

  <!-- Fecha y hora -->
  <div class="text-center my-3">
    <div style="font-size: 1.2rem;"><strong>SÁBADO</strong></div>
    <div style="font-size: 3rem; font-weight: bold;">13</div>
    <div style="font-size: 1.2rem;">DICIEMBRE - A LAS 5:00 P.M.</div>
  </div>

  <!-- Lugar -->
  <h3 class="text-center" style="font-weight: bold; font-size: 1.3rem;">SANTA MISA</h3>
  <p class="text-center" style="margin-bottom: 1rem;">Santuario de la Inmaculada Concepción</p>

  <!-- Padres -->
  <p class="text-center" style="font-weight: 600;">EN COMPAÑÍA DE NUESTROS QUERIDOS PADRES:</p>
  <div class="d-flex justify-content-around text-center mb-3" style="font-size: 0.9rem;">
    <div>
      <p>Angélica Quiroz Hernández</p>
      <p>Abduraúl Vega Orozco</p>
    </div>
    <div>
      <p>Martha Hernández Martínez</p>
      <p>Juan Luis Tello Pérez</p>
    </div>
  </div>

  <!-- Padrinos -->
  <p class="text-center" style="font-weight: 600;">PADRINOS DE VELACIÓN</p>
  <p class="text-center mb-3">Patricia Quiroz Hernández<br>Raúl Bucio García</p>

  <!-- Pregunta final -->
  <p class="text-center" style="font-weight: bold; font-size: 1.1rem;">¿Nos harían el honor de decir que “sí”...<br>a la invitación de nuestra boda?</p>
</div>

    </div>
</div>

<style>
    /* Efectos hover para el botón */
    #rsvp .btn:hover {
        transform: translateY(-3px);
        box-shadow: 0 8px 25px rgba(212, 175, 55, 0.6);
    }
    
    #rsvp .btn:hover span:last-child {
        opacity: 1;
    }
    
    #rsvp .btn:active {
        transform: translateY(1px);
    }
    
    /* Animación sutil para la tarjeta */
    @keyframes fadeInUp {
        from {
            opacity: 0;
            transform: translateY(20px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }
    
    #rsvp {
        animation: fadeInUp 0.6s ease-out forwards;
    }
</style>
    
    <!-- Tarjeta de invitación (se mostrará después de la búsqueda) -->
    
</div>
</div>
    <!-- Confirmación End -->

    <!-- Footer Start -->
    <div class="container-fluid bg-dark text-white py-5" id="contact" style="margin-top: 90px;">
    <div class="container text-center py-5">
        <div class="section-title position-relative text-center">
            <h1 class="font-secondary display-3 text-white">Gracias</h1>
            <i class="far fa-heart text-white"></i>
        </div>
        <div class="d-flex justify-content-center mb-4">
            <a class="btn btn-lg btn-outline-light btn-lg-square mr-2" href="#"><i class="fab fa-twitter"></i></a>
            <a class="btn btn-lg btn-outline-light btn-lg-square mr-2" href="#"><i class="fab fa-facebook-f"></i></a>
            <a class="btn btn-lg btn-outline-light btn-lg-square mr-2" href="#"><i class="fab fa-linkedin-in"></i></a>
            <a class="btn btn-lg btn-outline-light btn-lg-square" href="#"><i class="fab fa-instagram"></i></a>
        </div>
        <div class="d-flex justify-content-center py-2">
            <p class="text-white" href="#">info@joselineydustin.com</p>
            <span class="px-3">|</span>
            <p class="text-white" href="#">+012 345 6789</p>
        </div>
        
        <!-- Sección de créditos -->
        <div class="creditos mt-4">
            <p class="m-0">© 2025 Joseline & Dustin. Todos los derechos reservados.</p>
            <div class="mt-3" style="border-top: 1px solid rgba(255,255,255,0.1); width: 60%; margin: 10px auto;"></div>
            <p class="mb-1">Sitio web creado con ❤️ por <strong>[Tu Nombre]</strong></p>
            <p class="small mb-0">
                <a href="mailto:tuemail@ejemplo.com" class="text-white-50">Contacta al desarrollador</a> | 
                <a href="https://tusitio.com" class="text-white-50">Visita mi portafolio</a>
            </p>
        </div>
    </div>
</div>
    <!-- Footer End -->

    <!-- Scroll to Bottom -->
    <i class="fa fa-2x fa-angle-down text-white scroll-to-bottom"></i>

    <!-- Back to Top -->
    <a href="#" class="btn btn-lg btn-outline-primary btn-lg-square back-to-top"><i class="fa fa-angle-double-up"></i></a>

    <!-- JavaScript Libraries -->
    <script src="https://code.jquery.com/jquery-3.4.1.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.bundle.min.js"></script>
    <script src="lib/easing/easing.min.js"></script>
    <script src="lib/waypoints/waypoints.min.js"></script>
    <script src="lib/owlcarousel/owl.carousel.min.js"></script>
    <script src="lib/isotope/isotope.pkgd.min.js"></script>
    <script src="lib/lightbox/js/lightbox.min.js"></script>
    <script src="https://cdn.rawgit.com/davidshimjs/qrcodejs/gh-pages/qrcode.min.js"></script>
    <script src="https://cdn.jsdelivr.net/gh/davidshimjs/qrcodejs/qrcode.min.js"></script>

    <!-- Template Javascript -->
    <script src="js/main.js"></script>

    <!-- Custom JavaScript -->
    <script>
    // Countdown Timer
    function updateCountdown() {
        const weddingDate = new Date("December 13, 2025 17:00:00").getTime();
        const now = new Date().getTime();
        const distance = weddingDate - now;

        // Cálculo de meses (aproximado)
        const months = Math.floor(distance / (1000 * 60 * 60 * 24 * 30.44));
        const days = Math.floor((distance % (1000 * 60 * 60 * 24 * 30.44)) / (1000 * 60 * 60 * 24));
        const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
        const seconds = Math.floor((distance % (1000 * 60)) / 1000);

        document.getElementById("countdown").innerHTML = `
            <div class="countdown-container">
                <div class="countdown-box">
                    <span class="countdown-number">${months}</span>
                    <span class="countdown-label">Meses</span>
                </div>
                <div class="countdown-box">
                    <span class="countdown-number">${days}</span>
                    <span class="countdown-label">Días</span>
                </div>
                <div class="countdown-box">
                    <span class="countdown-number">${hours}</span>
                    <span class="countdown-label">Horas</span>
                </div>
                <div class="countdown-box">
                    <span class="countdown-number">${minutes}</span>
                    <span class="countdown-label">Minutos</span>
                </div>
                <div class="countdown-box">
                    <span class="countdown-number">${seconds}</span>
                    <span class="countdown-label">Segundos</span>
                </div>
            </div>
        `;

        if (distance < 0) {
            document.getElementById("countdown").innerHTML = `
                <h3 class="text-primary">¡Es el día de nuestra boda!</h3>
                <p class="text-white">Gracias por acompañarnos en este momento especial.</p>
            `;
        }
    }
    
    // Inicializar el contador
    updateCountdown();
    setInterval(updateCountdown, 1000);

    // Base de datos de invitados (deberías reemplazar esto con un backend real)
    $(document).ready(function() {
    let invitadoActual = null;
    let qrCode = null;
    
    // Manejar el formulario de búsqueda
    $('#formBusqueda').submit(function(e) {
        e.preventDefault();
        const nombreBusqueda = $('#nombreBusqueda').val().trim().toLowerCase();
        
        if (!nombreBusqueda) {
            alert('Por favor ingresa tu nombre');
            return;
        }
        
        // Mostrar carga
        $('#formBusqueda button').html('<i class="fas fa-spinner fa-spin mr-2"></i> Buscando...').prop('disabled', true);
        
        // Buscar en la base de datos
        $.ajax({
            url: 'php/buscar_invitado.php',
            method: 'POST',
            data: { nombre: nombreBusqueda },
            dataType: 'json',
            success: function(response) {
                $('#formBusqueda button').html('<i class="fas fa-search mr-2"></i> Buscar Invitación').prop('disabled', false);
                
                if (response.error) {
                    // Mostrar mensaje de error
                    $('#invitacionContainer').hide();
                    $('#invitacionNoValida').show();
                    return;
                }
                
                // Mostrar la tarjeta de invitación
                invitadoActual = response;
                mostrarInvitacion();
                $('#busquedaInvitacion').hide();
                $('#tarjetaInvitacion').show();
            },
            error: function() {
                $('#formBusqueda button').html('<i class="fas fa-search mr-2"></i> Buscar Invitación').prop('disabled', false);
                alert('Error al conectar con el servidor');
            }
        });
    });
    
    function mostrarInvitacion() {
        $('#nombreInvitado').text(invitadoActual.nombre);
        $('#numeroInvitados').text(`Pase para ${invitadoActual.invitados} personas`);
        $('#estadoConfirmacion').text(`Estado: ${invitadoActual.confirmacion === '1' ? 'Confirmado' : 'Pendiente'}`);
        
        // Generar QR
        if (qrCode) {
            qrCode.clear();
        }
        
        const qrData = JSON.stringify({
            id: invitadoActual.id,
            nombre: invitadoActual.nombre,
            invitados: invitadoActual.invitados,
            confirmacion: invitadoActual.confirmacion,
            evento: "Boda Joseline y Dustin",
            fecha: "13/12/2025"
        });
        
        qrCode = new QRCode(document.getElementById("qrCode"), {
            text: qrData,
            width: 180,
            height: 180,
            colorDark: "#1E5631",
            colorLight: "#ffffff",
            correctLevel: QRCode.CorrectLevel.H
        });
        
        // Configurar botón de confirmación
        if (invitadoActual.confirmacion === '1') {
            $('#confirmarAsistencia').html('<i class="fas fa-check-circle mr-2"></i> Asistencia Confirmada').prop('disabled', true);
        } else {
            $('#confirmarAsistencia').html('<i class="fas fa-check-circle mr-2"></i> Confirmar Asistencia').prop('disabled', false);
        }
    }
    
    // Confirmar asistencia
    $('#confirmarAsistencia').click(function() {
        if (!invitadoActual) return;
        
        if (confirm('¿Confirmas que asistirás al evento?')) {
            $(this).html('<i class="fas fa-spinner fa-spin mr-2"></i> Confirmando...').prop('disabled', true);
            
            $.ajax({
                url: 'php/confirmar_asistencia.php',
                method: 'POST',
                data: { id: invitadoActual.id },
                dataType: 'json',
                success: function(response) {
                    if (response.success) {
                        invitadoActual.confirmacion = '1';
                        mostrarInvitacion();
                        alert('¡Asistencia confirmada con éxito!');
                    } else {
                        alert(response.error || 'Error al confirmar asistencia');
                        $('#confirmarAsistencia').html('<i class="fas fa-check-circle mr-2"></i> Confirmar Asistencia').prop('disabled', false);
                    }
                },
                error: function() {
                    alert('Error al conectar con el servidor');
                    $('#confirmarAsistencia').html('<i class="fas fa-check-circle mr-2"></i> Confirmar Asistencia').prop('disabled', false);
                }
            });
        }
    });
    
    // Descargar QR
    $('#descargarQR').click(function() {
        if (!qrCode) return;
        
        const canvas = document.querySelector("#qrCode canvas");
        const url = canvas.toDataURL("image/png");
        const link = document.createElement("a");
        link.download = `Invitacion_${invitadoActual.nombre.replace(/\s+/g, '_')}.png`;
        link.href = url;
        link.click();
    });
    
    // Compartir invitación
    $('#compartirInvitacion').click(function() {
        if (!invitadoActual) return;
        
        if (navigator.share) {
            navigator.share({
                title: 'Invitación Boda',
                text: `${invitadoActual.nombre}, estás invitado a nuestra boda`,
                url: window.location.href + '?invitado=' + encodeURIComponent(invitadoActual.nombre.toLowerCase())
            }).catch(err => {
                console.log('Error al compartir:', err);
                copiarEnlace();
            });
        } else {
            copiarEnlace();
        }
    });
    
    function copiarEnlace() {
        const input = document.createElement('input');
        input.value = window.location.href + '?invitado=' + encodeURIComponent(invitadoActual.nombre.toLowerCase());
        document.body.appendChild(input);
        input.select();
        document.execCommand('copy');
        document.body.removeChild(input);
        alert('Enlace copiado al portapapeles');
    }
});
    </script>
</body>
</html>
