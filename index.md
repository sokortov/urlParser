
<html>
<head>
<title>
Hello there!
</title>

<style type="text/css">
 h1 {
     font-size: 2em;
     background-color: #fff;
     padding: 50px;
     max-width: 100%;
 }

html {
    font-family: sans-serif;
    -ms-text-size-adjust: 100%;
    -webkit-text-size-adjust: 100%;
    max-width: 100%;
}
body {
    max-width: 100%;
    word-wrap: break-word;
}
button {
    width: 200px;
    height: 50px;
    font-size: 1em;
}
p {
font-size: 2em;
}
</style>
</head>
<body bgcolor="#fff">
<h1 id="title">
</h1>

<h1 id="localStorageTitle">
</h1>

 <h1>Local Storage test value
</h1>
<p><button onclick="putTestValueToLocalStorage()">Put</button></p>
<p id="putState"></p>
 
<p><button onclick="getTestValueFromLocalStorage()">Get</button></p>
<p id="localStorageValue"></p>

<p><button onclick="deleteTestValueToLocalStorage()">Delete</button></p>
 <p id="deleteState"></p>
 
 <h1><a href="https://sokortov.github.io/urlParser?new=true">LINK</a></h1>

 <h1><a href="hyprr://">hyprr</a></h1>
 <h1><a href="hyprr://discover/posts">discover/posts</a></h1>
 <h1><a href="hyprr://hypetv/">hypetv/</a></h1>
 <h1><a href="hyprr://messaging?channel=bfca80d5-65cb-4121-93d8-208bc5c1d0ad">messaging?channel=bfca80d5-65cb-4121-93d8-208bc5c1d0ad</a></h1>
 <h1><a href="hyprr://profile/ivan_100">profile/ivan_100</a></h1>
 <h1><a href="hyprr://discover/hypetv">discover/hypetv</a></h1>
 <h1><a href="hyprr://discover/nft">discover/nft</a></h1>
 <h1><a href="dapp://www.google.com/">metamask</a></h1>
 <h1><a href="hyprr://">hyprr</a></h1>
 <h1><a href="hyprr://">hyprr</a></h1>
 <h1><a href="hyprr://">hyprr</a></h1>
 <h1><a href="googlegmail://">GMAIL</a></h1>

<script>
function parseURLParams(url) {
    var queryStart = url.indexOf("?") + 1,
        queryEnd   = url.indexOf("#") + 1 || url.length + 1,
        query = url.slice(queryStart, queryEnd - 1),
        pairs = query.replace(/\+/g, " ").split("&"),
        parms = {}, i, n, v, nv;

    if (query === url || query === "") return;

    for (i = 0; i < pairs.length; i++) {
        nv = pairs[i].split("=", 2);
        n = decodeURIComponent(nv[0]);
        v = decodeURIComponent(nv[1]);

        if (!parms.hasOwnProperty(n)) parms[n] = [];
        parms[n].push(nv.length === 2 ? v : null);
    }
    return parms;
}

document.getElementById("title").innerHTML = JSON.stringify(parseURLParams(location.href));


function lsLocalStorageEnabled(){
    var test = 'test1';
    try {
        localStorage.setItem(test, test);
        localStorage.removeItem(test);
        return "enabled";
    } catch(e) {
        return "disabled";
    }
}

document.getElementById("localStorageTitle").innerHTML = ("Local storage " + lsLocalStorageEnabled());
                                 
function getTestValueFromLocalStorage() {
var val = localStorage.getItem('test');
if (val) {
document.getElementById("localStorageValue").innerHTML = val;
} else {
document.getElementById("localStorageValue").innerHTML = "error";
}
};

function putTestValueToLocalStorage(){
var test = 'test';
localStorage.setItem(test, test);
document.getElementById("putState").innerHTML = "done";
};

function deleteTestValueToLocalStorage(){
var test = 'test';
localStorage.removeItem(test, test);
document.getElementById("deleteState").innerHTML = "done";
};
</script>

<script
  async
  src="https://dev.i10x.ai/widget.js"
  data-src="https://dev.i10x.ai/embed/chatbot/1f0832f4-02bb-64a7-940d-819e05d11d55/widget"
  data-position="top-left"
></script>

</body>
</html>

