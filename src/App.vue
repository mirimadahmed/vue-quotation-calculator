/* eslint-disable max-len */
<template>
  <div id="app">
    <div id="nav">
      <nav class="navbar navbar-expand-lg navbar-light">
        <a class="navbar-brand" href="#">
          <img
            class="img-fluid"
            src="https://i1.wp.com/gogreenpristine.uk/wp-content/uploads/2020/05/Asset-3.png"
          />
        </a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarText"
          aria-controls="navbarText"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse navbar-right" id="navbarText">
          <ul class="navbar-nav navbar-right">
            <li class="nav-item active">
              <a class="nav-link" href="https://gogreenpristine.uk/">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="https://gogreenpristine.uk/about-us/">About Us</a>
            </li>
            <li class="nav-item">
              <a
                class="nav-link"
                href="https://gogreenpristine.uk/residential-services/"
              >Residential Services</a>
            </li>
            <li class="nav-item">
              <a
                class="nav-link"
                href="https://gogreenpristine.uk/commercial-services/"
              >Commercial Services</a>
            </li>
            <li class="nav-item">
              <a
                class="nav-link"
                href="https://gogreenpristine.uk/covid-19-services/"
              >Covid 19 Services</a>
            </li>
            <li class="nav-item">
              <a
                class="nav-link"
                href="https://gogreenpristine.uk/eco-friendly-end-of-tenancy-cleaning/"
              >End of Tenancy Cleaning</a>
            </li>
            <li class="nav-item">
              <a
                class="nav-link"
                href="https://gogreenpristine.uk/property-maintenance/"
              >Property Maintenance</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="https://gogreenpristine.uk/extra-services/">Extra Services</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="https://gogreenpristine.uk/contact-us/">Contact Us</a>
            </li>
          </ul>
        </div>
      </nav>
    </div>
    <router-view />
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#nav {
  padding: 20px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  width: max-content;
}

.nav-item a {
  font-size: 0.9rem;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

@media (min-width: 992px) {
  .navbar-expand-lg .navbar-nav .nav-link {
    padding-right: 0.25rem !important;
    padding-left: 0.25rem !important;
  }
}
</style>
