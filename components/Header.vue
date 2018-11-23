<template>
	<header>
		<nav>
			<ul>
				<!-- <li><nuxt-link to="/home">Home</nuxt-link></li> -->
				<li><nuxt-link to="/users">Users</nuxt-link></li>
				<li><nuxt-link to="/about">About</nuxt-link></li>	
			</ul>
		</nav>
	</header>
</template>

<style>
header{
		width: 100%;
		height:50px;
		display:flex;
		justify-content: center;
		align-items: center;
		background-color: #333;
	}
ul {
    list-style: none;
	padding: 0;
	margin: 0;
	display: flex;
	justify-content: center;
	align-items: center;
	}
li {
    float: right;
    margin-right: 10px;
}

li a {
    display: flex;
    color: white;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
}

li a:hover:not(.active) {
    background-color: #111;
}

.active {
    background-color: #4CAF50;
}
</style>