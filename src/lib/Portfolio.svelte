<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">

<script>
    import logoCiencias from '../assets/LogoCiencias.png'
    import appStore from '../assets/appstore.png'
    import googlePlay from '../assets/googleplay.png'

    const cienciasLink = 'https://play.google.com/store/apps/details?id=com.LionStudios.Ciencia'
</script>

<div class="bg-light about-container">
    <p>
    <h1 class="flex-block text-center title" > 
            <strong>
                Meu Trabalho 
            </strong> 
    </h1>

    <div class="work-info-container row justify-items-start align-items-center">
        <div class="col-3">
            <img src={logoCiencias} 
            class="rounded-circle float-start app-image align-self-center" alt="..."
        width="auto" height="200">
        </div>
        <div class="col-9">
            <h2>
                <strong> Ciências RA </strong>
            </h2>
            <p>
                Ciências RA é um aplicativo de realidade aumentada usado para auxiliar no aprendizado
                do conteúdo de Ciências do Ensino Fundamental
                <br><br>
                <strong>Tecnologias usadas:</strong> Unity, C#(.NET), EasyAR SDK
                <strong>Responsabilidades:</strong> Desenvolvimento de novas cenas, implementação de UI responsiva, publicação para Android
            </p>
            <a href={cienciasLink}>
                <img src={googlePlay} height="40px" width="auto" alt="Play Store">
            </a>
        </div>
        
    </div>
</div>

<style>
    .title {
        padding-top: 20px;
        margin-bottom: 20px;
    }

    .about-container {
        padding-left: 24px;
        padding-right: 24px;    
        min-width: 600px;
    }

    .work-info-container {
        padding: 1rem 0;
        font-size: 1.5rem;
        font-weight: 300;

        margin-right: 5%;
        margin-left: 5%;
    }

    .app-image {
        margin-right: 20px;
    }

</style>