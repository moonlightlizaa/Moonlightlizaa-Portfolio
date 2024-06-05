<script>


	import { onMount } from 'svelte';



onMount(() => {

		// GitHub API laat maar 30 zien bij default
		// Verander username
			const apiUrl = `https://api.github.com/users/moonlightlizaa/repos?sort=updated&per_page=50`;

	
	fetch(apiUrl)
		.then((response) => response.json())
		.then((repos) => {
			repos = repos.map((repo) => {
				return {
					...repo,
					name: repo.name.replace(/-/g, ' ') // deze line zorgt ervoor dat er spaties staan ipv - 
				};
			});

				// Haal de volgende regel weg om alle repo's te krijgen op de website, wil je dit niet dan kan je de beste repo's een ster
				// geven zodat je alleen die ziet :) 

			repos = repos.filter((repo) => repo.stargazers_count > 0);

			// Sorteert het werk van hoog naar laag ster

			repos.sort((a, b) => b.stargazers_count - a.stargazers_count);

			const container = document.getElementById('repos-container');
			repos.forEach((repo) => {
				const repository = document.createElement('section');
				repository.className = 'repository';
				repository.innerHTML = `
					
					<h3> 
						<a href="${repo.html_url}" target="_blank">${repo.name}</a>
					<h3>
				<article>
					<a href="${repo.homepage}" target="_blank"> ${repo.homepage || 'no link available'} </a>
					
					<p>${repo.description || 'No description available.'} </p>
				</article>


				
				`;
				container.appendChild(repository);
			});
		})
		.catch((error) => console.error('Error fetching repos:', error));
});
</script>

<section class="github-portfolio">
	<h2>my work on github ✨</h2>

	<nav>
		<input
			class="searchbar"
			type="text"
			id="searchInput"
			onkeyup="search()"
			placeholder="Zoek een repo..."
		/>
	</nav>

	<ul id="repos-container"></ul>
</section>


<style>
	.github-portfolio {
		height: 101vh;
		margin: 1em;
	}
</style>