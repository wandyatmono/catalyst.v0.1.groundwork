<script lang="ts">
	let selectedTheme: string = 'purple-dark'; // default theme

	const changeTheme = (event: Event) => {
		const target = event.target as HTMLInputElement;
		selectedTheme = target.value;
	};
</script>

<div id="components-wrapper" class="membrane" data-theme={selectedTheme}>
	<slot />
	<!-- Switcher -->
	<input
		type="radio"
		id="indigo-light"
		name="themes"
		value="indigo-light"
		on:change={changeTheme}
	/>
	<input type="radio" id="indigo-dark" name="themes" value="indigo-dark" on:change={changeTheme} />
	<input
		type="radio"
		id="purple-light"
		name="themes"
		value="purple-light"
		on:change={changeTheme}
	/>
	<input
		type="radio"
		id="purple-dark"
		name="themes"
		value="purple-dark"
		on:change={changeTheme}
		checked
	/>
	<div class="wrapper">
		<div class="color-palette">
			<label for="indigo-light" />
			<label for="indigo-dark" />
			<label for="purple-light" />
			<label for="purple-dark" />
		</div>
	</div>
</div>

<style>
	#components-wrapper {
		min-height: 100vh;
	}
</style>
