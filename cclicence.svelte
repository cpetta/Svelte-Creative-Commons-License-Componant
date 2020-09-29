<script>
	export let author = "";
	export let authorURL = "";
	export let workName = "";
	export let workURL = "";
	export let licenceType = "";
	
	let authorHtml = "";
	let workNameHtml = "";
	let licenceURL = "";
	let licenceName = "";
	let licenceImg = "";
	let licenceImg2 = "";
	let licenceImg3 = "";
	
	let zero = `<img style="height: 22px !important;margin-left: 3px;vertical-align: text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/zero.svg" alt="" />`;
	let by = `<img style="height: 22px !important;margin-left: 3px;vertical-align: text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg" alt="" />`;
	let sa = `<img style="height: 22px !important;margin-left: 3px;vertical-align: text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg" alt="" />`;
	let nc = `<img style="height: 22px !important;margin-left: 3px;vertical-align: text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg" alt="" />`;
	let nd = `<img style="height: 22px !important;margin-left: 3px;vertical-align: text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nd.svg" alt="" />`;
	
	if(author !== "") {
		authorHtml = `by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href=${authorURL}>${author}</a>`;
	}
	
	if(workName !== "") {
		workNameHtml = `<a rel="cc:attributionURL" property="dct:title" href=${workURL}>${workName}</a>`;
	} else if(workURL !== "") {
		workNameHtml = `<a rel="cc:attributionURL" property="dct:title" href=${workURL}>This work</a>`;
	} else {
		workNameHtml = "This work";
	}
	
	switch(licenceType) {
		case "zero":
			licenceURL = "https://creativecommons.org/publicdomain/zero/1.0";
			licenceName = "CC CC0 1.0";
			licenceImg = zero;
			break;
			
		case "by":
			licenceURL = "https://creativecommons.org/licenses/by/4.0";
			licenceName = "CC BY 4.0";
			licenceImg = by;
			break;
			
		case "by-sa":
			licenceURL = "https://creativecommons.org/licenses/by-sa/4.0";
			licenceName = "CC BY-SA 4.0";
			licenceImg = by;
			licenceImg2 = sa;
			break;
			
		case "by-nd":
			licenceURL = "https://creativecommons.org/licenses/by-nd/4.0";
			licenceName = "CC BY-ND 4.0";
			licenceImg = by;
			licenceImg2 = nd;
			break;
			
		case "by-nc":
			licenceURL = "https://creativecommons.org/licenses/by-nc/4.0";
			licenceName = "CC BY-NC 4.0";
			licenceImg = by;
			licenceImg2 = nc;
			break;
			
		case "by-nc-sa":
			licenceURL = "https://creativecommons.org/licenses/by-nc-sa/4.0";
			licenceName = "CC BY-NC-SA 4.0";
			licenceImg = by;
			licenceImg2 = nc;
			licenceImg3 = sa;
			break;
			
		case "by-nc-nd":
			licenceURL = "https://creativecommons.org/licenses/by-nc-nd/4.0";
			licenceName = "CC BY-NC-ND 4.0";
			licenceImg = by;
			licenceImg2 = nc;
			licenceImg3 = nd;
			break;
		defaut:
			break;
	}
	
</script>

<style>
	img {
		height: 22px;
		margin-left: 3px;
		vertical-align: text-bottom;
	}
</style>

<p 
	 xmlns:dct="http://purl.org/dc/terms/" 
	 xmlns:cc="http://creativecommons.org/ns#" 
	 class="license-text">
	{@html workNameHtml}
	{@html authorHtml}
	is licensed under
	<a rel="license" href={licenceURL}>{licenceName}<img src="https://mirrors.creativecommons.org/presskit/icons/cc.svg" alt="" />{@html licenceImg}{@html licenceImg2}{@html licenceImg3}</a>
</p>
