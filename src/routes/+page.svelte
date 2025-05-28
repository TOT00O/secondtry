<script>
    import 'animate.css';
    import { base } from '$app/paths'; 
    import { scrollTo, scrollRef, scrollTop } from 'svelte-scrolling'
    import Flickity from 'svelte-flickity';
  const options = {
    wrapAround: true,
    cellAlign: 'center'
  };
  

  let images =[
    
    `${base}/angel.png`,
    `${base}/face.png`,
    `${base}/amazing.png`,
    `${base}/back.png`,
    `${base}/regein.png`
  ]

      let selectedImage = null;
    let showPopup = false;
    
    function openPopup(image) {
        selectedImage = image;
        showPopup = true;
        document.body.style.overflow = 'hidden'; // Prevent scrolling when popup is open
    }
    
    function closePopup() {
        showPopup = false;
        document.body.style.overflow = 'auto'; // Re-enable scrolling
    }
  

</script>

<main>
    <div class="first"  use:scrollRef={'home'}>
        <div class="head-container">
        <h1 class="head-text"> PORTFOLIO</h1>
        
        </div>
        <a href="#about" class="scroll-down" use:scrollTo={'about'}>
            <span>↓</span>
        </a>
    </div>
    <div class="about" id="about" use:scrollRef={'about'}>
        
        <img src="{base}/me.png" class="pfp">

        <h2>Who am i?</h2>
        <h3>I am a student who aspires to work with fashion and art. Creativity has always been at the heart of everything I do, and I’m passionate about expressing ideas through visual design, clothing, and aesthetics. I'm constantly exploring new styles, trends, and artistic techniques, and I hope to build a career that allows me to merge self-expression with innovation.
        
 </h3>
        
        
    </div>
    <div class="art" id="art" use:scrollRef={'art'}>
        <div class="spin">
            <h1 class="title-1">ART</h1>
        </div>
        <div class="contain">
            {#each images as image}
                <img src={image} alt="Artwork" on:click={() => openPopup(image)} class="art-image">
            {/each}
        </div>
        <div class="spin"></div>
    </div>


    
    {#if showPopup}
        <div class="popup-overlay" on:click={closePopup}>
            <div class="popup-content" on:click|stopPropagation>
                <button class="close-btn" on:click={closePopup}>✕</button>
                <img src={selectedImage} alt="Enlarged artwork" class="enlarged-image">
            </div>
        </div>
    {/if}
    <div class="projects" id="projects" use:scrollRef={'projects'}>
        <h1 class="title-1">"PROJECTS"</h1>
        <div class="contain">
            <br>
            <br>
            <Flickity {options} >
                <div class="carousel-cell" id="cell1"on:click={() => window.location.href = `${base}/project1`}>Mad as a hatter</div>
                <div class="carousel-cell" on:click={() => window.location.href = `${base}/project2`}>Slide 2</div>
                <div class="carousel-cell" on:click={() => window.location.href = `${base}/project3`}>Slide 3</div>
            </Flickity>
        </div>
    </div>

</main>

<style>

   .art img {
        height: 500px;
        cursor: pointer;
        transition: transform 0.3s ease;
    }

     .art img:hover {
        transform: scale(1.02);
    }

    .popup-overlay {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: rgba(0, 0, 0, 0.9);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 1000;
        animation: fadeIn 0.3s ease-out;
    }
    
    .popup-content {
        position: relative;
        max-width: 90vw;
        max-height: 90vh;
    }
    
    .enlarged-image {
        max-height: 90vh;
        max-width: 90vw;
        object-fit: contain;
    }

     .close-btn {
        position: absolute;
        top: -40px;
        right: 0;
        background: none;
        border: none;
        color: white;
        font-size: 2rem;
        cursor: pointer;
        padding: 0.5rem;
    }
    
    @keyframes fadeIn {
        from { opacity: 0; }
        to { opacity: 1; }
    }

 #cell1{
    font-family:Courier New, monospace;
    background:url(https://i.pinimg.com/736x/4f/7d/dc/4f7ddca39aa437b72acc51df3aeaf73d.jpg);
 }

  .carousel-cell {
    width: 50%;
    height: 300px;
    margin-right: 20px;
    background: #8C8;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 2em;
  }

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

    .about h3{
        font-size: 20px;
        width: 50vw;
        font-family:Georgia, 'Times New Roman', Times, serif;
        position: relative;
        left:40.5%;
        top:-73%;


    }

  

.head-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 20vh;
    width: 46vw;
    top: 20%;
    left: 10px;
    position: relative;
    background: #ffffff;
    font-family: 'TFMixVF', sans-serif;
    overflow: hidden;
}



.head-text {
    font-size: 8.2rem;
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
.projects .contain{
    margin-top: 150px;
    background-color: #ffffff;
    width: 100%;
    height: 50vh;

}



.art{
    width: 100vw;
        height: 100vh;
        background-color: black;
        align-content: start;
        justify-items: center;
}
.art .contain{
    height: 70vh;
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 10px;
    overflow-x: scroll;
}

.spin{
    width: 100vw;
    height: 10vh;
    background-color: #ffffff;
}

.art .title-1{
        font-family: Copperplate, "Copperplate Gothic Light", fantasy;
    font-weight: bolder;
    font-size: 50px;
    margin-top: 60px;
    text-align: center;
    color: black;
    padding-top: 30px;
}



@font-face {
  font-family: 'TFMixVF';
  src: local('JangerRegular-lgYWq'), local('JangerRegular-lgYWq'), local('JangerRegular lgYWq'),
			local('JangerRegular-lgYWq'), url('/static/JangerRegular-lgYWq.otf');
}



</style>