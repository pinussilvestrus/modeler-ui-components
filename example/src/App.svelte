<script>
	import Modeler from './components/Modeler.svelte';
	import StatusBar from './components/StatusBar.svelte';

	import diagram from '../resources/diagram.bpmn';

	import 'modeler-ui-components/dist/styles/modeler-ui.css';
</script>

<main>
	<div class="app-container">
		<Modeler xml={ diagram } />
		<StatusBar />
	</div>
	<div class="background"></div>
</main>

<style>
	@import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@300;400;500;600;700&display=swap');

	main {
		height: 100%;
	}

	.app-container {
		position: absolute;
    display: flex;
    flex-direction: column;
    top: calc(10vh - 15px);
    left: 10vw;
    width: 80vw;
    height: 80vh;
    border-radius: 16px;
		background: var(--color-grey-225-10-85);
    box-shadow: 0 6px 30px 0 rgb(0 0 0 / 40%);
    overflow: hidden;
	}

	.background {
    z-index: -1;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-size: cover;
    background-position: center;
		background-image: url(../wallpaper-mac.jpg);
	}
</style>