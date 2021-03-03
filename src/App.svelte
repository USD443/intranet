<script>
  // Import Components
  import Dashboard from "./components/Dashboard.svelte";
  import Elementary from "./components/Elementary.svelte";
  import Middle from "./components/Middle.svelte";
  import High from "./components/High.svelte";
  import Staff from "./components/Staff.svelte";

  // Import onMount
  import { onMount } from "svelte";

  // Create variables
  let aside;
  let toggle = false;
  let tSlice;
  let mSlice;
  let bSlice;
  let pageViews = "";

  // Update page views from CountAPI

  onMount(() => {
    fetch("https://api.countapi.xyz/update/usd443.org/usd443counter/?amount=1")
      .then((res) => res.json())
      .then((res) => {
        console.log(res.value);
        pageViews = parseInt(res.value).toLocaleString("en");
      })
      .catch((err) => {
        console.log(err);
      });
  });

  // Handle burger animation, toggle mobile menu
  const toggleBurger = () => {
    if (toggle) {
      aside.style = "right: -100%";
      mSlice.style = "opacity: 1";
      tSlice.style = "transform: rotate(0) translateY(0)";
      bSlice.style = "transform: rotate(0) translateY(0)";
      toggle = false;
    } else {
      aside.style = "right: 0";
      mSlice.style = "opacity: 0";
      tSlice.style = "transform: rotate(45deg) translateY(11px)";
      bSlice.style = "transform: rotate(-45deg) translateY(-11px)";
      toggle = true;
    }
  };
  // Which component gets loaded first
  let loadComponent = "Dashboard";
</script>

