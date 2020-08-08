# dark-light-mode
<h2>Simple way to switch between dark and light mode<h2>
see the <a href="https://material.io/design/color/dark-theme.html">demo</a>
 
For more colors, backgrounds and inspiration
 <a href="https://material.io/design/color/dark-theme.html">Visit this  page</a>

<h2>how to use<h2>
<h4>in javascript file <h4>
     // darkMode

    let darkMode = localStorage.getItem('darkMode');
    let sun = document.querySelector(".sun"); // sun icon Selector
    let moon = document.querySelector(".moon"); // moon icon Selector

    // toggler
    const togglerMode = document.querySelector(".theme-toggle") // toggler Selector

    // function for enable Dark Mode 
    const enableDarkMode = () => {
        document.body.classList.add('darkmode')
        localStorage.setItem('darkMode', 'enabled')
 
        sun.style.display = "inline";
        moon.style.display = "none";
        
    }

    // function for disable Dark Mode
    const disableDarkMode = () => {
        document.body.classList.remove('darkmode')
        localStorage.setItem('darkMode', null)

        moon.style.display = "inline";
        sun.style.display = "none";

    }

    // check if darkmode is enabled
    if (darkMode == "enabled") {
        enableDarkMode()
        sun.style.display = "inline";
        moon.style.display = "none";
    } else {
        moon.style.display = "inline";
        sun.style.display = "none";
    }

    // toggler on click
    togglerMode.addEventListener('click', () => {
        darkMode = localStorage.getItem('darkMode')
        if (darkMode !== "enabled") {
            enableDarkMode()
        } else {
            disableDarkMode()
        }
    });






