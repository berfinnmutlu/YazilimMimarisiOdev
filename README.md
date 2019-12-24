### YAZILIM MİMARİSİ ÖDEV

## Decorator Design Pattern

Decorator tasarım deseni , Structural grubuna ait bir tasarım desenidir. Bir nesneye dinamik olarak yeni sorumlulukların eklenmesi ve hatta var olanların çıkartılması amacıyla kullanılır. Bu tasarım deseni , nesneyi kendisinden türeyen alt sınıflar ile genişletmek yerine kullanılabilen alternatif bir yaklaşım olarak düşünülebilir.Bu desenin örnek UML diyagramı şu şekildedir;

![Image of Class](https://github.com/berfinnmutlu/YazilimMimarisiOdev/blob/master/decorator_uml.png)

Component, dinamik olarak operasyonlar eklenebilecek yapının uygulayacağı arayüz veya abstract nesnedir. ConcreteComponent ise bu yapıyı uygulayan, operasyon eklenecek gerçek nesnelerdir. Decorator nesnesi Component nesnesini uygular ve içinde Component tipinden bir referans barındırır. ConcreteDecorator nesneleri ekleyeceğimiz operasyonların olacağı nesnelerdir ve Decorator arayüzünü uygular.

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

Memento tasarım deseni Behavior grubununa ait, bir nesnenin tamamının veya bazı özelliklerinin tutularak sonradan tekrar elde edilmesini yöneten tasarım desenidir.Memento tasarım deseni nesnenin bir halinin kopyasını alıp sonra bu kopyanın tekrar elde edilmesini sağlar. Genelde geri al işlemi için kullanılır. Bu desenin örnek UML diyagramı şu şekildedir;

![Image of Class](https://github.com/berfinnmutlu/YazilimMimarisiOdev/blob/master/memento_uml.png)

Originator,tamamının veya bazı özelliklerinin kopyasının tutulacağı nesnedir. Memento nesnesini oluşturan ve geri yüklenmesinden sorumludur.Memento ,originator nesnesinin saklanacak özelliklerinin tanımlı olduğu nesne. Caretaker,saklanacak olan memento nesnesinin referansını içinde barındıran nesnedir.

![Image of Class](https://github.com/berfinnmutlu/YazilimMimarisiOdev/blob/master/memento_pattern_uml-diagram.png)

Originator, Memento nesnelerinde durum oluşturur ve saklar. Caretaker nesnesi, Memento'dan nesne durumunu geri yüklemekle sorumludur.

```java
public class Originator {
   private String state;

   public void setState(String state){
      this.state = state;
   }

   public String getState(){
      return state;
   }

   public Memento saveStateToMemento(){
      return new Memento(state);
   }

   public void getStateFromMemento(Memento memento){
      state = memento.getState();
   }
}
```

Caretaker nesnesi, Memento'dan nesne durumunu geri yüklemekle sorumludur.

```java
import java.util.ArrayList;
import java.util.List;

public class CareTaker {
   private List<Memento> mementoList = new ArrayList<Memento>();

   public void add(Memento state){
      mementoList.add(state);
   }

   public Memento get(int index){
      return mementoList.get(index);
   }
}
```
