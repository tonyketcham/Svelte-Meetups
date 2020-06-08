<header>
  <h1>Meetups</h1>
</header>

<style>
  header {
    position: fixed;
    width: calc(100% - 8px);
    top: 0;
    left: 0;
    height: 4rem;
    background: linear-gradient(45deg, #d53369 0%, #daae51 100%);
    display: flex;
    justify-content: center;
    align-items: center;
    /* box-shadow: 0 2px 12px rgba(0, 0, 0, 0.9), 0 2px 24px rgba(0, 0, 0, 0.9); */
    z-index: 1;
    border-top: 4px solid black;
    border: 4px solid black;
    border-radius: 7px;

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
    opacity: 0.25;
  }
  h1 {
    color: var(--Orange-White);
    text-shadow: 2px 2px 2px var(--Bastille);
    margin: 0;
    text-transform: uppercase;
  }
</style>
