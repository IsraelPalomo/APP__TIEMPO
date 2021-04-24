<template>
	<div class="app">
		<main>
			<nav>
				<div class="navegacion">
					<h3 v-if="error <= 0">{{ nombre }}</h3>
					<h4 v-else-if="error > 0" class="error  animate__animated  animate__shakeX">
						Tu ciudad esta mal escrita
					</h4>
				</div>

				<form @submit.prevent="callTiempo(), callDias()">
					<input type="text" placeholder="Buscar Tu Ciudad" v-model="nombre" />
					<button type="submit">Mira El Tiempo</button>
				</form>
				<hr />
			</nav>

			<h2>{{ pronostico.toUpperCase() }}</h2>

			<div class="principal">
				<img v-if="imagen.id === 800" src="..\assets\png\023-sun.png" alt="logo" />
				<img v-if="imagen.id === 201" src="..\assets\png\034-raining-1.png" alt="logo" />
				<img v-if="imagen.id === 202" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 210" src="..\assets\png\034-raining-1.png" alt="logo" />
				<img v-if="imagen.id === 211" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 212" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 221" src="..\assets\png\034-raining-1.png" alt="logo" />
				<img v-if="imagen.id === 230" src="..\assets\png\034-raining-1.png" alt="logo" />
				<img v-if="imagen.id === 231" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 232" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 200" src="..\assets\png\034-raining-1.png" alt="logo" />

				<img v-if="imagen.id === 300" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 301" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 302" src="..\assets\png\043-raining-2.png" alt="logo" />
				<img v-if="imagen.id === 310" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 311" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 312" src="..\assets\png\043-raining-2.png" alt="logo" />
				<img v-if="imagen.id === 313" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 314" src="..\assets\png\043-raining-2.png" alt="logo" />
				<img v-if="imagen.id === 321" src="..\assets\png\022-rain.png" alt="logo" />

				<img v-if="imagen.id === 500" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 501" src="..\assets\png\028-storm-1.png" alt="logo" />
				<img v-if="imagen.id === 502" src="..\assets\png\043-raining-2.png" alt="logo" />
				<img v-if="imagen.id === 503" src="..\assets\png\043-raining-2.png" alt="logo" />
				<img v-if="imagen.id === 504" src="..\assets\png\043-raining-2.png" alt="logo" />

				<img v-if="imagen.id === 511" src="..\assets\png\037-thermometer.png" alt="logo" />

				<img v-if="imagen.id === 520" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 521" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 522" src="..\assets\png\022-rain.png" alt="logo" />
				<img v-if="imagen.id === 531" src="..\assets\png\022-rain.png" alt="logo" />

				<img v-if="imagen.id === 600" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 601" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 602" src="..\assets\png\048-snowy-1.png" alt="logo" />
				<img v-if="imagen.id === 611" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 612" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 613" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 615" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 616" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 620" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 621" src="..\assets\png\029-hail.png" alt="logo" />
				<img v-if="imagen.id === 622" src="..\assets\png\048-snowy-1.png" alt="logo" />

				<img v-if="imagen.id === 701" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 711" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 721" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 731" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 741" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 751" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 761" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 762" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 771" src="..\assets\png\021-fog.png" alt="logo" />
				<img v-if="imagen.id === 781" src="..\assets\png\008-tornado.png" alt="logo" />

				<img v-if="imagen.id === 801" src="..\assets\png\050-cloudy-1.png" alt="logo" />
				<img v-if="imagen.id === 802" src="..\assets\png\050-cloudy-1.png" alt="logo" />
				<img v-if="imagen.id === 803" src="..\assets\png\001-cloud.png" alt="logo" />
				<img v-if="imagen.id === 804" src="..\assets\png\001-cloud.png" alt="logo" />

				<h1>{{ temperatura }}ºC</h1>
			</div>
			<div class="mas-info">
				<div class="info">
					<i class="fas fa-wind"> {{ " " + viento }} km/h</i>
				</div>
				<div class="info">
					<i class="fas fa-temperature-low"> {{ " " + temperatura_min }}ºC</i>
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
				<div class="lunes" v-if="DiaActual === 1">Lun</div>
				<div class="martes" v-else-if="DiaActual === 2">Mar</div>
				<div class="miercoles" v-else-if="DiaActual === 3">Mie</div>
				<div class="jueves" v-else-if="DiaActual === 4">Jue</div>
				<div class="viernes" v-else-if="DiaActual === 5">Vie</div>
				<div class="jueves" v-else-if="DiaActual === 6">Sab</div>
				<div class="viernes" v-else-if="DiaActual === 7">Dom</div>
				<div class="viernes" v-else-if="DiaActual === 8">Lun</div>
				<div class="viernes" v-else-if="DiaActual === 9">Mar</div>
				<div class="viernes" v-else-if="DiaActual === 10">Mie</div>
				<div class="viernes" v-else-if="DiaActual === 11">Jue</div>
				<div class="viernes" v-else-if="DiaActual === 12">Vie</div>
				<div class="viernes" v-else-if="DiaActual === 13">Sab</div>
				<div class="viernes" v-else-if="DiaActual === 14">Dom</div>

				<div class="lunes" v-if="DiaActual1 === 1">Lun</div>
				<div class="martes" v-else-if="DiaActual1 === 2">Mar</div>
				<div class="miercoles" v-else-if="DiaActual1 === 3">Mie</div>
				<div class="jueves" v-else-if="DiaActual1 === 4">Jue</div>
				<div class="viernes" v-else-if="DiaActual1 === 5">Vie</div>
				<div class="jueves" v-else-if="DiaActual1 === 6">Sab</div>
				<div class="viernes" v-else-if="DiaActual1 === 7">Dom</div>
				<div class="viernes" v-else-if="DiaActual1 === 8">Lun</div>
				<div class="viernes" v-else-if="DiaActual1 === 9">Mar</div>
				<div class="viernes" v-else-if="DiaActual1 === 10">Mie</div>
				<div class="viernes" v-else-if="DiaActual1 === 11">Jue</div>
				<div class="viernes" v-else-if="DiaActual1 === 12">Vie</div>
				<div class="viernes" v-else-if="DiaActual1 === 13">Sab</div>
				<div class="viernes" v-else-if="DiaActual1 === 14">Dom</div>

				<div class="lunes" v-if="DiaActual2 === 1">Lun</div>
				<div class="martes" v-else-if="DiaActual2 === 2">Mar</div>
				<div class="miercoles" v-else-if="DiaActual2 === 3">Mie</div>
				<div class="jueves" v-else-if="DiaActual2 === 4">Jue</div>
				<div class="viernes" v-else-if="DiaActual2 === 5">Vie</div>
				<div class="jueves" v-else-if="DiaActual2 === 6">Sab</div>
				<div class="viernes" v-else-if="DiaActual2 === 7">Dom</div>
				<div class="viernes" v-else-if="DiaActual2 === 8">Lun</div>
				<div class="viernes" v-else-if="DiaActual2 === 9">Mar</div>
				<div class="viernes" v-else-if="DiaActual2 === 10">Mie</div>
				<div class="viernes" v-else-if="DiaActual2 === 11">Juev</div>
				<div class="viernes" v-else-if="DiaActual2 === 12">Vie</div>
				<div class="viernes" v-else-if="DiaActual2 === 13">Sab</div>
				<div class="viernes" v-else-if="DiaActual2 === 14">Dom</div>

				<div class="lunes" v-if="DiaActual3 === 1">Lun</div>
				<div class="martes" v-else-if="DiaActual3 === 2">Mar</div>
				<div class="miercoles" v-else-if="DiaActual3 === 3">Mie</div>
				<div class="jueves" v-else-if="DiaActual3 === 4">Jue</div>
				<div class="viernes" v-else-if="DiaActual3 === 5">Vie</div>
				<div class="jueves" v-else-if="DiaActual3 === 6">Sab</div>
				<div class="viernes" v-else-if="DiaActual3 === 7">Dom</div>
				<div class="viernes" v-else-if="DiaActual3 === 8">Lun</div>
				<div class="viernes" v-else-if="DiaActual3 === 9">Mar</div>
				<div class="viernes" v-else-if="DiaActual3 === 10">Mie</div>
				<div class="viernes" v-else-if="DiaActual3 === 11">Jue</div>
				<div class="viernes" v-else-if="DiaActual3 === 12">Vie</div>
				<div class="viernes" v-else-if="DiaActual3 === 13">Sab</div>
				<div class="viernes" v-else-if="DiaActual3 === 14">Dom</div>

				<div class="lunes" v-if="DiaActual4 === 1">Lun</div>
				<div class="martes" v-else-if="DiaActual4 === 2">Mar</div>
				<div class="miercoles" v-else-if="DiaActual4 === 3">Mie</div>
				<div class="jueves" v-else-if="DiaActual4 === 4">Jue</div>
				<div class="viernes" v-else-if="DiaActual4 === 5">Vier</div>
				<div class="jueves" v-else-if="DiaActual4 === 6">Sab</div>
				<div class="viernes" v-else-if="DiaActual4 === 7">Dom</div>
				<div class="viernes" v-else-if="DiaActual4 === 8">Lun</div>
				<div class="viernes" v-else-if="DiaActual4 === 9">Mar</div>
				<div class="viernes" v-else-if="DiaActual4 === 10">Mie</div>
				<div class="viernes" v-else-if="DiaActual4 === 11">Jue</div>
				<div class="viernes" v-else-if="DiaActual4 === 12">Vie</div>
				<div class="viernes" v-else-if="DiaActual4 === 13">Sab</div>
				<div class="viernes" v-else-if="DiaActual4 === 14">Dom</div>

				<div class="calendar-img">
					<img v-if="calendarImg1 === 800" src="..\assets\png\023-sun.png" alt="logo" />
					<img v-if="calendarImg1 === 201" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg1 === 202" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg1 === 210" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg1 === 211" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg1 === 212" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg1 === 221" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg1 === 230" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg1 === 231" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg1 === 232" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg1 === 200" src="..\assets\png\028-storm-1.png" alt="logo" />

					<img v-if="calendarImg1 === 300" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg1 === 301" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg1 === 302" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg1 === 311" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg1 === 312" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg1 === 313" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg1 === 314" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg1 === 321" src="..\assets\png\022-rain.png" alt="logo" />

					<img v-if="calendarImg1 === 500" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg1 === 501" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg1 === 502" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg1 === 503" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg1 === 504" src="..\assets\png\028-storm-1.png" alt="logo" />

					<img v-if="calendarImg1 === 511" src="..\assets\png\037-thermometer.png" alt="logo" />

					<img v-if="calendarImg1 === 520" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg1 === 521" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg1 === 522" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg1 === 531" src="..\assets\png\022-rain.png" alt="logo" />

					<img v-if="calendarImg1 === 600" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg1 === 601" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg1 === 602" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg1 === 611" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg1 === 612" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg1 === 613" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg1 === 615" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg1 === 616" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg1 === 620" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg1 === 621" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg1 === 622" src="..\assets\png\029-hail.png" alt="logo" />

					<img v-if="calendarImg1 === 701" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg1 === 711" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg1 === 721" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg1 === 731" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg1 === 741" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg1 === 751" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg1 === 761" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg1 === 762" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg1 === 771" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg1 === 781" src="..\assets\png\021-fog.png" alt="logo" />

					<img v-if="calendarImg1 === 801" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg1 === 802" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg1 === 803" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg1 === 804" src="..\assets\png\050-cloudy-1.png" alt="logo" />
				</div>
				<div class="calendar-img">
					<img v-if="calendarImg2 === 800" src="..\assets\png\023-sun.png" alt="logo" />
					<img v-if="calendarImg2 === 201" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg2 === 202" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg2 === 210" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg2 === 211" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg2 === 212" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg2 === 221" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg2 === 230" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg2 === 231" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg2 === 232" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg2 === 200" src="..\assets\png\028-storm-1.png" alt="logo" />

					<img v-if="calendarImg2 === 300" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg2 === 301" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg2 === 302" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg2 === 311" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg2 === 312" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg2 === 313" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg2 === 314" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg2 === 321" src="..\assets\png\022-rain.png" alt="logo" />

					<img v-if="calendarImg2 === 500" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg2 === 501" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg2 === 502" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg2 === 503" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg2 === 504" src="..\assets\png\028-storm-1.png" alt="logo" />

					<img v-if="calendarImg2 === 511" src="..\assets\png\037-thermometer.png" alt="logo" />

					<img v-if="calendarImg2 === 520" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg2 === 521" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg2 === 522" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg2 === 531" src="..\assets\png\022-rain.png" alt="logo" />

					<img v-if="calendarImg2 === 600" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg2 === 601" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg2 === 602" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg2 === 611" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg2 === 612" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg2 === 613" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg2 === 615" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg2 === 616" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg2 === 620" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg2 === 621" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg2 === 622" src="..\assets\png\029-hail.png" alt="logo" />

					<img v-if="calendarImg2 === 701" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg2 === 711" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg2 === 721" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg2 === 731" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg2 === 741" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg2 === 751" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg2 === 761" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg2 === 762" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg2 === 771" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg2 === 781" src="..\assets\png\021-fog.png" alt="logo" />

					<img v-if="calendarImg2 === 801" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg2 === 802" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg2 === 803" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg2 === 804" src="..\assets\png\050-cloudy-1.png" alt="logo" />
				</div>
				<div class="calendar-img">
					<img v-if="calendarImg3 === 800" src="..\assets\png\023-sun.png" alt="logo" />
					<img v-if="calendarImg3 === 201" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg3 === 202" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg3 === 210" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg3 === 211" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg3 === 212" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg3 === 221" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg3 === 230" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg3 === 231" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg3 === 232" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg3 === 200" src="..\assets\png\028-storm-1.png" alt="logo" />

					<img v-if="calendarImg3 === 300" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg3 === 301" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg3 === 302" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg3 === 311" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg3 === 312" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg3 === 313" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg3 === 314" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg3 === 321" src="..\assets\png\022-rain.png" alt="logo" />

					<img v-if="calendarImg3 === 500" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg3 === 501" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg3 === 502" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg3 === 503" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg3 === 504" src="..\assets\png\028-storm-1.png" alt="logo" />

					<img v-if="calendarImg3 === 511" src="..\assets\png\037-thermometer.png" alt="logo" />

					<img v-if="calendarImg3 === 520" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg3 === 521" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg3 === 522" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg3 === 531" src="..\assets\png\022-rain.png" alt="logo" />

					<img v-if="calendarImg3 === 600" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg3 === 601" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg3 === 602" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg3 === 611" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg3 === 612" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg3 === 613" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg3 === 615" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg3 === 616" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg3 === 620" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg3 === 621" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg3 === 622" src="..\assets\png\029-hail.png" alt="logo" />

					<img v-if="calendarImg3 === 701" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg3 === 711" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg3 === 721" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg3 === 731" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg3 === 741" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg3 === 751" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg3 === 761" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg3 === 762" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg3 === 771" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg3 === 781" src="..\assets\png\021-fog.png" alt="logo" />

					<img v-if="calendarImg3 === 801" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg3 === 802" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg3 === 803" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg3 === 804" src="..\assets\png\050-cloudy-1.png" alt="logo" />
				</div>
				<div class="calendar-img">
					<img v-if="calendarImg4 === 800" src="..\assets\png\023-sun.png" alt="logo" />
					<img v-if="calendarImg4 === 201" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 202" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 210" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 211" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 212" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 221" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 230" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 231" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 232" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 200" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 300" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg4 === 301" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg4 === 302" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg4 === 311" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg4 === 312" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg4 === 313" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg4 === 314" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg4 === 321" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg4 === 500" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 501" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 502" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 503" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 504" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg4 === 511" src="..\assets\png\037-thermometer.png" alt="logo" />
					<img v-if="calendarImg4 === 520" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg4 === 521" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg4 === 522" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg4 === 531" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg4 === 600" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg4 === 601" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg4 === 602" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg4 === 611" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg4 === 612" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg4 === 613" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg4 === 615" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg4 === 616" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg4 === 620" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg4 === 621" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg4 === 622" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg4 === 701" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg4 === 711" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg4 === 721" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg4 === 731" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg4 === 741" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg4 === 751" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg4 === 761" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg4 === 762" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg4 === 771" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg4 === 781" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg4 === 801" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg4 === 802" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg4 === 803" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg4 === 804" src="..\assets\png\050-cloudy-1.png" alt="logo" />
				</div>
				<div class="calendar-img">
					<img v-if="calendarImg5 === 800" src="..\assets\png\023-sun.png" alt="logo" />
					<img v-if="calendarImg5 === 201" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 202" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 210" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 211" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 212" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 221" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 230" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 231" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 232" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 200" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 300" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg5 === 301" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg5 === 302" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg5 === 311" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg5 === 312" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg5 === 313" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg5 === 314" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg5 === 321" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg5 === 500" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 501" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 502" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 503" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 504" src="..\assets\png\028-storm-1.png" alt="logo" />
					<img v-if="calendarImg5 === 511" src="..\assets\png\037-thermometer.png" alt="logo" />
					<img v-if="calendarImg5 === 520" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg5 === 521" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg5 === 522" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg5 === 531" src="..\assets\png\022-rain.png" alt="logo" />
					<img v-if="calendarImg5 === 600" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg5 === 601" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg5 === 602" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg5 === 611" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg5 === 612" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg5 === 613" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg5 === 615" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg5 === 616" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg5 === 620" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg5 === 621" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg5 === 622" src="..\assets\png\029-hail.png" alt="logo" />
					<img v-if="calendarImg5 === 701" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg5 === 711" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg5 === 721" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg5 === 731" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg5 === 741" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg5 === 751" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg5 === 761" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg5 === 762" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg5 === 771" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg5 === 781" src="..\assets\png\021-fog.png" alt="logo" />
					<img v-if="calendarImg5 === 801" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg5 === 802" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg5 === 803" src="..\assets\png\050-cloudy-1.png" alt="logo" />
					<img v-if="calendarImg5 === 804" src="..\assets\png\050-cloudy-1.png" alt="logo" />
				</div>
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
			calendarImg1: "",
			calendarImg2: "",
			calendarImg3: "",
			calendarImg4: "",
			calendarImg5: "",
			DiaActual: "",
			DiaActual1: "",
			DiaActual2: "",
			DiaActual3: "",
			DiaActual4: "",
			error: 0,
		};
	},
	components: {},
	methods: {
		async callTiempo() {
			try {
				const res = await fetch(
					`https://api.openweathermap.org/data/2.5/weather?q=${this.nombre}&appid=6cd01d16690d7cf5421a4f285c854c5d&lang=es`
				);
				const data = await res.json();
				this.nombre = data.name;
				this.pronostico = data.weather[0].description;
				this.temperatura = Math.floor(data.main.temp - 273.15);
				this.viento = data.wind.speed;
				this.temperatura_min = Math.floor(data.main.temp_min - 275.5);
				this.temperatura_max = Math.floor(data.main.temp_max - 273.15);
				this.lluvia = data.main.humidity;
				this.imagen = data.weather[0];
				console.log(data);
				this.error = this.error - 1;
				this.error = 0;
			} catch (error) {
				console.log(error);
				this.error = this.error + 1;
			}
		},
		async callDias() {
			const res = await fetch(
				`https://api.openweathermap.org/data/2.5/forecast?q=${this.nombre}&appid=4f99f2cab90608915fdecfc3d2399794&lang=es`
			);
			const data = await res.json();
			this.calendarImg1 = data.list[2].weather[0].id;
			this.calendarImg2 = data.list[3].weather[0].id;
			this.calendarImg3 = data.list[4].weather[0].id;
			this.calendarImg4 = data.list[5].weather[0].id;
			this.calendarImg5 = data.list[6].weather[0].id;
			const diaActual = new Date();
			const dia = diaActual.getDay();
			this.DiaActual = dia + 1;
			this.DiaActual1 = dia + 2;
			this.DiaActual2 = dia + 3;
			this.DiaActual3 = dia + 4;
			this.DiaActual4 = dia + 5;
			console.log(dia);
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

	background: linear-gradient(
		to left,
		#1cb5e0,
		#000046
	); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

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
main h4 {
	text-align: center;
	color: rgb(250, 7, 7);
	margin: 0;
	padding: 1rem;
	border: 1px solid rgb(250, 7, 7);
	margin-bottom: 2rem;
	background: #ffffff;
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
	outline: none;
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
	filter: drop-shadow(30px 30px 4px #0d0d0eb2);
}
.principal h1 {
	font-size: 5rem;
	padding: 1rem;
	color: #ffffff;
	filter: drop-shadow(20px 25px 4px #0d0d0eb2);
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
	font-size: 1.7rem;
	font-style: normal;
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
.calendario img {
	width: 50px;
	height: 50px;
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
@media (max-width: 400px) {
	body {
		margin: 0;
		padding: 0;

		background: #177f9c; /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

		font-family: "Exo 2", sans-serif;
	}
	.principal img {
		width: 7rem;
		height: 7rem;
		padding: 1rem;
	}
	.principal h1 {
		font-size: 3rem;
		padding: 1rem;
		color: #ffffff;
	}
	.info i {
		font-size: 1.5rem;
	}
}
</style>
