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


### Entity/Component architecture like Unity


