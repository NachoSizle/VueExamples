<template>
  <div class="navBarContainer">
    <nav class="navBar">
      <a href="/index.html"><img class="headerLogo" src="/src/logos/circle.svg" alt="Circle Logo" /></a>
      <ul>
        <li><a href="/index.html"><span>Home</span></a></li>
        <li id="liCenter">
          <a href="/project-page/index.html">Projects</a>
        </li>
        <li><a href="/index.html#servicesAnchor">Services</a></li>
      </ul>
      <a href="/contact-page/index.html"><button class="blueButton">Contact Us</button></a>
    </nav>
  </div>
</template>

<script>
export default {

}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap');

body {
    background-color: #F2F4FC;
}
* {
    font-family: Roboto;
    margin: 0px;
}

/* Fonts and styles */
h1 {
    font-size: 60px;
    font-weight: bold;
}
h2 {
    font-size: 50px;
    font-weight: bold;
}
h3 {
    font-size: 40px;
    font-weight: bold;
}
h4 {
    font-size: 24px;
    font-weight: bold;
}
p {
    font-size: 20px;
}
a {
    text-decoration: none;
}
.blueButton {
    background-color: #072ACB;
    padding: 15px 30px;
    font-size: 17px;
    color: white;
    border: none;
}
/* header */
.navBarContainer {
    padding:  70px 170px 0px 170px;
    margin-bottom: 100px
}
.navBar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    align-content: flex-end;
}
.navBar .headerLogo {
    height: 20px;
}
.navBar ul {
    list-style: none;
    display: flex;
    justify-content: center;
}
.navBar #liCenter {
    margin: 0px 60px 0px 60px;
}
.navBar li {
    font-size: 17px;
}
.navBarContainer span {
    color: #072ac8;
}

/* Form */
.formContainer {
    padding: 20px 170px 140px 170px;
    color: #6B708D;
}
h1 {
    margin-bottom: 80px;
    color: black;
}
.form {
    display: flex;
    width: 100%;
}
.form label {
    font-size: 20px;
}
.formContainer input {
    width: 100%;
    background-color: rgb(107, 112, 141, 0.1);
    border: none;
    height: 70px;
    font-size: 17px;

}
.formContainer textarea {
    width: 100%;
    background-color: rgb(107, 112, 141, 0.1);
    border: none;
    font-size: 17px;
    color: #6B708D;
}
.submitButton {
    width: 100%;
    margin-top: 40px;
    background-color: #072ACB;
    color: white;
    padding: 30px 0px;
    font-size: 17px;
}
.centerInput {
    display: flex;
    margin: 40px 0px;
    justify-content: space-between;
}
.centerInput div {
    width: 48%;
}

/* footer */
footer {
    padding: 30px 170px 100px 170px;
    display: flex;
    justify-content: space-between;
}
.footAddress {
    height: 112px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: start;
}
.footAddress img {
    height: 30px;
    margin-bottom: 40px;
}
.linkContainer{
    width: 50%;
    height: 110px;
    display: flex;
    justify-content: space-between;
}
.footLinks {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

@media only screen and (max-width: 1200px) {
}

@media only screen and (max-width: 800px){
    body {
        font-size: 16px;
    }
    .blueButton {
        background-color: #072ACB;
        padding: 5px 10px;
        font-size: 15px;
        color: white;
        border: none;
        border-radius: 25px;
    }
    /* header */
    .navBarContainer {
        height: 55px;
        margin: 0px;
        padding: 0px;
    }
    .navBar {
        height: 100%;
        display: flex;
        padding: 0px 7%;
    }
    .navBar ul {
        width: 50%;
        margin: 0;
        padding: 0;
        justify-content: space-between;
    }
    .navBar li {
        font-size: 15px;
    }
    .navBar #liCenter {
        margin: 0px;
    }
    /*form*/
    h1 {
        font-size: 45px;
        margin-bottom: 20px;
    }
    .formContainer {
        padding-left: 7%;
        padding-right: 7%;
        padding-bottom: 50px;
    }
    .formContainer input {
        height: 50px;
        border-radius: 15px;
    }
    .formContainer textarea{
        border-radius: 15px;
    }
    .submitButton {
        height: 50px;
        padding: 0;
    }
    /* footer */
    footer {
        margin: 0;
        height: fit-content;
        padding: 15% 5%;
        margin-bottom: 50px;
    }
    .footAddress {
        margin-top: 5px;
    }
    .linkContainer {
        margin-left: 5%;
    }
    .linkContainer a {
        margin: 5px 0px 5px 0px; 
    }
}

@media only screen and (max-width: 600px) {
    body {
        font-size: 14px;
    }
    .blueButton {
        background-color: #072ACB;
        padding: 5px 10px;
        font-size: 13px;
        color: white;
        border: none;
        border-radius: 25px;
    }
    /* header */
    .navBarContainer {
        height: 55px;
        margin: 0px;
        padding: 0px;
    }
    .navBar {
        height: 100%;
        display: flex;
        padding: 0px 2%;
    }
    .navBar ul {
        width: 50%;
        margin: 0;
        padding: 0;
        justify-content: space-between;
    }
    .navBar li {
        font-size: 13px;
    }
    .navBar #liCenter {
        margin: 0px;
    }
    /*form*/
    h1 {
        font-size: 40px;
        margin-bottom: 20px;
    }
    .formContainer {
        padding-left: 7%;
        padding-right: 7%;
        padding-bottom: 50px;
    }
    .formContainer input {
        height: 40px;
        border-radius: 15px;
    }
    .formContainer textarea{
        border-radius: 15px;
    }
    .submitButton {
        height: 50px;
        padding: 0;
    }
    /* footer */
    footer {
        margin: 0;
        height: fit-content;
        padding: 15% 5%;
        margin-bottom: 50px;
    }
    .footAddress {
        margin-top: 5px;
    }
    .linkContainer {
        flex-direction: column;
        margin-left: 5%;
    }
    .linkContainer a {
        margin: 5px 0px; 
    }
    
}
</style>