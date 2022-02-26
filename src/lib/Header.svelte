<script lang="ts">
 import logo from '../assets/me.png'

 let links: {
   name: string
   id: string
   link: string
 }[] = [
   {
     name: "Twitter",
     id: "twitter",
     link: "https://twitter.com/s0n1c_dev"
   },
   {
     name: "GitHub",
     id: "github",
     link: "https://github.com/itss0n1c"
   },
   {
     name: "Discord",
     id: "discord",
     link: "https://discord.gg/VBTtGRg"
   },
   {
     name: "Reddit",
     id: "reddit",
     link: "https://reddit.com/u/S0n1cCA"
   }
 ]

</script>

<main>
  <div class="top-header">
    <img src={logo} alt="My Logo" />
    <div class="card">
      <div class="name">S0n1c</div>
      <div class="bio">21 year old full-stack Web Developer.</div>
      <div class="links">
        {#each links as link}
          <a href={link.link} class="button small tint-{link.id}" target="_blank" rel="noreferrer"><i class="fab fa-{link.id}"></i><span>{link.name}</span></a>
        {/each}
      </div>
    </div>
  </div>
</main>

<style lang="scss">
  @import '../styles/theme.scss';
  main {
    background: #f6f6f6;
    padding: 5rem 10rem;
    >.top-header {
      display: flex;
      justify-content: center;
      box-sizing: border-box;
      padding: 1rem 0;
      >img {
        width: 9rem;
        height: 9rem;
      }
      >.card {
        margin-left: 5rem;
        >.name, >.bio {
          word-wrap: break-word;
        }
        >.name {
          font-size: 2.5rem;
          font-weight: 800;
        }
        >.bio {
          font-size: 1rem;
          
          opacity: 0.6;
          padding: 1rem 0 0;
          
        }
        >.links {
          margin-top: 2rem;
          display: grid;
          row-gap: 1rem;
          column-gap: 1rem;
          grid-template-columns: repeat(4, 1fr);
          box-sizing: border-box;
          >.button {
            display:flex;
            justify-content: center;
            align-items: center;
          }
        }
      }
    }
  }

 
  @media only screen and (max-width: 820px) {
    main {
      padding: unset;
      >.top-header {
        grid-template-columns: unset;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        >.card {
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          margin-left:unset;
          >.links {
            grid-template-columns: repeat(2, 1fr);
          }
          >.bio {
            text-align: center;
          }
        }
      }
    }
  }

  

  @media(prefers-color-scheme: dark) {
    main {
      background: #1c1c1c;
      color: white;
    }

    .button.tint-github {
      background: #252525 !important;
      color: #ddd !important;
    }
  }


  
</style>