<script>
    import 'animate.css';
    import { base } from '$app/paths'; 
    import { scrollTo, scrollRef, scrollTop } from 'svelte-scrolling'

    
</script>

<main>
    <div class="first"  use:scrollRef={'home'}>
        <div class="head-container">
        <h1 class="head-text"> Portfolio</h1>
        
        </div>
        <a href="#about" class="scroll-down" use:scrollTo={'about'}>
            <span>↓</span>
        </a>
    </div>
    <div class="about" id="about" use:scrollRef={'about'}>
        
        <h2>WELCOME.</h2>
        <img src="https://i.pinimg.com/736x/d9/59/ce/d959ce169245d962fae688d08e4dca5a.jpg" class="angel">
        <img src="/swirles.png" class="swirl">
        
        <div class="sect">
        <h1>Who am I?</h1>  
        <p></p>
        </div>
        
    </div>
    <div class="projects" id="projects" use:scrollRef={'projects'}>
        <h1 class="title-1">PROJECTS</h1>
        <div class="contain">
            <a href="{base}/sewing">
                <div class="la">
                <h1>Sewing</h1>
                <p>Explore my sewing projects and designs.</p>
                </div>
            </a>
            <a href="{base}/drawings">
                <div class="la">
                <h1>Sewing</h1>
                <p>Explore my sewing projects and designs.</p>
                </div>
            </a>
        </div>
    </div>
    <div class="contacts" id="contacts" use:scrollRef={'contacts'}>

        
    </div>
</main>

<style>

    main{
        scroll-behavior: smooth;
        overflow-x: hidden;
    }

    .first{
    width: 100vw;
    height: 100vh;
    background: 
        linear-gradient(to bottom, transparent 70%, black 100%),
        url(/roundbald.png) no-repeat;
    background-size: cover;
}
    
    span {
        display: inline-block;
        width: 6rem;
        height: 6rem;
        background-color: #ffffff;
        font-size:3rem; 
        color: black;
        line-height: 3rem;
        text-align: center; 
        border-radius: 50%;
        position: relative;
        top: 65%;
        align-content: center;
        left: 49%;
        border: solid 2px black;
     }

     span:hover{
        border: solid 2px white;
        background-color: black;
        color: white;
        transition: 400ms ease-in-out;
     }


    .about {
        width: 100vw;
        height: 100vh;
        background-color: black;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }

    .about .angel{
        width: 600px + 15%;
        height: 397px + 15%;
        position: relative;
        left: -15%;
        top: -5%;
}

.about .swirl{
    width: 199px;
    position: relative;
    left:-19%;
    top:25%;
}


     h2{
        font-family: "Courier New", Courier, "Lucida Sans Typewriter";
        z-index: 11;
        position: relative;
        font-size: 80px;
        top:-30%;
        left: 8%;
    }



    .sect{
        width: 40vw;
        height: 40vh;
        background-color: rgba(255, 255, 255, 0.612) ;
        position: relative;
        left: -10%;
    }

.head-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 20vh;
    width: 40vw;
    top: 30%;
    left: 10px;
    position: relative;
    background: #ffffff;
    font-family: 'TFMixVF', sans-serif;
    overflow: hidden;
}



.head-text {
    font-size: 8rem;
    padding: 50px;
    font-weight: bold;
    color: transparent;
    background-image: url('https://i.pinimg.com/originals/81/f6/5b/81f65bff8563907a8a673c6306fd83a2.gif'); 
    background-size: 100% ;
    background-position: 0 50%;
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;

}

.projects {
        width: 100vw;
        height: 100vh;
        background-color: black;
        align-content: start;
        justify-items: center;
    }

.title-1{
    font-family: Copperplate, "Copperplate Gothic Light", fantasy;
    font-weight: bolder;
    font-size: 50px;
    margin-top: 60px;
}
.contain{
    margin-top: 150px;
    display: flex;
    flex-direction: row;
    width: 100%;
    height: auto;
    justify-content: center;
    align-items: center;
}

.contain a{
    margin: 100px;
    margin-top: 0;
    width: 450px;
    height: 450px;
    background:url('/sewplaceholder.png');
    background-size:cover ;
}

.contain a:hover{
    transform: scale(1.05);
    transition: transform 0.3s ease-in-out;

}

.contain .la:hover{
opacity: 1;
}
.contain .la{
    opacity: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.4);
}

.contacts{
    width: 100vw;
        height: 100vh;
        background-color: black;
        align-content: start;
        justify-items: center;
}

@font-face {
  font-family: 'TFMixVF';
  src: local('JangerRegular-lgYWq'), local('JangerRegular-lgYWq'), local('JangerRegular lgYWq'),
			local('JangerRegular-lgYWq'), url('/static/JangerRegular-lgYWq.otf');
}



</style>