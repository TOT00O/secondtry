<script>
    import 'animate.css';
    import { base } from '$app/paths'; 

</script>

<main>
    <div class="first">
        <div class="head-container">
        <h1 class="head-text"> Portfolio</h1>
        </div>

    </div>
    <div class="about" id="about">
        <div class="sect">
        <h1>About</h1>  
        <p>Welcome to my portfolio! I'm a passionate developer with a love for creating innovative solutions. Explore my projects and get to know me better.</p>
        </div>
        
    </div>
</main>

<style>

    .first{
        width: 100vw;
        height: 100vh;
        background:url(/lessbald.png) no-repeat ;
        background-size: cover;
    }

    .about {
        width: 100vw;
        height: 100vh;
        background-color: black;
        align-content: center;
        justify-items: center;
    }

    .sect{
        width: 70vw;
        height: 60vh;
        background-color: rgba(255, 255, 255, 0.612) ;
    }

.head-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 20vh;
    width: 40vw;
    top: 30%;
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

@font-face {
  font-family: 'TFMixVF';
  src: local('JangerRegular-lgYWq'), local('JangerRegular-lgYWq'), local('JangerRegular lgYWq'),
			local('JangerRegular-lgYWq'), url('/static/JangerRegular-lgYWq.otf');
}

</style>