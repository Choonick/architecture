# factory method
### 왜 써야하는가?
- 클래스간의 결합도를 낮추기 위해 
 	- 결합도(변경점이 생겼을때 얼마나 다른 클래스에 영향을 주는가)
- 객체 생성하는 부분을 팩토리에서 하지않고 각가의 서브 클래스에 위임한다. 

예시) 로봇

### Robot

```
package pattern.factory;

public abstract class Robot {
	public abstract String getName();
}
```

```
package pattern.factory;

public class SuperRobot extends Robot {
	@Override
	public String getName() {
		return "SuperRobot";
	}
}
```

```
package pattern.factory;

public class PowerRobot extends Robot {
	@Override
	public String getName() {
		return "PowerRobot";
	}
}
```

### RobotFactory

```
package pattern.factory;

public abstract class RobotFactory {
	abstract Robot createRobot(String name);
}
```

```
package pattern.factory;

public class SuperRobotFactory extends RobotFactory {
	@Override
	Robot createRobot(String name) {
		switch( name ){
			case "super": return new SuperRobot();
			case "power": return new PowerRobot();
		}
		return null;
	}
}
```

```
package pattern.factory;

public class ModifiedSuperRobotFactory extends RobotFactory {
	@Override
	Robot createRobot(String name) {
		try {
			Class<?> cls = Class.forName(name);
			Object obj = cls.newInstance();
			return (Robot)obj;
		} catch (Exception e) {
			return null;
		}
	}
}
```

### main
```
package pattern.factory;

public class FactoryMain {
	public static void main(String[] args) {

		RobotFactory rf = new SuperRobotFactory();
		Robot r = rf.createRobot("super");
		Robot r2 = rf.createRobot("power");

		System.out.println(r.getName());
		System.out.println(r2.getName());

		RobotFactory mrf = new ModifiedSuperRobotFactory();
		Robot r3 =  mrf.createRobot("pattern.factory.SuperRobot");
		Robot r4 =  mrf.createRobot("pattern.factory.PowerRobot");

		System.out.println(r3.getName());
		System.out.println(r4.getName());
	}
}
```