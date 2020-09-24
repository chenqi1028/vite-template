<template>
<div id="nav">
	<router-link to="/">Home</router-link> |
	<router-link to="/about">About</router-link>
</div>
<router-view />
</template>

<style lang="scss">
#app {
	text-align: center;
	overflow: hidden;
}

.nav {
	color: #000;
	text-decoraction: none;
}
</style>
