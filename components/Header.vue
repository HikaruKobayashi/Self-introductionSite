<template>
  <header class='header-logo-menu menu'>
    <div id='nav-drawer'>
      <input  id="nav-input" type="checkbox" class="nav-unshown"/>
      <label id="nav-open" for="nav-input"><span></span></label>
      <label class="nav-unshown" id="nav-close" for="nav-input"></label>
      <div id="nav-content">
        <p v-scroll-to="'#overview'" to>About</p>
        <p v-scroll-to="'#skill'" to>Skill</p>
        <p v-scroll-to="'#work'" to>Work</p>
        <p v-scroll-to="'#contact'" to>Contact</p>
      </div>
    </div>
  </header>
</template>

<style>
  #nav-drawer {
    position: relative;
    padding: 10px;
    z-index: 9999;
  }
  .nav-unshown {
    display:none;
  }
  #nav-open {
    display: inline-block;
    width: 30px;
    height: 22px;
    vertical-align: middle;
  }
  #nav-open span, #nav-open span:before, #nav-open span:after {
    position: absolute;
    height: 3px;
    width: 25px;
    border-radius: 3px;
    background: rgb(17, 32, 63);
    display: block;
    content: '';
    cursor: pointer;
    z-index: 50;
  }
  #nav-open span:before {
    bottom: -8px;
  }
  #nav-open span:after {
    bottom: -16px;
  }

  #nav-close {
    display: none;
    position: fixed;
    z-index: 99;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: black;
    opacity: 0;
    transition: .3s ease-in-out;
  }

  #nav-content {
    overflow: auto;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 9999;
    width: 90%;
    max-width: 200px;
    height: 100%;
    background: #fff;
    transition: .3s ease-in-out;
    -webkit-transform: translateX(-105%);
    transform: translateX(-105%);
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  #nav-content > p {
    font-size: 20px;
    padding: 10px 60px;
    cursor: pointer;
    border-radius: 50px;
  }
  #nav-content > p:hover {
    color: #f3f3f3;
    background: linear-gradient(rgb(52,62,98), rgb(24,26,41));
  }

  #nav-input:checked ~ #nav-close {
    display: block;
    opacity: .5;
  }

  #nav-input:checked ~ #nav-content {
    -webkit-transform: translateX(0%);
    transform: translateX(0%);
    box-shadow: 6px 0 25px rgba(0,0,0,.15);
  }

  .header-logo-menu{
    display: flex;
    display: -moz-flex;
    display: -o-flex;
    display: -webkit-flex;
    display: -ms-flex;
    flex-direction: row;
    -moz-flex-direction: row;
    -o-flex-direction: row;
    -webkit-flex-direction: row;
    -ms-flex-direction: row;
    position: fixed;
    z-index: 9999;
  }
</style>