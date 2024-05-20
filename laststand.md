---
layout: default
---

[Back To Home](index.md)

# Last Stand (working title)

<figure>
	<a href="https://youtu.be/chEkzVIZrI0" target="blank">
		<img height="78" width="150" src="/assets/images/laststand0_thumb.png" />
	</a>
	<figcaption>Title screen (video)</figcaption>
</figure>

Last Stand is a live-service multiplayer game which I developed between jobs using
<a href="https://godotengine.org/" target="blank">Godot 4</a>. The game was not completed by the
time I was forced to pause development, but it is in a playable state.

## Gameplay Overview

Gameplay involves a team of 40+ defenders who spend ten minutes gathering supplies and building
defenses, after which they are attacked by the monster team, which consists of both other players
and NPCs. The defenders are much stronger, but the monsters respawn infinitely. Defenders who die
switch to the monster team, and the game ends once all defenders fall or their base is captured.
There is no winning or losing.

Communication is done through positional voice chat, or through global or team-separated text chat.

### Defenders

Players can select from three defender classes. Players who prefer to play as monsters can also
play as serfs, who complete tasks during the prep phase for rewards and leave to become monsters
when the fighting starts.

<figure>
	<a href="https://youtu.be/Cyj6XYr9HUY" target="blank">
		<img height="78" width="150" src="/assets/images/laststand1_thumb.png" />
	</a>
	<figcaption>Long rampage against a swarm of NPCs (video)</figcaption>
</figure>

Defender classes so far include the warrior, pyrotechnician, and ranger. Warriors enter a rampage
state after slaying a monster, which powers them up to the point of slaying almost anything in one
hit. Further kills extend the rampage, but it ends after three seconds without a kill.

<!-- TODO radar scanner video clip  -->

Pyrotechnicians have a blaster with area-of-effect damage, allowing them to handle crowds without
the need for the rampage. Rangers can attack from afar and deal piercing damage, and have improved
mobility. Their scanner tool further allows them to provide support.

### Monsters

Players on the monster side earn XP points by killing defenders and destroying their structures.
They can spend their XP on undead upgrades, which have three branching paths to select: bruiser,
tank, or infiltrator. They can also periodically spawn as special monster types. More, better
special monsters become available as the game progresses, so players who join the monsters late
aren't left behind and don't have to worry about upgrading their undead.

## Technical Info

<figure>
	<a href="https://youtu.be/N9TSqAqptgw" target="blank">
		<img height="78" width="150" src="/assets/images/laststand3_thumb.png" />
	</a>
	<figcaption>NPCs pathing through a player-built maze (video)</figcaption>
</figure>

NPC pathfinding efficiently utilizes A* on a separate thread. The A* grid is generated procedurally
from the map, then adapts dynamically to the defenders' structures as they are placed and
destroyed. The procedural grid is cached and only needs to be generated once for each game map.

API services implemented in ASP.NET Core provide authentication, inventory management, class
selection, a list of ongoing games, and profile information. Ongoing games are stored in a SQLite
database, while all other data is stored in a MariaDB database.

The game itself uses Godot's built-in ENet fork for communication, including for positional voice
chat. Authentication is enforced.
