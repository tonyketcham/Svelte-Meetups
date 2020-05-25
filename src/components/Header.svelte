<header>
  <h1>Meetups</h1>
</header>

<style>
  header {
    position: fixed;
    width: 100%;
    top: 0;
    left: 0;
    height: 4rem;
    background: linear-gradient(45deg, #d53369 0%, #daae51 100%);
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0 2px 12px rgba(0, 0, 0, 0.9), 0 2px 24px rgba(0, 0, 0, 0.9);
    z-index: 1;

    /* 0 2px 48px rgb(215, 111, 93, 0.75)
    0 2px 14px rgb(215, 111, 93, 0.15) */
  }
  header::after {
    content: "";
    position: absolute;
    background: inherit;
    border-radius: inherit;
    width: inherit;
    height: inherit;
    transform: translate(0px, 20px) scale(1.1);
    z-index: -1;
    filter: blur(18px);
    opacity: 0.45;
  }
  h1 {
    color: white;
    font-family: "Fira Code", Courier, monospace;
    margin: 0;
  }
</style>
