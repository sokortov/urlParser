
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
</style>
</head>
<body bgcolor="#fff">
<h1 id="title">
</h1>

<h1 id="localStorageTitle">
</h1>
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
    var test = 'test';
    try {
        localStorage.setItem(test, test);
        localStorage.removeItem(test);
        return "enabled";
    } catch(e) {
        return "disabled";
    }
}

document.getElementById("localStorageTitle").innerHTML = ("Local storage " + lsLocalStorageEnabled());
</script>
<a href="https://sokortov.github.io/urlParser?new=true">LINK</a>





</body>
</html>
