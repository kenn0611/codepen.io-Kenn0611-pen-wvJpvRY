<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="script.js"></script>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <header>
        <div id='tab_buttons'>
            <button class='tab_button' id='home_button'>Home</button>
            <button class='tab_button' id='about_button'>About</button>
            <button class='tab_button' id='interact_button'>Interact</button>
        </div>
    </header>

    <div id="home_tab" class="tab">
        <h1>Home</h1>
    </div>

    <div id="about_tab" class="tab">
        <h1>About</h1>
        <h3>Kenson</h3>
    </div>

    <div id="interact_tab" class="tab">
        <h1>Interact</h1>
        <button id='counter_button'>Increase Counter</button> <br>
        <label id='counter_label'>Counter: 0</label>
    </div>


</body>

</html>

header {
    display: block;
    background-color: blue;
    height: 40px;
    width: auto;
    border-radius: 2px;
    align-items: center;
}

#tab_buttons {
    padding-top: 10px;
    text-align: center;
}

.tab {
    display: none;

}

#home_tab {
    display: block;
}

counter = 0;


var tabs;

window.addEventListener('load', () => {
    tabs = document.getElementsByClassName('tab');

    document.getElementById('home_button').addEventListener('click', () => {
        switch_tab('home_tab');
    })

    document.getElementById('about_button').addEventListener('click', () => {
        switch_tab('about_tab');
    })

    document.getElementById('interact_button').addEventListener('click', () => {
        switch_tab('interact_tab');
    })

    document.getElementById('counter_button').addEventListener('click', (e) => {
        ++counter;
        document.getElementById('counter_label').innerHTML = 'Counter: ' + counter;
    })
});


function hide_all_tabs() {
    for (let i = 0; i < tabs.length; ++i) {
        tabs.item(i).style.display = 'none';
    };
}

function switch_tab(tab_name) {
    hide_all_tabs();
    document.getElementById(tab_name).style.display = 'block';
}
