<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">

<nav class="sticky-top navbar navbar-expand-sm navbar-dark bg-dark text-light">
    <div class="container-fluid">
        <span class="navbar-brand mb-0 h1 title texto-navbar"> Rodrigo Sônego </span>
        <div class="collapse navbar-collapse">
            <!-- gambiarra com ul vazia aqui só pra deixar os itens pra esquerda -->
            <ul class="navbar-nav me-auto my-2 my-lg-0 navbar-nav-scroll" style="--bs-scroll-height: 100px;"></ul>

            <div class="texto-navbar navbar-nav d-flex justify-content-lg-end me-2">
                <button class="nav-link active" class:selected={isAboutOnFrame} aria-current="page" on:click={()=> {goToSection('about')}} id="about-button">
                    Sobre
                </button>
                <button class="nav-link active" class:selected={isPortfolioOnFrame} on:click={()=> {goToSection('portfolio')}} id="portfolio-button">Portfolio</button>
                <button class="nav-link active" class:selected={isContactOnFrame} on:click={()=> {goToSection('contact')}} id="contact-button">Contato</button>
            </div>
        </div>
    </div>
</nav>

<style>
    .title {
        font-size: 1.25rem;
    }

    .texto-navbar{
        font-family: "Roboto", "Helvetica", "Arial", sans-serif;
        font-weight: 500;
        line-height: 1.6;
    }

    button {
        border: none;
        background-color: transparent;
    }

    button:hover {
        text-decoration-line: underline;
        text-underline-offset: 5px;
        text-decoration-color: rgb(105, 105, 105);
    }

    .selected {
        text-decoration-line: underline;
        text-underline-offset: 5px;
    }

</style>

<script>
    import { onMount } from 'svelte';
    
    function goToSection(sectionId) {
        const section = document.getElementById(sectionId);
        const yOffset = -60;
        const y = section.getBoundingClientRect().top + window.pageYOffset + yOffset;
        
        window.scrollTo({top: y, behavior:"smooth"})
    }
    
    let aboutSect = null
    let portfolioSect = null
    let contactSect = null
    
    let isAboutOnFrame = true
    let isPortfolioOnFrame = false
    let isContactOnFrame = false
      
    function onScrollSection(){
        let st1 = document.documentElement.scrollTop
        let st2 = document.body.scrollTop
        let sh = document.documentElement.scrollHeight
        let ch = document.documentElement.clientHeight

        let sectionIndex = (st1 + st2) / (sh - ch) * 3;

        console.log(sectionIndex)
        if(sectionIndex >= 0 && sectionIndex <= 1.3) {
            isAboutOnFrame = true;
            isPortfolioOnFrame = false;
            isContactOnFrame = false;
        }
        else if (sectionIndex > 1 && sectionIndex <= 2.9) {
            isAboutOnFrame = false;
            isPortfolioOnFrame = true;
            isContactOnFrame = false;
        }
        else {
            isAboutOnFrame = false
            isPortfolioOnFrame = false;
            isContactOnFrame = true;
        }
    }

    document.addEventListener('scroll', onScrollSection)

    onMount(() => { 
        aboutSect = document.getElementById("about")
        portfolioSect = document.getElementById("portfolio")
        contactSect = document.getElementById("contact")
    })

    
</script>