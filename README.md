### YAZILIM MİMARİSİ ÖDEV

## Decorator Design Pattern

Decorator tasarım deseni , Structural grubuna ait bir tasarım desenidir. Bir nesneye dinamik olarak yeni sorumlulukların eklenmesi ve hatta var olanların çıkartılması amacıyla kullanılır. Bu tasarım deseni , nesneyi kendisinden türeyen alt sınıflar ile genişletmek yerine kullanılabilen alternatif bir yaklaşım olarak düşünülebilir.
![Image of Class](https://github.com/berfinnmutlu/YazilimMimarisiOdev/blob/master/class.png)

Yukarıdaki class diagramının örneğinde, bir araba nesnesine dekorasyon ile yeni özellikler kazandırılacaktır.



1.Component Interface – Uygulanacak yöntemleri tanımlayan arayüz veya soyut sınıf. Bu sınıfımız Car() sınıfı.
```java

package com.journaldev.design.decorator;

public interface Car {

	public void assemble();
}
```

2.Component Implementation – Bileşen arayüzün temel uygulamasıdır. Bileşen uygulamamız olarak BasicCar() sınıfını oluşturduk. 
```java

package com.journaldev.design.decorator;

public class BasicCar implements Car {

	@Override
	public void assemble() {
		System.out.print("Basic Car.");
	}

}

```

3.Decorator - Bileşen değişkeni alt dekoratör sınıfları tarafından erişilebilir olmalıdır, bu nedenle bu değişken korumalı olmalı.
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






















