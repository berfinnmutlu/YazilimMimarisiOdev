### YAZILIM MİMARİSİ ÖDEV

## Decorator Design Pattern

Decorator tasarım deseni , Structural grubuna ait bir tasarım desenidir. Bir nesneye dinamik olarak yeni sorumlulukların eklenmesi ve hatta var olanların çıkartılması amacıyla kullanılır. Bu tasarım deseni , nesneyi kendisinden türeyen alt sınıflar ile genişletmek yerine kullanılabilen alternatif bir yaklaşım olarak düşünülebilir.Bu desenin örnek UML diyagramı şu şekildedir;










![Image of Class](https://github.com/berfinnmutlu/YazilimMimarisiOdev/blob/master/class.png)

Yukarıdaki class diagramının örneğinde, bir araba nesnesine dekorasyon ile yeni özellikler kazandırılacaktır.



Decorator - Bileşen değişkeni alt dekoratör sınıfları tarafından erişilebilir olmalıdır, bu nedenle bu değişken korumalı olmalı.

```java
package com.journaldev.design.decorator;

public class CarDecorator implements Car {

	protected Car car;
	
	public CarDecorator(Car c){
		this.car=c;
	}
	
	@Override
	public void assemble() {
		this.car.assemble();
	}
}
```

Concrete Decorators - Temel dekoratör işlevini genişletmek amacıyla LuxuryCar ve SportsCar olmak üzere somut dekoratör sınıflar oluştururuz.

```java
package com.journaldev.design.decorator;

public class SportsCar extends CarDecorator {

	public SportsCar(Car c) {
		super(c);
	}

	@Override
	public void assemble(){
		super.assemble();
		System.out.print(" Adding features of Sports Car.");
	}
}
```


```java
package com.journaldev.design.decorator;

public class LuxuryCar extends CarDecorator {

	public LuxuryCar(Car c) {
		super(c);
	}
	
	@Override
	public void assemble(){
		super.assemble();
		System.out.print(" Adding features of Luxury Car.");
	}
}
```

## Memento Design Pattern






















