Çok işlemcili mimariler konusunda araştırmalarım doğrultusunda hazırladığım bu araştırmada, çoklu işlemci ne olduğu ve hangi türlerden oluştuğu konularına değineceğim. Daha sonrasında ise ikinci konu başlığı altında çok işlemcili mimarilerin hangi şekilde sınıflandırıldığı durumuna kısaca giriş yapacak ve sınıflandırma ile ilgili araştırmalarım doğrultusunda bilgiler vereceğim. Bu sınıflandırma mimari ve donanım türleri olmak üzere iki başlık altında olacak. Bu bilgilendirmeleri yaparken,  çok işlemcili mimarileri konusuna detaylı bir şekilde değineceğim.

### 1.	Çok İşlemcili Mimariler
Çok işlemcili mimariler oluşturulurken amaç bilgisayar için performansı ve erişilebilirliği arttırabilmektir. Mantık olarak bilgisayar sistemi içerisinde birden fazla CPU kullanılması ile oluşturulur. Performans artışını sağlayabilmek için işlem sırasında bekleyen işlemler tıpkı görev dağılımı yapar gibi farklı birimlere dağıtılır. Bu işlemleri gerçekleştiren CPU’lar aynı ana bellek ve çevre birimlerini paylaşır. Bu CPU’lar için farklı cache bellekler kullanılır. Sonuçta birden fazla işlemci işin farklı kısımlarını ele almış ve gerçekleştirmiş olur.

### 2.	Çoklu İşlemci İşletim Sistemi Türleri 
İşletim sistemlerinde çoklu işlemcilerin farklı kullanım türleri vardır. Bu başlık altında işlemcilerle işletim sistemi ilişkisini inceleyeceğiz.

#### 2.1	Simetrik Çoklu İşlem (SMP)

