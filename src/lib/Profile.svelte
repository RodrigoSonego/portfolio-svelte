<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.0.7/css/all.css">

<script>
    import { onMount } from 'svelte/internal';
    import { fade } from 'svelte/transition'

    import githubLogo from "../assets/github-logo.png"
    import gmailLogo from "../assets/gmail-logo.png"
    import linkedinLogo from "../assets/linkedin-logo.png"
    import euFoto from "../assets/eu.jpg"

    const githubLink = 'https://github.com/RodrigoSonego'
    const mailLink = 'rodrigoasonego@gmail.com'
    const linkedinLink = 'https://www.linkedin.com/in/rodrigo-sônego-2a9aa4211/'

    const logoSize = 30

    let isMounted = false;

    onMount(() => { isMounted = true; });
</script>

<head>
    <script src="https://kit.fontawesome.com/f006e1eac3.js" crossorigin="anonymous"></script>
</head>

<div class="bg-dark container-fluid d-flex header">
    <div class="align-self-center container-fluid">
        <div class="flex-row">
            <img src={euFoto} class="rounded-circle mx-auto img-responsive d-block profile-image" alt="..."
            width="200px" height="200px">
        </div>

        <div class="container-fluid">
            <div class="flex-row">
                <h1 class="text-light flexbox text-center title">
                    Rodrigo Sônego
                </h1>
            </div>

            <div class="container icon-row jusitfy-self-center">
                <div class="row center">
                    <div class="col-4">
                        <a class="" href={githubLink} target="_blank">
                            <img src={githubLogo} alt="Github" class="contact-icon justify-self-center"
                            width="{logoSize}px" height="{logoSize}px">
                        </a>
                    </div>
            
                    <div class="col-4">
                        <a class="" href="mailto:{mailLink}" target="_blank">
                            <img src={gmailLogo} alt="Email" class="contact-icon justify-self-center"
                            width="auto" height="{logoSize}px">
                        </a>
                    </div>
                    <div class="col-4">
                        <a class="" href={linkedinLink} target="_blank">
                            <img src={linkedinLogo} alt="Linkedin" class="contact-icon justify-self-center"
                            width="{logoSize}px" height="{logoSize}pxpx">
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div> 
</div>
{#if isMounted}
    <div class="bg-light about-container" id="about">
        <div class="about-info-container">
        <p> 
            <h1 transition:fade="{{duration: 1000}}" class="flex-block text-left" > 
            <strong>
                Olá! 
            </strong> 
            </h1>
        <p transition:fade="{{duration: 1000}}" class="flex-block text-left"> 
                Meu nome é Rodrigo Sônego.
                <br>
                Sou acadêmico do curso de <strong>Ciência da computação</strong>, com experiência em
                <strong>desenvolvimento de jogos, sistemas</strong> e <strong>aplicações de reliadade aumentada</strong>.
                <br>
                Sinta-se à vontade para entrar em contato ou conferir meu trabalho abaixo
        </p>
        </div>
    </div>
{/if}

<style>
    .profile-image {
        padding-top: 10px;
    }

    .center {
        margin: 0 auto;
        width: 20%;
        display: flex;
    }

    .icon-row {
        margin-top: 25px;
    }

    .title {
        font-size: 3rem;
        margin: 10px;
        font-family: "Roboto", "Helvetica", "Arial", sans-serif;;
        font-weight: 400;
    }

     @media (min-width: 600px){
         .about-container {
             padding-left: 24px;
             padding-right: 24px;    
             /* min-width: 600px; */
             margin-bottom: 3rem;
         }
     }

    .about-info-container {
        padding: 1rem 0;
        font-size: 1.5rem;
        font-weight: 300;

        margin-right: 10%;
        margin-left: 10%;
    }

    .header {
        min-height: 500px;
    }

    .contact-icon {
        transform: scale(1);
        transition: transform .2s;
    }

    .contact-icon:hover {
        transform: scale(1.5);
    }
</style>