<!-- Primary Wrapper -->
<div class="wrapper">
  <!-- Mobile Menu -->
  <aside bind:this={aside}>
    <div class="aside-wrapper">
      <ul class="links-container">
        <li
          class={loadComponent === "Dashboard" ? "link active-menu" : "link"}
          on:click={() => {
            loadComponent = "Dashboard";
            toggleBurger();
          }}
        >
          Dashboard
        </li>
        <li
          class={loadComponent === "Elementary" ? "link active-menu" : "link"}
          on:click={() => {
            loadComponent = "Elementary";
            toggleBurger();
          }}
        >
          Elementary School
        </li>
        <li
          class={loadComponent === "Middle School" ? "link active-menu" : "link"}
          on:click={() => {
            loadComponent = "Middle School";
            toggleBurger();
          }}
        >
          Middle School
        </li>
        <li
          class={loadComponent === "High School" ? "link active-menu" : "link"}
          on:click={() => {
            loadComponent = "High School";
            toggleBurger();
          }}
        >
          High School
        </li>
        <li
          class={loadComponent === "Teachers & Staff" ? "link active-menu" : "link"}
          on:click={() => {
            loadComponent = "Teachers & Staff";
            toggleBurger();
          }}
        >
          Teachers & Staff
        </li>
      </ul>
      <div class="contact">
        <p>Technology Help Desk: (620) 371-1080</p>
        <br />
        <p>Coded & Maintained By: <span>Carlos Rodriguez</span></p>
        <a href="mailto:rodriguez.carlos@usd443.org?subject=USD443 Intranet">rodriguez.carlos@usd443.org</a>
        <br />
        <p class="pageviews" style={pageViews != "" ? "" : "visibility: hidden"}>{pageViews} views</p>
      </div>
    </div>
  </aside>

  <!-- Sub Primary Wrapper -->
  <main class="main-wrapper">
    <!-- Application Title -->
    <div class="main-title-container">
      <div class="titles">
        <h2>USD443 Intranet</h2>
        <p>Link Management</p>
      </div>

      <!-- Burger Menu -->
      <div class="burger" on:click={toggleBurger}>
        <div class="slice" bind:this={tSlice} />
        <div class="slice" bind:this={mSlice} />
        <div class="slice" bind:this={bSlice} />
      </div>

      <!-- Contact Information (hidden on mobile) -->
      <div class="contact-hidden">
        <p>Technology Help Desk: (620) 371-1080</p>
        <p id="webmaster">
          Web Master: Carlos Rodriguez<br /><a href="mailto:rodriguez.carlos@usd443.org?subject=USD443 Intranet"
            >rodriguez.carlos@usd443.org</a
          >
        </p>

        <!-- Page Views -->
        <p class="pageviews" style={pageViews != "" ? "" : "visibility: hidden"}>{pageViews} views</p>
      </div>
    </div>

    <!-- Side Menu (hidden on mobile, contains same links as found in mobile menu) -->
    <div class="hidden-menu">
      <ul class="links-container">
        <li
          class={loadComponent === "Dashboard" ? "link active-menu" : "link"}
          on:click={() => {
            loadComponent = "Dashboard";
          }}
        >
          Dashboard
        </li>
        <li
          class={loadComponent === "Elementary" ? "link active-menu" : "link"}
          on:click={() => {
            loadComponent = "Elementary";
          }}
        >
          Elementary School
        </li>
        <li
          class={loadComponent === "Middle School" ? "link active-menu" : "link"}
          on:click={() => {
            loadComponent = "Middle School";
          }}
        >
          Middle School
        </li>
        <li
          class={loadComponent === "High School" ? "link active-menu" : "link"}
          on:click={() => {
            loadComponent = "High School";
          }}
        >
          High School
        </li>
        <li
          class={loadComponent === "Teachers & Staff" ? "link active-menu" : "link"}
          on:click={() => {
            loadComponent = "Teachers & Staff";
          }}
        >
          Teachers & Staff
        </li>
      </ul>
    </div>

    <!-- Component Container -->
    <div class="main-content-container">
      {#if loadComponent === "Dashboard"}
        <Dashboard {loadComponent} />
      {:else if loadComponent === "Elementary"}
        <Elementary {loadComponent} />
      {:else if loadComponent === "Middle School"}
        <Middle {loadComponent} />
      {:else if loadComponent === "High School"}
        <High {loadComponent} />
      {:else if loadComponent === "Teachers & Staff"}
        <Staff {loadComponent} />
      {/if}
    </div>
  </main>
</div>

<!-- Primary Wrapper -->
<style>
  /* Primary Wrapper */
  .wrapper {
    width: 100%;
    height: 100%;
    position: relative;
    overflow-x: hidden;
  }

  /* Mobile Menu */
  aside {
    position: absolute;
    z-index: 1000;
    background-color: var(--clr-side-bg);
    width: 100%;
    height: 100%;
    color: var(--clr-bg);
    top: 0;
    right: -100%;
    transition: all 0.5s cubic-bezier(0.64, 0.01, 0.17, 0.99);
  }
  .aside-wrapper {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  /* Hidden Menu (only visible on iPads, Laptop, Desktop) */
  .hidden-menu {
    display: none;
  }

  /* Links Container (Applies to Mobile Menu and Hidden Menu) */
  .links-container {
    text-align: center;
    -webkit-touch-callout: none;
    -webkit-user-select: none;
    -khtml-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
  }

  /* Link Styling (Applies to Mobile Menu and Hidden Menu) */
  .link {
    margin: 25px;
    padding: 10px;
    cursor: pointer;
    font-size: 1.2rem;
    opacity: 0.8;
    transition: all 0.3s ease;
    color: var(--clr-light-blue);
  }
  .link:hover {
    color: var(--clr-ultra-light-blue);
    opacity: 1;
  }

  /* Active Link */
  .active-menu {
    opacity: 1;
    color: var(--clr-ultra-light-blue);
  }

  /* Title Styling */
  .main-title-container {
    padding: 30px 25px;
    background-color: var(--clr-side-bg);
    color: var(--clr-bg);
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  /* Main Content Component Container */
  .main-content-container {
    position: relative;
  }
  .titles h2 {
    font-size: clamp(1.5rem, calc(1.5rem + 1vw), 2.5rem);
  }
  .titles p {
    font-weight: 700;
    color: var(--clr-light-blue);
    font-size: clamp(1rem, calc(1rem + 1vw), 1.4rem);
  }

  /* Burger */
  .burger {
    width: 30px;
    cursor: pointer;
    z-index: 1200;
  }
  .slice {
    width: 100%;
    background-color: var(--clr-bg);
    border-radius: 5px;
    margin: 6px 0;
    height: 2px;
    transition: all 0.5s ease;
  }

  /* Page View */
  .pageviews {
    color: var(--clr-light-blue);
    margin-top: 10px;
    font-size: 0.8rem;
    animation: fadeIn 1s 0.5s ease backwards;
    letter-spacing: 0.7px;
  }

  /* Contact */
  .contact {
    margin-top: 90px;
    font-size: 0.9rem;
    text-align: center;
    color: var(--clr-light-blue);
  }
  .contact p:first-of-type {
    font-size: 1rem;
  }
  .contact a {
    margin-top: 5px;
    text-decoration: underline;
  }

  /* Contact Hidden (only visible on iPad, Laptop, Desktop) */
  .contact-hidden {
    display: none;
  }
  .contact-hidden p:first-of-type {
    color: var(--clr-light-blue);
    font-weight: bold;
    margin-bottom: 5px;
  }

  /* Main Wrapper */
  .main-wrapper {
    width: 100%;
    height: 100%;
    display: grid;
    grid-template-rows: auto 1fr;
  }

  /**** Media Queries (Global) ****/
  /* iPads Landscape Orientation */
  @media only screen and (min-width: 1024px) {
    aside,
    .burger {
      display: none;
    }
    .main-wrapper {
      grid-template-rows: auto auto 1fr;
    }
    .hidden-menu {
      display: initial;
      background-color: var(--clr-side-bg);
      color: var(--clr-bg);
      margin-bottom: 15px;
    }
    .links-container {
      display: flex;
      justify-content: space-evenly;
    }
    .contact-hidden {
      display: initial;
      padding: 0 20px;
      text-align: right;
    }
    .titles {
      padding: 0 20px;
    }
  }

  /* Student Laptops */
  @media only screen and (min-width: 1280px) {
    .main-wrapper {
      display: grid;
      grid-template-columns: auto 1fr;
      grid-template-rows: auto repeat(3, 1fr);
    }
    .main-title-container {
      grid-area: 1/1/2/3;
      padding: 40px 25px;
    }
    .link {
      text-align: left;
      margin: 20px 0;
    }
    .hidden-menu {
      grid-area: 2/1/6/2;
      margin-bottom: 0;
      display: flex;
      align-items: center;
      padding: 0 50px;
      overflow-y: auto;
    }
    .main-content-container {
      grid-area: 2/2/6/3;
      padding: 20px;
    }
    .links-container {
      flex-direction: column;
    }

    /* Change Component Wrapper */
    :global(.component-wrapper) {
      width: 500px;
      max-height: 100%;
      overflow-y: auto;
      overflow-x: hidden;
    }
    :global(.component-title h4) {
      margin-bottom: 0;
    }
    :global(.component-links-container .link) {
      margin: 10px;
    }
    :global(.component-links-container .link a) {
      padding: 15px;
    }
  }
  /* Large Desktop Screen */
  @media only screen and (min-width: 1920px) {
    .link {
      font-size: 1.6rem;
    }
    :global(.component-title h4) {
      margin-bottom: 35px;
    }
    :global(.component-wrapper) {
      width: 650px;
    }
    :global(.component-links-container .link) {
      margin: 15px;
    }
    :global(.component-links-container .link a) {
      padding: 15px;
    }
  }

  /* Special Case */
  @media only screen and (max-height: 540px) and (min-width: 1280px) {
    .link {
      margin: 4px;
    }
  }
</style>
