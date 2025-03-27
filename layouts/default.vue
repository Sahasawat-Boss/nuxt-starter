<template>
    <div>
        <nav>
            <ul>
                <li><a class="active" href="/">Home</a></li>
                <li><a href="/about">About</a></li>
                <li><a href="/attraction">Attraction</a></li>
                <li><a href="/attraction/info">(Attraction Info)</a></li>
            </ul>
        </nav>
        <slot /> <!-- Page Content-->
    </div>
</template>

<style>
body {
    margin: 0px;
}

nav > ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    overflow: hidden;
    background-color: #333;
}

nav > ul > li {
    float: left;
}

nav > ul > li > a {
    display: block;
    color: white;
    text-align: center;
    padding: 10px 16px;
    text-decoration: none;
}

nav > ul > li > a:hover {
    background-color: #7e7e7e;
}
</style>