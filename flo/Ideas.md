## This is my idea, how our engine would be of good use xD

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
I would do the engine like Unity using a Entity-Component-System architecture. <br>
We would have to write different Systems, that recieve their data
from the components and process it. They don`t know anything about
the engine and other compontents, except a event que.
This event que is passed threw every system, to perform inter 
system communication (e.g. play sound, move?! *to be discussed*). <br>

##


