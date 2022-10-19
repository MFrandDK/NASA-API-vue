<template>
    <footer>
        <h4>NASA Picture of The Day - Markus Frandsen</h4>
    </footer>
</template>

<script>

export default {
    name: 'NasaFooter'
};

</script>

<style scoped> 
footer {
    position: relative;
	right: 0;
	left: 0;
	bottom: 0;
	height: 80px;
	display: flex;
	align-items: center;
	justify-content: center;
	background: rgba(32, 29, 29, 0.633);
	margin-top: 100px;
	border-top: 1px solid #1f1f1f;
	width: 100vw;
}

h4 {
    color: #dfdfdf;
	font-size: 14px;
	font-weight: 400;
}

</style>