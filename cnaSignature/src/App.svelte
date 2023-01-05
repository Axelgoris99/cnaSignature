<script>
	let image =
		'https://ci5.googleusercontent.com/proxy/EdHi45teqg6RYjuZWqBt8Ui0z42SuWZvnHRKCT7xYskWy13gsi0pqfvn6_WXUApItCrz5MPLsxvaJLfTTJUtx3HupcMfLobqrvwtjyglxaMXnh0B4vwfYhR_0uE06Q=s0-d-e1-ft#https://www.centraliens-nantes.org/medias/image/16232021165c07e85253b25.png';
	let prenom = '';
	let nom = '';
	let roleCna = '';
	let job = '';
	let promotion = '';
	let phone = '';
	let email = '';
	/**
	 * @param {string} string
	 */
	function capitalizeFirstLetter(string) {
		if (!string) return;
		return string[0].toUpperCase() + string.substring(1);
	}
	$: fullName = capitalizeFirstLetter(prenom) + ' ' + nom.toUpperCase();
	$: role = capitalizeFirstLetter(roleCna);
	$: work = capitalizeFirstLetter(job);
</script>
<main>
<div class="main">
	<h1>Signature CNA</h1>
	<h2>Informations</h2>
	<p>
		Vous pouvez modifier les informations ci-dessous pour obtenir votre signature CNA.<br />
		Vous pouvez ensuite le copier et le coller dans votre signature.
	</p>
	<div class="inside">
		<div class="input">
			Prénom <input bind:value={prenom} />
			Nom <input bind:value={nom} />
			Rôle CNA <input bind:value={roleCna} />
			Métier <input bind:value={job} />
			Promotion <input bind:value={promotion} />
			Numéro de Téléphone<input type="tel" bind:value={phone} />
			Email nécessaire seulement si votre mail est différent de prenom.nom
			<input type="email" bind:value={email} />
		</div>
	</div>
	<div id="signature">
		<table style="font-family:&quot;Times New Roman&quot;;color: #0F2748;">
			<tbody style="font-family:&quot;Titillium Web&quot;,Arial,sans-serif"
				><tr
					><td rowspan="8" width="140" valign="top"
						><a
							href="https://www.centraliens-nantes.org/"
							style="color:rgb(17,85,204)"
							target="blank"
							><img
								src="https://ci5.googleusercontent.com/proxy/EdHi45teqg6RYjuZWqBt8Ui0z42SuWZvnHRKCT7xYskWy13gsi0pqfvn6_WXUApItCrz5MPLsxvaJLfTTJUtx3HupcMfLobqrvwtjyglxaMXnh0B4vwfYhR_0uE06Q=s0-d-e1-ft#https://www.centraliens-nantes.org/medias/image/16232021165c07e85253b25.png"
								alt="Centrale Nantes Alumni |"
								width="130"
							/></a
						></td
					><td
						>{#if prenom || nom}<table style="font-family:&quot;Times New Roman&quot;">
								<tbody style="font-family:&quot;Titillium Web&quot;,Arial,sans-serif"
									><tr><td style="font-size:medium;font-weight:900">{fullName}</td></tr><tr
									/></tbody
								>
							</table>{/if}
						{#if role}<i>&nbsp;{role}</i>{/if}
						{#if work}<br />&nbsp;{work}<br />{/if}</td
					></tr
				>
				{#if (prenom || nom || job || roleCna) && ((prenom && nom) || promotion || phone || email)}<tr
						><td
							><img
								src="https://ci5.googleusercontent.com/proxy/nyh4uQGLFFuxSIZGFJxvcDcBu5z-GFtT9h6SxuNLWYCv2k8H6LcsqeUIxKOQ4WkNST_qG6Rqv5OVx7JxWZDMpYIPHCXT2-vcUdH4HFtCj4YcUQvg9Qg5=s0-d-e1-ft#https://www.ec-nantes.fr/medias/photo/v_tiret-sign_1492585977585-png"
								alt="----"
								height="12"
							/></td
						></tr
					>{/if}<tr>
					<td
						>{#if promotion}&nbsp;Promotion E{promotion}<br />{/if}
						{#if phone}&nbsp;<a href="tel:{phone}}" style="color:rgb(14,39,72)" target="blank">
								T&nbsp;:&nbsp;{phone}</a
							><br />{/if}
						{#if email}&nbsp;<a
								href="mailto:florian.bartocci@centraliens-nantes.com"
								style="color:rgb(14,39,72);font-weight:bold"
								target="blank"
							>
								{email}@centraliens-nantes.com</a
							><br />
						{:else if prenom || nom}&nbsp;<a
								href="mailto:{prenom}.{nom}@centraliens-nantes.com"
								style="color:rgb(14,39,72);font-weight:bold"
								target="blank"
							>
								{prenom.toLowerCase()}.{nom.toLowerCase()}@centraliens-nantes.com</a
							>
						{/if}
					</td></tr
				></tbody
			>
		</table>
	</div>
	<!-- <div id="signature2" class="signature">
			<a href="https://www.centraliens-nantes.org/" target="blank"
				><img src={image} alt="" width="130px" /></a
			>
			<div class="text">
				{#if prenom || nom}<p class="prenom">
						{fullName}
					</p>{/if}
				{#if roleCna}<i class="role">{role}</i>{/if}
				{#if job}<p class="job">{work}</p>{/if}
				{#if (prenom || nom || job || roleCna) && ((prenom && nom) || promotion || phone || email)}<img
						src="https://ci5.googleusercontent.com/proxy/nyh4uQGLFFuxSIZGFJxvcDcBu5z-GFtT9h6SxuNLWYCv2k8H6LcsqeUIxKOQ4WkNST_qG6Rqv5OVx7JxWZDMpYIPHCXT2-vcUdH4HFtCj4YcUQvg9Qg5=s0-d-e1-ft#https://www.ec-nantes.fr/medias/photo/v_tiret-sign_1492585977585-png"
						alt=""
						height="12px"
						width="30px"
					/>{/if}
				{#if promotion}<p class="promotion">Promotion E{promotion}</p>{/if}
				{#if phone}<p><a href="tel:{phone}" class="phone">T : {phone}</a></p>{/if}
				{#if email}<p>
						<a href="mailto:{email}@centraliens-nantes.com" class="email"
							>{email}@centraliens-nantes.com</a
						>
					</p>
				{:else if prenom && nom}
					<p>
						<a href="mailto:{prenom}.{nom}@centraliens-nantes.com" class="email"
							>{prenom.toLowerCase()}.{nom.toLowerCase()}@centraliens-nantes.com</a
						>
					</p>{/if}
			</div>
		</div>-->

	<button
		on:click={() => {
			if (typeof ClipboardItem === 'undefined') {
				alert(
					"Désolé! Cette fonctionnalité n'est pas disponible dans le navigateur Firefox. Vous pouvez en utiliser un autre!\n\n" +
						'Toutefois, sélectionner le texte, le copier et le coller dans votre signature fonctionne très bien.'
				);
				return;
			}
			const htmlCode = document.getElementById('signature').innerHTML;
			const blobInput = new Blob([htmlCode], { type: 'text/html' });
			navigator.clipboard.write([new ClipboardItem({ 'text/html': blobInput })]);
			alert('Copié !');
		}}>Copier la signature</button
	>
	Plus qu'à la coller !
</div>
</main>
<style>
	@import url('https://fonts.googleapis.com/css2?family=Titillium+Web:wght@400;700;900&display=swap');

	:root {
		--blue: #0e2748;
		--yellow: #fab500;
	}
	h1 {
		color: var(--blue);
		margin-bottom: 5px;
	}
	h2 {
		margin-top: 5px;
		color: var(--yellow);
	}
	p {
		margin: 0;
	}
	input {
		margin: 2px;
	}
	.main {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.inside {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin: 20px;
	}
	.input {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin: 20px;
	}
	/* .signature {
		display: flex;
		flex-direction: row;
		align-items: top;
	} */
</style>
