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

