## This is my idea, how our engine would be of good use xD

### How it would be used
Game.java is the only class that communicates with the Engine directly. <br>
Everything else is in components and get`s handled by the Engine.

```java

public class Game {
	
	public Game(){}

	public ArrayList<Entity> init(){
		
		Entity player = new Entity();
		player.add(new Renderable());
		player.add(new Controller());

		Entity tree = new Enity();
		tree.add(new Renderable());

		Entity enemy = new Entity();
		enemy.add(new Controler(){
			@Override
			public atIdle(){
				moveInCircle(5.0f);
			}

			@Override
			public atPlayerInSight(){
				shoot();
			}

			private void shoot(){
				Entity bullet = new Entity(new Fly(10.5f));
				spwan(bullet);
			}
		});

		return null;
	}
}

```


### Entity/Component architecture like Unity


