<script>
  export let loadComponent;

  // Create variables
  let expandToggle = false;
  let expandToggle2 = false;
  let expandLink;
  let expandLink2;
  let expandText = "+";
  let expandText2 = "+";

  // Expand the first link
  const expandMenu = () => {
    if (expandToggle) {
      expandText = "+";
      expandToggle = false;
      expandLink.style = "background-color: #fff color:; #357ef2";
    } else {
      expandText = "x";
      expandToggle = true;
      expandLink.style = "background-color: #357ef2; color: #fff";
    }
  };

  // Expand the second link
  const expandMenu2 = () => {
    if (expandToggle2) {
      expandText2 = "+";
      expandToggle2 = false;
      expandLink2.style = "background-color: #fff color:; #357ef2";
    } else {
      expandText2 = "x";
      expandToggle2 = true;
      expandLink2.style = "background-color: #357ef2; color: #fff";
    }
  };
</script>

<div class="component-wrapper">
  <div class="component-title">
    <h4>{loadComponent}</h4>
  </div>
  <div class="component-body">
    <ul class="component-links-container">
      <li class="link">
        <a href="fmp://assessment.usd443.org/FMMain" target="_blank" rel="noreferrer">FileMaker Main Menu</a>
      </li>
      <li class="link">
        <a
          href="https://webmail.usd443.org/owa/auth/logon.aspx?replaceCurrent=1&url=https://webmail.usd443.org/owa/"
          target="_blank"
          rel="noreferrer">District Email</a
        >
      </li>
      <li class="link">
        <a
          href="https://accounts.google.com/ServiceLogin/signinchooser?service=CPanel&passive=1209600&cpbps=1&continue=https%3A%2F%2Fadmin.google.com%2F443mail.org%2FDashboard&followup=https%3A%2F%2Fadmin.google.com%2F443mail.org%2FDashboard&skipvpage=true&flowName=GlifWebSignIn&flowEntry=ServiceLogin"
          target="_blank"
          rel="noreferrer">Google Email</a
        >
      </li>
      <li class="link">
        <a href="fmp://Sub:@10.0.0.29/demons" target="_blank" rel="noreferrer">Pass System Sub Link</a>
      </li>

      <!-- Expand Link 1 -->
      <li
        class="link expand-link"
        bind:this={expandLink}
        on:click={() => {
          expandMenu();
        }}
      >
        <div class="title-wrapper">
          <p>Savvas Login</p>
          <span class="expand-btn">{expandText}</span>
        </div>
        {#if expandToggle}
          <a
            href="https://sso.rumba.pk12ls.com/sso/login?profile=eb&service=https://cat.easybridge.pk12ls.com/ca/dashboard.htm&EBTenant=DCUSD-KS"
            target="_blank"
            rel="noreferrer">Teachers</a
          >
          <a
            href="https://sso.rumba.pk12ls.com/sso/login?profile=eb&service=https://cat.easybridge.pk12ls.com/ca/dashboard.htm&additionalAttributes=Domains"
            target="_blank"
            rel="noreferrer">Administrators</a
          >
        {/if}
      </li>

      <li class="link">
        <a href="https://auth.fastbridge.org/login.do" target="_blank" rel="noreferrer">Fast Bridge</a>
      </li>
      <li class="link">
        <a
          href="https://skyward.iscorp.com/scripts/wsisa.dll/WService=wsedudodgecityks/seplog01.w"
          target="_blank"
          rel="noreferrer">Skyward</a
        >
      </li>

      <!-- Expand Link 2 -->
      <li
        class="link expand-link"
        bind:this={expandLink2}
        on:click={() => {
          expandMenu2();
        }}
      >
        <div class="title-wrapper">
          <p>KSDE/CETE Information</p>
          <span class="expand-btn">{expandText2}</span>
        </div>
        {#if expandToggle2}
          <a href="https://apps.ksde.org/authentication/login.aspx" target="_blank" rel="noreferrer">KSDE Online</a>
          <a href="https://www.ksde.org/" target="_blank" rel="noreferrer">KSDE</a>
          <a href="https://ksreportcard.ksde.org/" target="_blank" rel="noreferrer">Kansas Building Report Card</a>
          <a href="https://datacentral.ksde.org/" target="_blank" rel="noreferrer">Kansas Data Central</a>
          <a href="https://educator.kiteaai.org/AART/logIn.htm" target="_blank" rel="noreferrer">KITE Educator Portal</a
          >
          <a href="https://www.ksassessments.org/" target="_blank" rel="noreferrer">KAP - Kansas Assessment Program</a>
          <a
            href="https://www.ksde.org/Portals/0/CSAS/CSAS%20Home/Assessments/2020-2021%20Kansas%20Assessment%20Program%20Overview.pdf?ver=2020-10-26-094836-250"
            target="_blank"
            rel="noreferrer">2020 - 2021 KAP Overview</a
          >
          <a href="https://dynamiclearningmaps.org/kansas" target="_blank" rel="noreferrer"
            >Dynamic Learning MAPS - Kansas</a
          >
          <a href="https://training.dynamiclearningmaps.org/login/index.php" target="_blank" rel="noreferrer"
            >MOODLE Login</a
          >
        {/if}
      </li>

      <li class="link">
        <a href="http://www.usd443.org/238579_2" target="_blank" rel="noreferrer">Technology Department</a>
      </li>
      <li class="link">
        <a href="https://tc8.treeringws.com/etimeclock/ClockLogin.aspx?c=154" target="_blank" rel="noreferrer"
          >Time Online</a
        >
      </li>
      <li class="link">
        <a
          href="https://tc8.treeringws.com/timecentre8/Login/Login.aspx?ReturnUrl=/timecentre8/Default.aspx"
          target="_blank"
          rel="noreferrer">Time Centre</a
        >
      </li>
      <li class="link">
        <a href="https://usd443.org/295008_2" target="_blank" rel="noreferrer">Employee Assistance Programs</a>
      </li>
      <li class="link">
        <a href="https://www.skacd.com/" target="_blank" rel="noreferrer">SKACD</a>
      </li>
      <li class="link">
        <a href="https://skacd.keystonelearning.org/" target="_blank" rel="noreferrer">WebKIDSS</a>
      </li>
      <li class="link">
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
  /* Styling Links that expand */
  .expand-link {
    color: var(--clr-dark-blue);
  }
  .expand-link p {
    padding: 15px;
  }
  .expand-link a {
    color: var(--clr-dark-blue);
    padding: 15px;
    display: block;
    text-decoration: none;
    background-color: var(--clr-bg);
    border-radius: 5px;
    margin: 15px;
  }
  .expand-btn {
    margin-right: 15px;
    background-color: var(--clr-dark-blue);
    color: var(--clr-bg);
    width: 30px;
    height: 30px;
    border-radius: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: 700;
  }

  /* Expanding link title and button container */
  .title-wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
