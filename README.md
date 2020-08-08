# dark-light-mode
<h2>Simple way to switch between dark and light mode<h2>
see the <a href="https://material.io/design/color/dark-theme.html">demo</a>
 
For more colors, backgrounds and inspiration
 <a href="https://material.io/design/color/dark-theme.html">Visit this  page</a>

how to use
<h4>1. in javascript file <h4>
 
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
    
<h4>2. in css file <h4>
 
     :root {
        --main-bg : #fff; /* main background color in light mode*/
        --secondary-bg : #eee; /* secondary background color in light mode*/
        --color : #3a3b45; /* main color in light mode*/
    }
    .darkmode {
        --main-bg : #303030; /* main background color in dark mode*/
        --secondary-bg : #424242; /* secondary background color in dark mode*/
        --color : #f8f9fc; /* main color in dark mode*/
    }

    .main-bg {
        background-color: var(--main-bg);
    }

    .secondary-bg {
        background-color: var(--secondary-bg);
        text-align: center;
    }

    .color {
        color: var(--color);
    }
    
<h4>3. add toggler Selector and icons then add the previous classes in html elements <h4>        
