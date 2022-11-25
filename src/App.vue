<script>
export default {
	data() {
		return {
			dataMahasiswa: [],
			nama: "",
			nim: "",
		};
	},
	methods: {
		simpanData() {
			var mahasiswa = {
				nama: this.nama,
				nim: this.nim,
			};
			this.dataMahasiswa.push(mahasiswa);
		},
	},
};
</script>

<template>
	<div class="container">
		<nav class="navbar navbar-expand-lg navbar-light bg-light">
			<div class="container-fluid">
				<a class="navbar-brand" href="#">Navbarr</a>
				<button
					class="navbar-toggler"
					type="button"
					data-bs-toggle="collapse"
					data-bs-target="#navbarNav"
					aria-controls="navbarNav"
					aria-expanded="false"
					aria-label="Toggle navigation"
				>
					<span class="navbar-toggler-icon"></span>
				</button>
				<div class="collapse navbar-collapse" id="navbarNav">
					<ul class="navbar-nav">
						<li class="nav-item">
							<router-link to="/" class="nav-link active"
								>Home</router-link
							>
						</li>
						<li class="nav-item">
							<router-link class="nav-link" to="/about"
								>About</router-link
							>
						</li>
					</ul>
				</div>
			</div>
		</nav>
		<router-view />
		<div class="container">
			<form>
				<p class="alert alert-success">Hello RajaIndraRamoza</p>
				<p>Nama</p>
				<input v-model="nama" type="text" class="form-text" />
				<p>Nim</p>
				<input v-model="nim" type="text" class="form-text" />
				<div class="mt-2">
					<button
						class="btn btn-success"
						type="submit"
						@click.prevent="simpanData"
					>
						Simpan
					</button>
				</div>
			</form>
		</div>

		<table class="table">
			<thead>
				<tr>
					<th>Nama</th>
					<th>Nim</th>
				</tr>
			</thead>
			<tbody>
				<tr v-for="item in dataMahasiswa" :key="item">
					<td>{{ item.nama }}</td>
					<td>{{ item.nim }}</td>
					<button>x</button>
					<button @click.prevent="$delete(item, key)">remove</button>
				</tr>
			</tbody>
		</table>
	</div>
</template>


<style>
</style>
