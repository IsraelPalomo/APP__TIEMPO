<template>
	<div class="app">
		<main>
			<nav>
				<div class="navegacion">
					<h3>Madrid</h3>
				</div>

				<form>
					<input type="text" placeholder="Buscar Tu Ciudad" />
					<button type="submit">Mira El Tiempo</button>
				</form>
				<hr />
			</nav>

			<h2>LLUVIAS</h2>

			<div class="principal">
				<img src="../assets/nublado.png" alt="" />
				<h1>7ºC</h1>
			</div>
			<div class="mas-info">
				<div class="info">
					<i class="fas fa-wind"> 4k</i>
				</div>
				<div class="info"><i class="far fa-snowflake"> 4k</i></div>
				<div class="info"><i class="fas fa-temperature-high"> 4k</i></div>
				<div class="info"><i class="fas fa-tint"> 4k</i></div>
			</div>
			<hr />
			<div class="calendario">
				<div class="lunes">Lunes</div>

				<div class="martes">Martes</div>
				<div class="miercoles">Miercoles</div>
				<div class="jueves">Jueves</div>
				<div class="viernes">Viernes</div>
				<i class="fas fa-cloud-sun"></i><i class="fas fa-cloud-sun"></i
				><i class="fas fa-cloud-sun"></i><i class="fas fa-cloud-sun"></i
				><i class="fas fa-cloud-sun"></i>
				<!-- <div class="sabado">Sabado</div>
				<div class="domingo">Domingo</div> -->
			</div>
		</main>
	</div>
</template>

<script>
// @ is an alias to /src

export default {
	name: "Home",
	components: {},
};
</script>
<style>
.app {
	padding: 1rem;
}
body {
	margin: 0;
	padding: 0;
	background-image: url(../assets/Fondo-Noche.jpg);
	background-position: center;
	background-size: contain;
	font-family: "Exo 2", sans-serif;
}
nav {
	width: 100%;
	height: 9rem;
	margin-top: 1rem;
	margin-bottom: 5rem;
	/* position: absolute; */
}
main {
	width: 100%;
	height: 100vh;
}
nav h3 {
	text-align: center;
	color: white;
	padding: 0;

	margin-top: 0rem;
}
main h2 {
	font-size: 2.2rem;
	text-align: center;
	color: white;
	margin: 0;
	padding: 3rem 3rem 2rem 3rem;
}

form {
	display: flex;
	justify-content: center;
	flex-wrap: wrap;
}

form input {
	width: 90%;
	margin-bottom: 1rem;
	border: none;
	border-radius: 50px;
	padding: 10px;
	text-align: center;
}
button {
	padding: 0.5rem;
	border-radius: 50px;
	height: 2rem;
	border: none;
	margin-bottom: 2rem;
}
button:hover {
	background-color: rgb(219, 217, 217);
}

.principal {
	margin-top: 3rem;
	display: flex;
	justify-content: space-around;
}
.principal img {
	width: 10rem;
	height: 10rem;
	padding: 1rem;
}
.principal h1 {
	font-size: 5rem;
	padding: 1rem;
	color: #ffffff;
}
.mas-info {
	display: grid;
	grid-template-columns: repeat(2, 1fr);
	grid-template-rows: repeat(2, 1fr);
	margin-top: 3rem;
}
.info {
	height: 5rem;
	text-align: center;
}
i {
	color: #ffffff;
	font-size: 2rem;
}
.calendario {
	display: grid;
	grid-template-columns: repeat(5, 1fr);
	grid-template-rows: repeat(2, 1fr);
	color: white;
	text-align: center;
	justify-content: center;
	margin-top: 3rem;
	padding-bottom: 3rem;
}

.navegacion h3 {
	font-size: 3.5rem;
	text-align: center;
	margin-bottom: 3rem;
}
@media (min-width: 900px) {
	form input {
		width: 95%;
	}
	.principal {
		justify-content: center;
	}
	.principal h1 {
		padding: 2rem;
	}
	.principal img {
		padding: 2rem;
	}
	.calendario {
		grid-template-columns: repeat(5, 18%);
		grid-template-rows: repeat(2, 1fr);
	}
	.mas-info {
		grid-template-columns: repeat(2, 30%);
		grid-template-rows: repeat(2, 30%);
		justify-content: center;
	}
	.info {
		margin-bottom: 2rem;
	}
}
</style>
