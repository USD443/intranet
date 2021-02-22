<script>
  export let loadComponent;
</script>

<div class="component-wrapper">
  <div class="component-title">
    <h4>{loadComponent}</h4>
  </div>
  <div class="component-body">
    <ul class="quicklinks-wrapper">
      <p>Quick Links</p>
      <li class="quicklinks-link">
        <a href="fmp://assessment.usd443.org/FMMain" target="_blank" rel="noreferrer">FileMaker Main Menu</a>
      </li>
      <li class="quicklinks-link">
        <a href="https://www.usd443.org/" target="_blank" rel="noreferrer">USD443 District Website</a>
      </li>
      <li class="quicklinks-link">
        <a
          href="https://webmail.usd443.org/owa/auth/logon.aspx?replaceCurrent=1&url=https://webmail.usd443.org/owa/"
          target="_blank"
          rel="noreferrer">District Email</a
        >
      </li>
      <li class="quicklinks-link">
        <a
          href="https://accounts.google.com/ServiceLogin/signinchooser?service=CPanel&passive=1209600&cpbps=1&continue=https%3A%2F%2Fadmin.google.com%2F443mail.org%2FDashboard&followup=https%3A%2F%2Fadmin.google.com%2F443mail.org%2FDashboard&skipvpage=true&flowName=GlifWebSignIn&flowEntry=ServiceLogin"
          target="_blank"
          rel="noreferrer">Google Email</a
        >
      </li>
      <li class="quicklinks-link">
        <a
          href="https://skyward.iscorp.com/scripts/wsisa.dll/WService=wsedudodgecityks/seplog01.w"
          target="_blank"
          rel="noreferrer">Skyward Login</a
        >
      </li>
      <li class="quicklinks-link">
        <a
          href="https://login.frontlineeducation.com/login?signin=326aa86a385363df9ed31d0853146f9a&clientId=superSuit#/login"
          target="_blank"
          rel="noreferrer">Frontline</a
        >
      </li>
    </ul>
  </div>
</div>

<style>
  /* Quicklinks */
  .quicklinks-wrapper {
    margin-top: 30px;
    box-shadow: 0px 2px 8px rgba(100, 100, 200, 0.2);
    border-radius: 5px;
    overflow: hidden;
    background-color: #fff;
  }
  .quicklinks-wrapper p {
    background-color: var(--clr-dark-blue);
    color: var(--clr-bg);
    padding: 20px;
    font-weight: 700;
    font-size: 1.1rem;
  }
  .quicklinks-link {
    margin: 20px 25px;
    background-color: #fff;
    border: 2px solid #e1e6fd;
    border-radius: 5px;
  }
  .quicklinks-link a {
    color: var(--clr-dark-blue);
    display: block;
    padding: 15px;
  }

  /* Media Queries */
  @media only screen and (min-width: 1280px) {
    .quicklinks-link {
      margin: 10px 15px;
    }
    .quicklinks-link a {
      padding: 10px;
    }
  }
  @media only screen and (min-width: 1920px) {
    .quicklinks-link {
      margin: 20px 25px;
    }
    .quicklinks-link a {
      padding: 15px;
    }
  }
</style>