![](https://user-images.githubusercontent.com/46966075/86813949-7093ac00-c089-11ea-8e9a-100fb74a1ff2.png)

- Şekil-1 Simetrik Çoklu İşlem [Kaynak 7’ den yararlanılarak tekrardan oluşturulmuştur.]

 Simetrik çoklu işlem (SMP), birden fazla özdeş özellikli işlemcinin aynı anda belleğe erişebilmesi amaçlanarak oluşturulmuş mimarilerdir. Böylece iş bölümü gerçekleştirilerek performans artışı amaçlanmaktadır. Simetrik mimari gereği tüm CPU’lar eşit muamele görür ve bu doğrultuda işlem yapar. Bellekte yer alan işletim sistemi kopyasını her işlemci bir engel olmaksızın kullanabilir. 
 
Bu sistem oluşturulurken elbette bazı sorunlarla karşılaşılmıştır. Bunlardan en büyüğü ve çözüm gerektireni işlemcilerin aynı anda erişim ve değişim yapma istekleridir. Böyle bir durumun ortaya çıkmasında sistem kendini devam ettiremez hale gelir. Bu soruna çözüm olarak da sistem çağrılarına kilit koyma yöntemi geliştirilmiştir. Bu çözüm mantıken oda kapısı kilitliyse birisi var demektir. İçerdeki kişi çıkınca odayı sen kullanabilirsin şeklindedir. İlk başta işlemcilerin aynı anda çalışmasını engelleyecek bir durummuş gibi görünse de organizasyon mantığıyla bu durumun da üstesinden gelinebilir. 
#### 2.2	Asimetrik Çoklu İşlem (AMP)
![](https://user-images.githubusercontent.com/46966075/86813940-6ec9e880-c089-11ea-9b90-9631b0f72a82.png)
- Şekil-2 Asimetrik Çoklu İşlem [Kaynak 6’ dan alınmıştır.]

Asimetrik çoklu işlem (AMP), simetrik çoklu işlemden farklı olarak CPU’ların eşit imkanlar dahilinde çalışmadığı mimari türüdür. CPU’nun işlem yapabilmesi donanımsal veya sistem bazında izin gerektirir. Bazı veya tüm çevre birimlerinin belli CPU’lara bağlanmasından dolayı asimetrik bir çalışma olşur.

#### 2.3	Birincil-İkincil Çoklu İşlemciler (MSMP)

![](https://user-images.githubusercontent.com/46966075/86813943-6ffb1580-c089-11ea-87ab-d3e0d0f6c398.png)
- Şekil-3 Birincil- İkincil Çoklu İşlem [Kaynak 9’ dan alınmıştır.]

Adından da anlaşılabileceği gibi bu sistemin çalışma mantığı birincil ve ikincil işlemci paylaşımına dayanır. Bu mantığa göre işletim sistemi sadece bir işlemci üzerinde çalışır. Bu çalışma alanına birincil işlemci denir. Bu işlemcinin yapacağı işlemler ise diğer işlemciler arasında pay edilir. Pay edilen bu işlemciler ise ikincil işlemcilerdir. Meşguliyet prensibiyle çalışan bu sistemlerde bir işlemci meşgul haldeyse işlem boş olan işlemciye aktarılır. 

### 3.	Çoklu İşlemci Donanım Türleri
Bu bölümde çoklu işlemcilerin donanım yönünden oluşturulmasını ele alacağız.

#### 3.1 UMA (Uniform Memory Access) Çok İşlemciler
 ![](https://user-images.githubusercontent.com/46966075/86813945-6ffb1580-c089-11ea-9f35-ccf682bf991c.png)
- Şekil- 4 Uniform Memory Access [Kaynak 11’den alınmıştır.]

UMA çoklu işlemcilerinin çalışması durumunda her işlemcinin belleğe erişiminde kelime yazması veya okuması esnasında geçen süre aynıdır. Yukarıdaki şekilden de göründüğü gibi mimaride ortak bir veri yolu vardır. Bu veri yolu ile belleğe ulaşım sağlanır. Çalışma mantığı olarak bu mimari de doluluk- boşluk prensibiyle çalışır. İşletim sistemi mimarisinde anlattığımız gibi bu bekleme durumu gecikmeye yol açabilir. Bu soruna çözüm olarak önbellekleme yöntemi geliştirilmiştir. Bu çözümde önbellekler okunabilir veya yazılabilir olarak ayrılmıştır. Böylece bu verinin korunması ve işlemlerden etkilenmemesi amaçlanmış ve sağlanmıştır.


#### 3.2 NUMA (Nonuniform Memory Access) Çok İşlemcileri
Bir önceki başlıkta incelediğimiz UMA’nın yetersiz kaldığı ve ihtiyacımızı karşılayamadığı durumlarda NUMA’ kullanılır. UMA’nın tek veri yolu üzerinden işlem yapıyor olması ve sınırlandırılmış işlemci sayısına sahip olması bunun yanında bu işlemcilerin pahalılığından dolayı NUMA kullanılmaktadır. Sistem yüz ve üzeri işlemci sayısına sahip olabilir.

![](https://user-images.githubusercontent.com/46966075/86813948-7093ac00-c089-11ea-8d9e-a6dcdb852a78.png)
- Şekil-5 Nonuniform Memory Access [Kaynak 10’dan alınmıştır.]

Üstte yer alan şekilden de görünebildiği gibi sistem tek adres alanı ile paylaşımlı bellek sunar ve bu durum tek işletim sitemi üzerindedir. Bellek fiziksel olarak memory instruction bufferlara paylaştırılır.

### Kaynaklar

[1] https://tr.scribd.com/document/101106/IsletimSistemleri

[2] https://seninfikrinsenindunyan.wordpress.com/isletim-sistemleri

[3] https://e-bergi.com/y/coklu-islemciler

[4] https://www.slideshare.net/arpanbaishya/multiprocessor-architecture 

[5] http://www.eng.auburn.edu/~agrawvd/COURSE/E6200_06/STUDENT_TALKS/Multiprocessor_YChen.ppt 

[6] http://www.wikizero.org/index.php?q=aHR0cHM6Ly9lbi53aWtpcGVkaWEub3JnL3dpa2kvQXN5bW1ldHJpY19tdWx0aXByb2Nlc3Npbmc 

[7] http://www.wikizero.org/index.php?q=aHR0cHM6Ly9lbi53aWtpcGVkaWEub3JnL3dpa2kvU3ltbWV0cmljX211bHRpcHJvY2Vzc2luZw 

[8] http://www.wikizero.org/index.php?q=aHR0cHM6Ly9lbi53aWtpcGVkaWEub3JnL3dpa2kvTm9uLXVuaWZvcm1fbWVtb3J5X2FjY2Vzcw

[9] https://slideplayer.com/slide/777643/

[10] http://www.new-npac.org/projects/cdroms/cewes-1999-06-vol1/nhse/hpccsurvey/architecture/slide9.html


[11] https://www.slideshare.net/parbhatverma/aca-2
