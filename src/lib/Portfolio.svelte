<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">

<script>
    import { fade, fly } from 'svelte/transition'
    import {onMount} from 'svelte'

    import logoCiencias from '../assets/LogoCiencias.png'
    import logoCorpoHumano from '../assets/LogoCorpo.png'
    import logoMatematica from '../assets/LogoMatematica.png'

    import googlePlay from '../assets/googleplay.png'
    
    const cienciasLink = 'https://play.google.com/store/apps/details?id=com.LionStudios.Ciencia'
    const matematicaLink = 'https://play.google.com/store/apps/details?id=br.com.lionstudios.matematicara'
    const corpoHumanoLink = 'https://play.google.com/store/apps/details?id=com.LionStudios.LCHRA'

    let cienciasSection;
    let matSection;
    let corpoSection;

    let hasCienciasAppeared = false;
    let hasMatematicaAppeared = false;
    let hasCorpoAppeared = false;

    onMount(() => {
        cienciasSection = document.getElementById('ciencias')
        matSection = document.getElementById('matematica')
        corpoSection = document.getElementById('corpohumano')

        console.log(!cienciasSection)
        console.log(!matSection)
        console.log(!corpoSection)
    });

    // TODO: Criar uma variavel pra ver se tal div entrou no frame
    
    
    function hasEnteredViewport(element) {
        const rect = element.getBoundingClientRect();
        const offset = rect.height/3;
        
        return (
            rect.top >= 0 &&
            rect.left >= 0 &&
            rect.bottom <= ((window.innerHeight + offset) || document.documentElement.clientHeight + offset) &&
            rect.right <= (window.innerWidth || document.documentElement.clientWidth)
            );        
    }

    function checkIfElementsEnteredViewport()
    {
        if(hasCienciasAppeared === false){ hasCienciasAppeared = hasEnteredViewport(cienciasSection); }
        if(hasMatematicaAppeared ===false){ hasMatematicaAppeared = hasEnteredViewport(matSection); }
        if(hasCorpoAppeared ===false){ hasCorpoAppeared = hasEnteredViewport(corpoSection); }

    }

    document.addEventListener('scroll', checkIfElementsEnteredViewport);

</script>

<div class="bg-light d-flex justify-content-center" id="portfolio">
    <div class="about-container">
        <p>
            <h1 class="flex-block text-center title" > 
                    <strong>
                        Meu Trabalho 
                    </strong> 
            </h1>
            <hr>
        <div id="ciencias">
            {#if hasCienciasAppeared}
                <div transition:fly="{{x: -500, duration: 3500}}"
                 class="work-info-container row align-items-center">
                    <div class="col-3 d-flex justify-content-center">
                        <img src={logoCiencias} 
                        class="app-image align-self-center" alt="..."
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
                            <br>
                            <strong>Responsabilidades:</strong> Desenvolvimento de novas cenas, implementação de UI responsiva, publicação para Android
                        </p>
                        <a class="play-store-btn" href={cienciasLink} target="_blank">
                            <img src={googlePlay} height="40px" width="auto" alt="Play Store">
                        </a>
                    </div>
                </div>       
            {/if}
        </div>
        
        <div id="matematica">
            {#if hasMatematicaAppeared}
                <div transition:fly="{{x: 500, duration: 4000}}"
                 class="work-info-container row align-items-center">
                    <div class="col-9">
                        <h2>
                            <strong> Matemática RA </strong>
                        </h2>
                        <p>
                            Matemática RA é um aplicativo de realidade aumentada usado para auxiliar no aprendizado
                            do conteúdo de Matemática do Ensino Fundamental
                            <br><br>
                            <strong>Tecnologias usadas:</strong> Unity, C#(.NET), EasyAR SDK
                            <br>
                            <strong>Responsabilidades:</strong> Desenvolvimento de novas cenas, implementação de UI responsiva, publicação para Android
                        </p>
                        <a class="play-store-btn" href={matematicaLink} target="_blank">
                            <img src={googlePlay} height="40px" width="auto" alt="Play Store">
                        </a>
                    </div>
                    <div class="col-3 d-flex justify-content-center">
                        <img src={logoMatematica} 
                        class="app-image-right" alt="..."
                    width="auto" height="200">
                    </div>
                </div>
                
            {/if}
        </div>
        
        <div id="corpohumano">
            {#if hasCorpoAppeared}
                <div transition:fly="{{x: -500, duration: 5000}}"
                class="work-info-container row align-items-center">
                    <div class="col-3 d-flex align-content-center justify-content-center">
                        <img src={logoCorpoHumano} 
                        class="app-image" alt="..."
                    width="auto" height="200">
                    </div>
                    <div class="col-9">
                        <h2>
                            <strong> Corpo Humano RA </strong>
                        </h2>
                        <p>
                            Corpo Humano RA é um aplicativo de realidade aumentada usado para auxiliar no aprendizado
                            sobre o corpo humano no Ensino Fundamental
                            <br><br>
                            <strong>Tecnologias usadas:</strong> Unity, C#(.NET), EasyAR SDK
                            <br>
                            <strong>Responsabilidades:</strong> Desenvolvimento de novas cenas, implementação de UI responsiva, publicação para Android
                        </p>
                        <a class="play-store-btn" href={corpoHumanoLink} target="_blank">
                            <img src={googlePlay} height="40px" width="auto" alt="Play Store">
                        </a>
                    </div>
                </div>
            {/if}
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
        padding-bottom: 5%;
        min-width: 600px;
        max-width: 75%;
    }

    .work-info-container {
        padding: 1rem 0;
        font-size: 1.5rem;
        font-weight: 300;

        margin-right: 3%;
        margin-left: 3%;
    }

    .app-image {
        margin-right: 20px;
    }

    .app-image-right {
        margin-left: 20px;
    }

    .play-store-btn:hover {
        opacity: 75%;
    }
</style>