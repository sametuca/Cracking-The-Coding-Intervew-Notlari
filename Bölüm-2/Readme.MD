# Cracking The Coding Interview Notları - 1
--------------------------------------------------
## İçindekiler
* [Çok Başarılı Bir Öğrenci Neden Elenir?](#cok-basarili-bir-ogrenci-neden-elenir)
* [Üst Düzey Teknoloji Şirketlerinin Dikkat Ettiği Noktalar](#ust-duzey-teknoloji-sirketlerinin-dikkat-ettigi-noktalar)
* [Bu Tarz Durumlarda Ne Yapmak Gerekir?](#bu-tarz-durumlarda-ne-yapmak-gerekir)
* [Nasıl Değerlendirilirsiniz?](#nasıl-değerlendirilirsiniz)
* [Amazon Mülakatı](#amazon-mulakati)
* [Facebook Mülakatı](#facebook-mulakati)
* [Google Mülakatı](#google-mulakati)
* [Microsoft Mülakatı](#microsoft-mulakati)
* [İyi Bir Özgeçmiş Hazırlama](#iyi-bir-cv-hazirlama)


### Algoritma Analizi

Algoritma analizi ve büyük O (O) gösterimi hakkında konuşuluyor. İlk olarak, büyük O gösterimi bir algoritmanın performansını ve çalışma zamanını ifade etmek için kullanılan bir notasyondur. O (1), sabit bir çalışma zamanını ifade ederken, O (N), girdi boyutu N'e bağlı olarak lineer bir şekilde artan bir çalışma zamanını ifade eder.

Metinde, O (N) kodunun belirli girdiler için O (1) koddan daha hızlı çalışabileceği ifade ediliyor. Bunun nedeni, büyük O gösteriminin yalnızca artış hızını açıklamasıdır. Örneğin, O (2N) olarak tanımlanan bir algoritma aslında O (N) olarak kabul edilebilir, çünkü sabit faktörler veya katsayılar genellikle analizde göz ardı edilir.

Metinde, insanların genellikle iki (iç içe olmayan) döngüye sahip kodları O (2N) olarak gördüklerinden bahsediliyor, ancak bu yanlış bir anlayıştır. Bu durumda, kod aslında O (N) olarak değerlendirilebilir.

Verilen kod örneğinde, bir dizi içindeki minimum ve maksimum değerleri bulan bir algoritma sunuluyor. İlk olarak, minimum değeri bulmak için bir döngü kullanılır ve ardından maksimum değeri bulmak için aynı dizi üzerinde başka bir döngü kullanılır. Bu kod, O (N) zaman karmaşıklığına sahiptir çünkü her bir dizi elemanı için bir işlem yapılır.

Özetle, metinde algoritma analizi, büyük O gösterimi ve kod örneği hakkında açıklamalar bulunmaktadır. Metindeki örnekteki kod, minimum ve maksimum değerleri bulmak için O (N) zaman karmaşıklığına sahip bir algoritmayı temsil etmektedir.


```javascript Code1
int min » Integer.MAX_VALUE; 
int max = Integer.MIN_VALUE;
for (int x ; array) { 
if (x < min) min = x;
if (x > max) max = x; 
} 
```

```javascript Code2
int min = Integer.MAX_VALUE
int max = Integer.MIN_VALUE;
for (int x : array) { 
if (x < min) min = x; 
>
for (int x : array) { 
if (x > max) max = x; 
>
```

lk çözümde bir adet for döngüsü kullanılırken, ikinci çözümde iki ayrı for döngüsü kullanılıyor. Ancak, her bir for döngüsü için ilk çözümde iki satır kod kullanılırken ikinci çözümde bir satır kod kullanılıyor.

Eğer talimat sayısını saymaya başlarsanız, o zaman derinlere inip çarpmanın toplamadan daha fazla talimat gerektirdiği, derleyicinin bir şeyi nasıl optimize edeceği ve diğer tüm ayrıntıları hesaba katmanız gerekecektir. Bu oldukça karmaşık bir süreç olur ve büyük O gösterimi bu detayları hesaba katmadan sadece çalışma süresinin nasıl ölçeklendiğini ifade etmemize olanak sağlar.

Büyük O gösterimi, algoritmanın çalışma süresinin nasıl ölçeklendiğini ifade eder. O (N) ile gösterilen bir algoritma, girdi boyutu N'ye bağlı olarak çalışma süresinin doğrusal olarak artacağını belirtir. Ancak bu, her zaman O (N) olan bir algoritmanın herhangi bir O (N^2) algoritmadan daha hızlı olduğu anlamına gelmez.

Yani, metindeki ifade, büyük O gösteriminin sadece çalışma süresinin ölçeklendirilmesini ifade ettiğini ve her zaman O (N) olan bir algoritmanın herhangi bir O (N^2) algoritmadan daha iyi olmadığını kabul etmemiz gerektiğini vurgulamaktadır.

### Büyük O İle Gösterilen İfadelerin Değerlendirilmesi

Örneğin, "O(N^3 + N)" gibi bir ifade verildiğinde, ikinci N terimi tam olarak bir sabit değil, ancak çok önemli değildir. Zaten sabitleri göz ardı ettiğimiz için, "O(N^3 + N^2)" ifadesi "O(N^3)" olarak kabul edilebilir. Yani, bu durumda N terimini göz ardı edebiliriz.

Metinde, daha az baskın olan terimlerin göz ardı edilmesi gerektiği belirtiliyor. Örneğin, "O(N^2 + N)" ifadesi "O(N^2)" olarak kabul edilir. Benzer şekilde, "O(N + log N)" ifadesi "O(N)" olarak kabul edilebilir. Aynı şekilde, "O(52^N + 100N^100)" ifadesi "O(2^N)" olarak kabul edilebilir.

Ancak, bazen çalışma zamanında toplam olabilir. Örneğin, "O(B + A)" ifadesi (A ve B hakkında özel bir bilgi olmadan) azaltılamaz.


### Multi-Part Algorithms: Add vs. Multiply

Bir algoritmanızın iki adımı olduğunu düşünelim. Zaman karmaşıklıklarını çarpmak veya toplamak ne zaman gereklidir?

Eğer adımlar ardışık olarak, birbirini takip eden şekilde gerçekleştiriliyorsa, genellikle adımların zaman karmaşıklıklarını toplamalısınız. Bunun nedeni, toplam çalışma zamanının, her bir adımın zaman karmaşıklıklarının toplamından oluşmasıdır.

Örneğin, 1. Adımın çalışma zamanı O(N) ise ve 2. Adımın çalışma zamanı O(M) ise, algoritmanın toplam çalışma zamanı O(N + M) olur, çünkü adımlar birbiri ardından gerçekleştirilir.

Diğer taraftan, adımlar iç içe döngülerde veya ikinci adımın çıktısı ilk adıma bağlı olduğu durumlarda çarpmalısınız. Bunun nedeni, ilk adımın her bir tekrarlaması için ikinci adımın birden fazla kez çalıştırılmasıdır.

Örneğin, 1. Adımın çalışma zamanı O(N) ise ve 2. Adımın çalışma zamanı O(M) ise, ancak 2. Adım 1. Adımın her bir tekrarlaması için M kez çalıştırılıyorsa, toplam çalışma zamanı O(N * M) olur, çünkü adımlar iç içe bir şekilde gerçekleştirilir.

Adımlar arasındaki bağımlılıkları ve etkileşimleri dikkatlice analiz etmek, zaman karmaşıklıklarını çarpmak veya toplamak konusunda doğru kararı vermek için önemlidir. Bu ayrım gerçekten kafa karışıklığına neden olabilen bir konudur ve adayların dikkat etmeleri gereken bir konudur.


[Türkçeleştirme Devam Etmektedir]
