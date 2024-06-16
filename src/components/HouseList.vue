<script lang="ts">
import { PropType, defineComponent } from "vue";
import House from "../types/House";
import Order from "../types/Order";

export default defineComponent({
	props: {
		houses: {
			type: Array as PropType<House[]>,
			required: true,
		},
		order: {
			type: String as PropType<Order>,
			required: true,
		},
	},
	setup(props) {
		console.log(props.houses);
	},
});
</script>

<template>
	<div class="hous-list">
    <h3>Order by {{ order }}</h3>
		<ul>
			<li v-for="st in houses" :key="st.id">
				<h2>
					{{ st.name }} in {{ st.region }} region. Square meters:
					{{ st.square }}
				</h2>
				<div class="price">
					<p>Price: $ {{ st.price }}</p>
				</div>
				<div class="description">
					<p>
						Lorem ipsum dolor sit amet consectetur adipisicing elit.
						Nam nihil quasi, quidem placeat quis veniam, vel et
						consectetur tempore porro impedit non ea, quisquam
						voluptatem. Blanditiis tenetur quo cupiditate ut.
					</p>
				</div>
			</li>
		</ul>
	</div>
</template>

<style scoped>
.hous-list {
	max-width: 960px;
	margin: 40px auto;
}
.hous-list ul {
	padding: 0;
}
.hous-list li {
	list-style-type: none;
	background: white;
	padding: 16px;
	margin: 16px 0;
	border-radius: 4px;
}
.hous-list h2 {
	margin: 0 0 10px;
	text-transform: capitalize;
}
.price {
	display: flex;
}
.price img {
	width: 30px;
}
.price p {
	color: #17bf66;
	font-weight: bold;
	margin: 10px 4px;
}
</style>
