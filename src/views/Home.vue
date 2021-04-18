<template>
	<div class="app">
		<main>
			<nav>
				<div class="navegacion">
					<h3>{{ nombre }}</h3>
				</div>

				<form @submit.prevent="callTiempo()">
					<input type="text" placeholder="Buscar Tu Ciudad" v-model="nombre" />
					<button type="submit">Mira El Tiempo</button>
				</form>
				<hr />
			</nav>

			<h2>{{ pronostico.toUpperCase() }}</h2>

			<div class="principal">
				<img v-if="imagen.id === 800" src="..\assets\png\023-sun.png" alt="logo" />
				<img v-if="imagen.id === 201" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 202" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 210" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 211" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 212" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 221" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 230" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 231" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 232" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 200" src="..\assets\png\028-storm-1.png" alt="logo" />

				<img v-if="imagen.id === 300" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 301" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 302" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 310" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 311" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 312" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 313" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 314" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 321" src="..\assets\png\022-rain.png" alt="logo" />

				<img v-if="imagen.id === 500" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 501" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 502" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 503" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 504" src="..\assets\png\028-storm-1.png" alt="logo" />

				<img v-if="imagen.id === 511" src="..\assets\png\037-thermometer.png" alt="logo" />

				<img v-if="imagen.id === 520" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 521" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 522" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 531" src="..\assets\png\022-rain.png" alt="logo" />

				<img v-if="imagen.id === 600" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 601" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 602" src="..\assets\png\029-hail.png" alt="logo" />
				ç<img v-if="imagen.id === 611" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 612" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 613" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 615" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 616" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 620" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 621" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 622" src="..\assets\png\029-hail.png" alt="logo" />

				<img v-if="imagen.id === 701" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 711" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 721" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 731" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 741" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 751" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 761" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 762" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 771" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 781" src="..\assets\png\021-fog.png" alt="logo" />

				<img v-if="imagen.id === 801" src="..\assets\png\050-cloudy-1.png" alt="logo" />
				<img v-if="imagen.id === 802" src="..\assets\png\050-cloudy-1.png" alt="logo" />
				<img v-if="imagen.id === 803" src="..\assets\png\050-cloudy-1.png" alt="logo" />
				<img v-if="imagen.id === 804" src="..\assets\png\050-cloudy-1.png" alt="logo" />

				<h1>{{ temperatura }}ºC</h1>
			</div>
			<div class="mas-info">
				<div class="info">
					<i class="fas fa-wind"> {{ " " + viento }} KM/H</i>
				</div>
				<div class="info">
					<i class="far fa-snowflake"> {{ " " + temperatura_min }}ºC</i>
				</div>
				<div class="info">
					<i class="fas fa-temperature-high">{{ " " + temperatura_max }}ºC</i>
				</div>
				<div class="info">
					<i class="fas fa-tint">{{ " " + lluvia }} %</i>
				</div>
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
	data() {
		return {
			nombre: "Madrid",
			pronostico: "",
			temperatura: "",
			viento: "",
			temperatura_min: "",
			temperatura_max: "",
			lluvia: "",
			imagen: "",
		};
	},
	components: {},
	methods: {
		async callTiempo() {
			const res = await fetch(
				`http://api.openweathermap.org/data/2.5/weather?q=${this.nombre}&appid=6cd01d16690d7cf5421a4f285c854c5d&lang=es`
			);
			const data = await res.json();
			this.nombre = data.name;
			this.pronostico = data.weather[0].description;
			this.temperatura = Math.floor(data.main.temp - 273.15);
			this.viento = data.wind.speed;
			this.temperatura_min = Math.floor(data.main.temp_min - 273.15);
			this.temperatura_max = Math.floor(data.main.temp_max - 273.15);
			this.lluvia = data.main.humidity;
			this.imagen = data.weather[0];
			console.log(data);
		},
		async callDias() {
			const res = await fetch(
				"http://api.openweathermap.org/data/2.5/forecast?q=madrid&appid=4f99f2cab90608915fdecfc3d2399794&lang=es"
			);
			const data = await res.json();
			console.log(data);
		},
	},
	created() {
		this.callTiempo();
		this.callDias();
	},
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
	padding-bottom: 5rem;
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
