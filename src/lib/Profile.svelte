<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.0.7/css/all.css">

<script>
    import githubLogo from "../assets/github-logo.png"
    import gmailLogo from "../assets/gmail-logo.png"
    import linkedinLogo from "../assets/linkedin-logo.png"

    const githubLink = 'https://github.com/RodrigoSonego'
    const mailLink = 'rodrigoasonego@gmail.com'
    const linkedinLink = 'https://www.linkedin.com/in/rodrigo-sônego-2a9aa4211/'

    const logoSize = 40
</script>

<head>
    <script src="https://kit.fontawesome.com/f006e1eac3.js" crossorigin="anonymous"></script>
</head>

<div class="bg-dark center-block">
    <img src="https://pbs.twimg.com/profile_images/1293925081542995971/s2la3KS9_400x400.png" class="rounded-circle mx-auto img-responsive d-block" alt="..."
    width="250px" height="250px">
    <!-- <img src={githubLogo} class="rounded-circle mx-auto img-responsive d-block" alt="..."
    width="250px" height="250px"> -->

    <div class="container">
        <div class="row">
            <h1 class="text-light flexbox text-center title">
                Rodrigo Sônego
            </h1>
        </div>


        <div class="row">
            <div class="center icon-row">
                <div class="col-lg-4 col-md-4 col-xs-4-thumb align-center">
                    <a class="thumbnail" href={githubLink} target="_blank">
                        <img src={githubLogo} alt="Github" class="img-responsive"
                        width="{logoSize}px" height="{logoSize}px">
                    </a>
                </div>
        
                <div class="col-lg-4 col-md-4 col-xs-4-thumb align-center">
                    <a class="thumbnail" href="mailto:{mailLink}" target="_blank">
                        <img src={gmailLogo} alt="Email" class="img-responsive"
                        width="{logoSize}px" height="{logoSize}px">
                    </a>
                </div>
                <div class="col-lg-4 col-md-4 col-xs-4-thumb align-center">
                    <a class="thumbnail" href={linkedinLink} target="_blank">
                        <img src={linkedinLogo} alt="Linkedin" class="img-responsive"
                        width="{logoSize}px" height="{logoSize}pxpx">
                    </a>
                </div>

            <!-- <div class="col align-center"> <img style="width: 25%; height: 25%" src="https://image.ibb.co/ckA7ka/mr_marbles.png" alt="Mister Marbles head tilt"> </div>
            <div class="col align-center"> <img style="width: 25%; height: 25%" src="https://image.ibb.co/bTMKyv/kermit.png" alt="Kermit the Dog"> </div>
            <div class="col align-center"> <img style="width: 25%; height: 25%" src="https://image.ibb.co/ki8tQa/peach.png" alt="Peach posing magestically"> </div> -->
            </div>
        </div>
    </div>
    
</div>

<style>
    /*CENTER COLUMN */
    .align-center {
        text-align: center;
    }
    /*CENTER DIV*/
    .center {
        margin: 0 auto;
        width: 30%;
        display: flex;
    }

    .icon-row {
        margin-top: 10px;
    }

    .title {
        margin: 10px;
        font-family:  "Roboto", "Helvetica", "Arial", sans-serif;;
        font-weight: 400;
    }
</style>