**1.** **Bölüm: Monolitk ve Mikroservis**

**1.1 Monolitik ve Mikroservis Mimarisi Kavramları**

**Monolitik Mimari**: Uygulamanın tüm bileşenlerinin tek bir yapı içerisinde geliştirildiği mimaridir. Kullanıcı arayüzü, iş mantığı ve veri işlemleri aynı uygulama içerisinde bulunur.

**Mikroservis Mimarisi**: Uygulamanın birbirinden bağımsız, belirli görevleri yerine getiren küçük servislere ayrıldığı mimaridir. Her servis ayrı olarak geliştirilebilir, çalıştırılabilir ve güncellenebilir.

**1.2 Monolitik Mimaride Yatay ve Dikey Genişleme**

**Dikey Genişleme (Vertical Scaling)**: Uygulamanın çalıştığı sunucunun işlemci (CPU), RAM ve depolama gibi donanım kaynaklarının artırılmasıdır.

**Yatay Genişleme (Horizontal Scaling)**: Uygulamanın birden fazla sunucuda çalıştırılarak işlem yükünün sunucular arasında dağıtılmasıdır.

Monolitik mimaride her iki yöntem de kullanılabilir. Ancak yatay genişlemede uygulamanın tamamı yeni sunucularda çalıştırılır.

**1.3 Mikroservis ve Monolitik Mimari Arasındaki Farklar**

| Monolitik Mimari                                                     | Mikroservis Mimarisi                             |
| -------------------------------------------------------------------- | ------------------------------------------------ |
| Tek bir uygulamadan oluşur.                                          | Birden fazla bağımsız servisten oluşur.          |
| Geliştirilmesi ve yönetilmesi daha kolaydır.                         | Yönetimi ve koordinasyonu daha karmaşıktır.      |
| Bir değişiklik tüm uygulamanın yeniden dağıtılmasını gerektirebilir. | Servisler bağımsız güncellenebilir.              |
| Ölçeklendirme genellikle tüm uygulama üzerinden yapılır.             | İhtiyaç duyulan servis ayrı ölçeklendirilebilir. |
| Küçük ve orta ölçekli projeler için uygundur.                        | Büyük ve karmaşık projeler için uygundur.        |

**2\. Bölüm: Hayali Proje**

**2.1 Projenin Amacı, Kapsamı ve Çözümlediği Problem**

**Projenin Amacı**: OBİS (Öğrenci Bilgi Sistemi), öğrencilerin akademik bilgilerine kolayca erişebilmesini sağlayan bir sistemdir.

**Projenin Kapsamı**: Öğrenci bilgileri, dersler, notlar ve devamsızlık işlemlerini kapsar.

**Çözümlediği Problem**: Öğrencilerin akademik bilgilerine farklı kaynaklardan ulaşma zorunluluğunu ortadan kaldırarak tüm bilgileri tek bir platformda toplar.

**2.2 Hedef Kitle**

OBİS'in hedef kitlesini öğrenciler, öğretmenler ve okul yöneticileri oluşturmaktadır. Sistem, bu kullanıcıların akademik bilgilere kolayca erişmesini ve gerekli işlemleri gerçekleştirmesini sağlar.

**2.3 Zaman Planı**

| Aşama                 | Süre        |
| --------------------- | ----------- |
| Analiz ve planlama    | 1 hafta     |
| Tasarım               | 1 hafta     |
| Yazılım Geliştirme    | 3 hafta     |
| Test ve hata düzeltme | 1 hafta     |
| Toplam                | **6 hafta** |

**3\. Gereksinim Analizi**

**3.1 MoSCoW Yöntemine Göre Gereksinimler**

**Must Have (Olmazsa Olmaz)**

1. Kullanıcı girişi yapılabilmelidir.
2. Öğrenci kayıtları oluşturulabilmelidir.
3. Öğrenci bilgileri görüntülenebilmelidir.
4. Öğrenci bilgileri güncellenebilmelidir.
5. Öğrenci kayıtları silinebilmelidir.
6. Dersler sisteme eklenebilmelidir.
7. Öğrencilerin notları görüntülenebilmelidir.
8. Öğretmenler not girebilmelidir.
9. Devamsızlık bilgileri görüntülenebilmelidir.
10. Kullanıcıların yetkileri kontrol edilmelidir.

