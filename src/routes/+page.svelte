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
        
        <img src="/me.png" class="pfp">

        <h2>Who am i?</h2>
        
        
    </div>
    <div class="projects" id="projects" use:scrollRef={'projects'}>
        <h1 class="title-1">PROJECTS</h1>
        <div class="contain">

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
    white no-repeat;
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


    }

     .pfp{
        width: 40%;
        position: relative;
        top:5%;
    }


    .about h2{
        font-size: 100px;
        position: relative;
        left:40%;
        top:-80%;
        font-family:Georgia, 'Times New Roman', Times, serif;
    }

  

.head-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 20vh;
    width: 45vw;
    top: 20%;
    left: 10px;
    position: relative;
    background: #ffffff;
    font-family: 'TFMixVF', sans-serif;
    overflow: hidden;
}



.head-text {
    font-size: 9rem;
    padding: 50px;
    font-weight: bold;
    color: transparent;
    background-image: url('https://i.pinimg.com/originals/81/f6/5b/81f65bff8563907a8a673c6306fd83a2.gif'); 
    background-size: 100% ;
    background-position: 0 50%;
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
        filter: drop-shadow(5px 20px 4px rgba(0, 0, 0, 0.6));

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
    background-color: #ffffff;
    display: flex;
    flex-direction: row;
    width: 100%;
    height: 50vh;
    justify-content: center;
    align-items: center;
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