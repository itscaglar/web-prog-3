# Konu
Nesne Temelli Programlama Prensipleri

## Araştırma
**Class, Object ve Constructor**

* **Kavram:** Sınıf bir taslaktır; nesne ise bu taslaktan üretilmiş gerçek varlıktır. Constructor, nesne ilk oluşturulduğunda çalışan metottur.
* **Çözdüğü Problem:** Aynı özellikleri taşıyan verileri defalarca baştan yazmayı engeller; veri grupları için standart bir şablon oluşturur.
* **Günlük Hayat Örneği:** Bir evin mimari planı "Class", o plana göre inşa edilmiş sokağınızdaki gerçek ev "Object", evin temeli atılırken kapı numarasının belirlenmesi "Constructor" işlemidir.


```cs
class Ev {
    public string Renk;
    public Ev (string baslangicRengi) {
        Renk = baslangicRengi;
    }
}

Ev evim = new Ev("Kırmızı"); 
```

**Encapsulation ve Access Modifiers**

* **Kavram:** Sınıf içindeki verilerin dış dünyadan gizlenmesi ve sadece izin verilen metotlar aracılığıyla kontrollü şekilde değiştirilmesidir. Erişim belirleyiciler bu kontrolü sağlar.

* * **public:** herkese açık
* * **private:** sadece sınıf içine açık
* * **protected:** sınıf ve miras alanlara açık 

* **Çözdüğü Problem:** Verilerin yetkisiz veya hatalı değiştirilmesini önleyerek sistemin kararlılığını korur.

* **Günlük Hayat Örneği:** Banka hesabınızdaki bakiye doğrudan elle değiştirilemez; ancak para yatırma veya çekme işlemi ile kurallar dahilinde güncellenebilir.

```csharp
class BankaHesabi {
    private decimal bakiye = 0;
    public void ParaYatir(decimal miktar) {
        if (miktar > 0) bakiye += miktar;
    }
}
```

**Inheritance ve Polymorphism**

* **Kavram:** Kalıtım, bir sınıfın başka bir sınıfın özelliklerini devralmasıdır. Çok biçimlilik ise aynı isimdeki bir işlemin, farklı nesnelerde farklı şekillerde çalışabilmesidir.

* **Çözdüğü Problem:** Kalıtım kod tekrarını önler. Çok biçimlilik ise sisteme yeni nesneler eklendiğinde mevcut kodları değiştirmeden esneklik sağlar.

* **Günlük Hayat Örneği:** Tüm "Taşıtlar" hareket eder. Ancak bir "Uçak" nesnesine hareket et dendiğinde uçar, "Otomobil" nesnesine hareket et dendiğinde karada ilerler.

```csharp
class Tasit {
    public virtual void HareketEt() {
        Console.WriteLine("Taşıt ilerliyor.");
    }
}
class Ucak : Tasit {
    public override void HareketEt() {
        Console.WriteLine("Uçak uçuyor.");
    }
}
```

**Abstraction, Abstract Class ve Interface**

* **Kavram:** Sistemin karmaşık iç işleyişini gizleyip kullanıcıya sadece ne yapabildiğini göstermektir. **Abstract Class**, ortak özellikleri barındıran ancak tek başına nesne üretilemeyen temel sınıflardır. **Interface** ise bir sınıfın hangi metotları içermesi gerektiğini belirten yetenek sözleşmeleridir.

* **Çözdüğü Problem:** Büyük projelerde "nelerin yapılması gerektiğini" belirler, "nasıl yapılacağını" alt sınıflara bırakarak takım çalışmasını ve modülerliği kolaylaştırır.

* **Günlük Hayat Örneği:** Kahve makinesinin sadece düğmesine basarsınız. Makinenin suyu nasıl ısıttığı veya basıncı nasıl ayarladığı sizi ilgilendirmez.

```csharp
interface ICalisabilir {
    void Calis();
}
class KahveMakinesi : ICalisabilir {
    public void Calis() { /* Suyu ısıt */ }
}
```

**Composition ve Inheritance Farkı**

* **Kavram:** Kalıtım (Is-a) ilişkisi kurarken, Composition (Has-a) ilişkisi kurarak nesneleri birbirinin içinde kullanmayı ifade eder.

* **Çözdüğü Problem:** Kalıtım zinciri çok uzadığında sistem hantallaşır. Composition, parçaları birleştirerek daha esnek yapılar kurmayı sağlar.

* **Günlük Hayat Örneği:** Otomobil bir Taşıttır. Ancak Otomobil bir Motora "sahiptir".

```csharp
class Motor { 
    public void Calistir() {}
}

class Otomobil {
    private Motor motor = new Motor();
    public void GazaBas() { motor.Calistir(); }
}
```

## Sektörde Kullanımı

Yazılım sektöründe OOP, özellikle büyük ekiplerin aynı proje üzerinde karmaşa yaşamadan çalışabilmesi için standart bir mimari olarak kullanılır. Spagetti koda engel olduğu için kurumsal projelerde endüstri standardıdır. Sektördeki başlıca kullanım alanları ve sağladığı faydalar şunlardır:

* **Modüler Geliştirme ve Takım Çalışması:** Sektörde bir projeyi tek kişi yazmaz. OOP sayesinde proje "Sipariş", "Kullanıcı", "Ödeme" gibi nesnelere bölünür. Bir yazılımcı sadece `OdemeSistemi` sınıfı üzerinde çalışırken, diğer yazılımcı `KullaniciYonetimi` sınıfını geliştirebilir. Sınıflar birbirinden bağımsız olduğu için kimse birbirinin kodunu bozmaz.
* **Code Reusability:** Şirketler aynı kodları tekrar tekrar yazmak istemez. Kalıtım prensibi sayesinde, daha önce yazılmış güvenli bir "Musteri" sınıfı, yeni bir projede "VIP_Musteri" olarak genişletilip doğrudan kullanılabilir. Bu da geliştirme süresini ve maliyetini ciddi oranda düşürür.
* **Maintainability:** Milyonlarca satırlık bir e-ticaret uygulamasında "Sepete Ekle" butonunda bir hata çıktığında, yazılımcılar tüm kodu okumak yerine sadece `Sepet` sınıfına giderler. Hata izolasyonu kolaydır.
* **Game Development:** Unity veya Unreal Engine gibi sektör standartı oyun motorları tamamen OOP üzerine kuruludur. Oyundaki her bir düşman, karakter, silah veya ağaç birer Object olarak tasarlanır ve her nesnenin kendi davranışları vardır.
* **Frameworks:** Sektörde sıkça kullanılan .NET Core, Spring Boot, Laravel ve Django gibi büyük web framework'leri OOP mimarisi ile inşa edilmiştir. Bu araçları kullanabilmek için sınıfları, interfaceleri ve nesneleri anlamak zorunludur.