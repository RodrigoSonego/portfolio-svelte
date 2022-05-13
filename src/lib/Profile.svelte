<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.0.7/css/all.css">

<script>
    import githubLogo from "../assets/github-logo.png"
    import gmailLogo from "../assets/gmail-logo.png"
    import linkedinLogo from "../assets/linkedin-logo.png"

    const githubLink = 'https://github.com/RodrigoSonego'
    const mailLink = 'rodrigoasonego@gmail.com'
    const linkedinLink = 'https://www.linkedin.com/in/rodrigo-sônego-2a9aa4211/'

    const logoSize = 30
</script>

<head>
    <script src="https://kit.fontawesome.com/f006e1eac3.js" crossorigin="anonymous"></script>
</head>

<div class="bg-dark container-fluid d-flex header">
    <div class="align-self-center container-fluid">
        <div class="flex-row">
            <img src="https://pbs.twimg.com/profile_images/1293925081542995971/s2la3KS9_400x400.png" class="rounded-circle mx-auto img-responsive d-block profile-image" alt="..."
            width="200px" height="200px">
        </div>

        <div class="container-fluid">
            <div class="flex-row">
                <h1 class="text-light flexbox text-center title">
                    Rodrigo Sônego
                </h1>
            </div>

            <div class="container-fluid icon-row">
                <div class="row align-center center d-flex">
                    <div class="col-sm-4">
                        <a class="thumbnail" href={githubLink} target="_blank">
                            <img src={githubLogo} alt="Github" class="img-responsive"
                            width="{logoSize}px" height="{logoSize}px">
                        </a>
                    </div>
            
                    <div class="col-sm-4">
                        <a class="thumbnail" href="mailto:{mailLink}" target="_blank">
                            <img src={gmailLogo} alt="Email" class="img-responsive"
                            width="auto" height="{logoSize}px">
                        </a>
                    </div>
                    <div class="col-sm-4">
                        <a class="thumbnail" href={linkedinLink} target="_blank">
                            <img src={linkedinLogo} alt="Linkedin" class="img-responsive"
                            width="{logoSize}px" height="{logoSize}pxpx">
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div> 
</div>

<div class="bg-light about-container" id="about">
    <div class="about-info-container">
       <p> 
        <h1 class="flex-block text-left" > 
          <strong>
            Olá! 
          </strong> 
        </h1>
       <p class="flex-block text-left"> 
            Meu nome é Rodrigo Sônego.
            <br>
            Sou acadêmico do curso de <strong>Ciência da computação</strong>, com experiência em
            <strong>desenvolvimento de jogos, sistemas</strong> e <strong>aplicações de reliadade aumentada</strong>.
            <br>
            Sinta-se à vontade para entrar em contato ou conferir meu trabalho abaixo
       </p>
    </div>
</div>

<style>
    .profile-image {
        padding-top: 10px;
    }

    /*CENTER COLUMN */
    .align-center {
        text-align: center;
    }
    /*CENTER DIV*/
    .center {
        margin: 0 auto;
        width: 20%;
        display: flex;
        min-width: 100px;
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

    /* @media (min-width: 600px) */
    .about-container {
        padding-left: 24px;
        padding-right: 24px;    
        min-width: 600px;
        margin-bottom: 3rem;
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
</style>