**Should Have (Olması Gereken)**

11. Öğrenciler ders programlarını görüntüleyebilmelidir.
12. Öğrenciler sınav sonuçlarını görüntüleyebilmelidir.
13. Öğretmenler devamsızlık girebilmelidir.
14. Kullanıcılar şifrelerini değiştirebilmelidir.
15. Yöneticiler kullanıcı hesaplarını yönetebilmelidir.

**Could Have (Olabilir)**

16. Sistem duyuru paylaşabilmelidir.
17. Öğrenciler transkript görüntüleyebilmelidir.
18. Sistem e-posta bildirimi gönderebilmelidir.
19. Kullanıcılar profil fotoğrafı ekleyebilmelidir.
20. Öğrenciler akademik takvimi görüntüleyebilmelidir.

**Won't Have (Bu Sürümde Olmayacak)**

21. Mobil uygulama geliştirilmeyecektir.
22. Online ödeme sistemi bulunmayacaktır.

**3.2 Türlerine Göre Gereksinim Sınıflandırması**

**1\. İş Gereksinimleri**

- Öğrenci bilgilerinin dijital ortamda yönetilmesi.
- Akademik işlemlerin tek bir sistem üzerinden yürütülmesi.
- Okul yönetiminin iş yükünün azaltılması.

**2\. Kullanıcı Odaklı Gereksinimler**

- Öğrenciler notlarını görüntüleyebilmelidir.
- Öğretmenler not ve devamsızlık girebilmelidir.
- Yöneticiler öğrenci ve öğretmen bilgilerini yönetebilmelidir.

**3\. Fonksiyonel Gereksinimler**

- Kullanıcı girişi yapılabilmelidir.
- Öğrenci kayıtları eklenebilmeli, silinebilmeli ve güncellenebilmelidir.
- Ders ve not bilgileri yönetilebilmelidir.
- Devamsızlık bilgileri kaydedilebilmelidir.

**4\. Fonksiyonel Olmayan Gereksinimler**

- Sistem kolay kullanılabilir olmalıdır.
- Kullanıcı bilgileri güvenli şekilde saklanmalıdır.
- Sistem hızlı yanıt vermelidir.
- Sistem farklı cihazlardan erişilebilir olmalıdır.

**3.3 Kullanım Senaryoları**

**1\. Kullanıcı Girişi**

- Aktör: Öğrenci / Öğretmen / Yönetici
- Ön Koşul: Kullanıcının sisteme kayıtlı olması.
- Senaryo:
  1. Kullanıcı giriş sayfasını açar.
  2. Kullanıcı adı ve şifresini girer.
  3. Sistem bilgileri kontrol eder.
  4. Bilgiler doğruysa kullanıcı sisteme giriş yapar.
- Sonuç: Kullanıcı sisteme erişir.

**2\. Not Görüntüleme**

- Aktör: Öğrenci
- Ön Koşul: Öğrencinin sisteme giriş yapmış olması.
- Senaryo:
  1. Öğrenci notlar sayfasını açar.
  2. Sistem öğrencinin notlarını getirir.
  3. Notlar ekranda görüntülenir.
- Sonuç: Öğrenci kendi notlarını görüntüler.

**3\. Ders Ekleme**

- Aktör: Yönetici
- Ön Koşul: Yöneticinin sisteme giriş yapmış olması.
- Senaryo:
  1. Yönetici dersler sayfasını açar.
  2. Yeni ders ekleme seçeneğine tıklar.
  3. Ders bilgilerini girer.
  4. Kaydet butonuna tıklar.
  5. Sistem dersi kaydeder.
- Sonuç: Yeni ders sisteme eklenir.

**4\. Kaynakça**

1\. <https://learn.microsoft.com/en-us/azure/architecture/guide/architecture-styles/microservices>

2\. <https://www.ibm.com/think/topics/monolithic-architecture>

3\. <https://www.ibm.com/think/topics/monolithic-vs-microservices>

<!-- word2md kullanıldı -->