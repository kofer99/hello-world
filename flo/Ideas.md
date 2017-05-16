## This is my idea, how our engine would be of good use xD
Examples in Java
### How it would be used
Game.java is the only class that communicates with the Engine directly. <br>
Everything else is in components and get`s handled by the Engine.

```java

public class Game {
	
	public Game(){}

	public ArrayList<Entity> init(){
		ArrayList<Entity> entities = new ArrayList<Entity>();
		
		Entity player = new Entity();
		player.add(new Renderable());
		player.add(new Controller());
		entities.add(player);

		Entity tree = new Enity();
		tree.add(new Renderable());
		entities.add(tree);

		Entity enemy = new Entity();
		enemy.add(new AI());
		entities.add(enemy);

		return entities;
	}
}

```
## Entity/Component architecture like Unity
I would do the engine like ~Unity using a Entity-Component-System architecture. <br>
We would have to write different Systems, that recieve their data
from the components and process it. They don`t know anything about
the engine and other compontents, except an event que.
This event que is passed threw every system, to perform inter 
system communication (e.g. play sound, move?! *to be discussed*). <br>

### Entity
Is created and holds all the Components added to this entity, until
it gets passed to the systems. Then it only holds hashes of the components,
witch have moved into the systems.

### Component
Holds systemspecific data and a hash of it self, for identification.

### System
Holds a list of components associated with this system.<br>
Creates the hashes and transforms the entities. Is responsible for
inserting and deleting.

## Events
Every system can have events associated with it.

### Event-que
Probably a java map of all events, read/write for all systems.<br>
Gets cleand after every loop.


