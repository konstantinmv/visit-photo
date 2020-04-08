  <script>
    import { navigate } from "svelte-routing";

    const goToNested = () => {
      navigate("/about", { replace: true });
    }
    const [instagramIcon, telegramIcon, githubIcon] = [
      'images/entrance/Icon_Insta.png',
      'images/entrance/Icon_TG.png',
      'images/entrance/Icon_GH.png'
    ];
    console.log('instagram', instagramIcon)

  </script> 

  <div class="imageWelcome" style="background-image: url('images/entrance/000040.JPG')">
    <div class="infoDiv">
      <p class="homeText">KOSTIK PHOTOKROF</p>
      <button class="enterButton" on:click={goToNested}>
      Come in
      </button>
    </div>
    <div class="socialMediaDiv">
      <a href="InstagramLink"><img src={instagramIcon} alt="instaClick"></a>
      <a href="TelegramLink"><img src={telegramIcon} alt="telegaClick"></a>
      <a href="GitHubLink"><img src={githubIcon} alt="gitHubClick"></a>
    </div>
  </div>

  <style>

    .homeText {
      display: flex;
      color: white;
      font-size: 4em;
      margin: 0.5em;
      width: 15vw;
      justify-content: center;
    }

    .enterButton {
      background-color: transparent;
      border: 1px solid white;
      font-size: 2em;
      color: white;
    }

    .enterButton:hover {
      background-color: white;
      color: gray;
    }

    .socialMediaDiv {
      display: flex;
      flex-direction: column;
      position: absolute;
      top: 40vh; 
      right: 5vw;
    }

    .socialMediaDiv img {
      height: 40px;
      width: 40px;
      margin: 0.5em;
      /* color: white; */
    }

    .infoDiv {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
    }

    .imageWelcome {
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      background-size: cover;
      background-repeat: no-repeat;
      height: 100vh;
      /* box-sizing: border-box; */
    }

  </style>