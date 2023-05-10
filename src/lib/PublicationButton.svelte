<script>
    export let publicationUrl;
    export let height = "50px";
    export let imgSrc;
</script>

<a href={publicationUrl} target="_blank">
    <img
        class="publication-btn"
        src={imgSrc}
        height={height}
        width="auto"
        alt="Play Store"
    />
</a>

<style>
    
	.publication-btn {
		transform: scale(1);
		transition: transform 0.2s;
        position: relative;
	}

	.publication-btn:hover {
		transform: scale(1.2);
        z-index: 3;
		/* opacity: 75%; */
	}
</style>