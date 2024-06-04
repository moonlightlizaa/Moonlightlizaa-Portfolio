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
					name: repo.name.replace(/-/g, ' ')
				};
			});

				// Haal de volgende regel weg om alle repo's te krijgen op de website, wil je dit niet dan kan je de beste repo's een ster
				// geven zodat je alleen die ziet :) 

			repos = repos.filter((repo) => repo.stargazers_count > 0);

			// Sorteert het werk van hoog naar laag ster

			repos.sort((a, b) => b.stargazers_count - a.stargazers_count);

			const container = document.getElementById('repos-container');
			repos.forEach((repo) => {
				const repository = document.createElement('div');
				repository.className = 'repository';
				repository.innerHTML = `

		 	 <h2>
				<a href="${repo.html_url}" target="_blank">${repo.name}</a>
			</h2>

		  	<p>
				<a href="${repo.homepage}" target="_blank">${repo.homepage || 'no link available'}</a>
			</p>

		 	 <p>${repo.description || 'No description available.'}

			</p>

	  <section>⭐ ${repo.stargazers_count} | 👁️ ${repo.watchers_count} | 🍴 ${repo.forks_count}</section>
	  `;
				container.appendChild(repository);
			});
		})
		.catch((error) => console.error('Error fetching repos:', error));
});
</script>

<section class="other">
	<h1>Alle repo's</h1>

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


