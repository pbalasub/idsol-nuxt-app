<template>
	<v-app id="inspire">
		<v-navigation-drawer v-model="drawer" app>
			<!--  -->
		</v-navigation-drawer>
		<v-app-bar app color="primary" prominent>
			<v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
			<v-toolbar-title>Industrial Automation</v-toolbar-title>
			<v-menu>
				<template v-slot:activator="{ props }">
					<v-btn v-bind="props">
						Activator slot
					</v-btn>
				</template>
				<v-list>
					<v-list-item v-for="(item, index) in items" :key="index" :value="index">
						<v-list-item-title>{{ item.title }}</v-list-item-title>
					</v-list-item>
				</v-list>
			</v-menu>
			<v-menu>
				<template v-slot:activator="{ props }">
					<v-btn v-bind="props">
						Activator slot
					</v-btn>
				</template>
				<v-list>
					<v-list-item v-for="(item, index) in items" :key="index" :value="index">
						<v-list-item-title>{{ item.title }}</v-list-item-title>
					</v-list-item>
				</v-list>
			</v-menu>
			<v-icon>mdi-account-arrow-right</v-icon>
		</v-app-bar>

		<v-main>
			<v-container>
				<slot />
			</v-container>
		</v-main>
	</v-app>
</template>

<script>
export default {
	data: () => ({
		drawer: null,
		items: [
			{ title: 'Click Me' },
			{ title: 'Click Me' },
			{ title: 'Click Me' },
			{ title: 'Click Me 2' },
		],
	}),
}
</script>