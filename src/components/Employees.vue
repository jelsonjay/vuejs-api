<template>
	<div class="container">
		<h1>Employee List</h1>
		<table class="table table-hover ">
			<thead class="table-primary">
				<tr>
					<th scope="col">Id</th>
					<th scope="col">Name</th>
					<th scope="col">Email</th>
					<th scope="col">City</th>
				</tr>
			</thead>
			<tbody>
				<tr v-for="user in user" v-bind:key="user.id">
					<th scope="row">{{ user.id }}</th>
					<td>{{ user.name }}</td>
					<td>{{ user.email }}</td>
					<td>{{ user.address.city }}</td>
				</tr>
				<tr></tr>
			</tbody>
		</table>
	</div>
</template>
<script>
import axios from 'axios';

export default {
	name: 'Employees',
	data() {
		return {
			Employee: null
		};
	},
	created: function() {
		axios.get('https://jsonplaceholder.typicode.com/users').then((res) => {
			this.user = res.data;
		});
	}
};
</script>
<style>
h1 {
	margin: 1rem;
}
table {
	cursor: pointer;
}
</style>
