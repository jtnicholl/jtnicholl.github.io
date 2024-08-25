---
layout: default
---

[Back To Home](index.md)

# Advanced Search

<figure>
	<a href="/assets/images/advsearch0.png" target="blank">
		<img height="78" width="150" src="/assets/images/advsearch0_thumb.png" />
	</a>
	<figcaption>Advanced Search</figcaption>
</figure>

While employed at Cosairus, I developed a search application to search release of information
requests. The search app uses a Vue.js frontend with an ASP.NET Core backend.

The search has 29 different search parameters. Unused options do not affect search performance.
There are also options for page size and sorting order. A SQL view does most of the work involved
in the search, while LINQ is used to compose a dynamic select statement to get a page of filtered
results and total result count. Users can only search for requests they have permission to access.

The search displays up to 1,000 paginated results, and up to 100,000 results can be exported as
CSV. The exported results are streamed to the user's device while the database connection is still
open, making it highly efficient.

Authentication is handled using ASP.NET Core Session cookies, after logging in either with a
one-time password, or cross-login from another application. I developed a two-way cross-login
system with an existing, entirely separate React application so that logging in to one application
allows seamless access to the other. This was accomplished by passing short-lived JSON web tokens
from one application to the other. This is a similar technique what is used when signing in to a
website though a third party account, such as a Google or Facebook account.

This link was made both ways. Returning back to the user's search brought back up the previous
search results, scrolling down to the release that was selected. To avoid storing the entire search
query in the JWT, the search parameters were hashed and stored in a Redis database using the hash
as a key. Then, only the hash needed to be passed in the JWTs.

### Additional Screenshots

<ul class="gallery">
	<li>
		<a href="/assets/images/advsearch1.png" target="blank">
			<img src="/assets/images/advsearch1_thumb.png" height="87" width="150" />
			<span>Search results, in dark mode</span>
		</a>
	</li>
	<li>
		<a href="/assets/images/advsearch2.png" target="blank">
			<img src="/assets/images/advsearch2_thumb.png" height="87" width="150" />
			<span>Login page</span>
		</a>
	</li>
</ul>
