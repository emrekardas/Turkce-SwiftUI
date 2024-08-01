# Variable ve Constant Nasıl Oluşturulur

Program geliştirdiğinizde bazı verileri saklamak isteyeceksiniz. Bu veriler, kullanıcının yeni yazdığı ad olabilir, internetten indirdiğiniz bazı haberler olabilir ya da yaptığınız karmaşık bir hesaplamanın sonucu olabilir.

Swift, verileri saklamanın iki yolunu sunar; verilerin zaman içinde değişmesini isteyip istemediğinize bağlı olarak. İlk seçenek, yeni bir playground oluşturduğunuzda otomatik olarak kullanılır ve şu satırı içerir:

```
var greeting = "Hello, playground"
```

Bu, `greeting` adında yeni bir değişken oluşturur ve değişken olduğu için değeri değişebilir – programımız çalışırken değişebilir.

**İpucu:** macOS playground'undaki diğer satır `import Cocoa`'dur; bu, Apple tarafından sağlanan geniş bir kod koleksiyonunu içerir ve uygulama geliştirmeyi kolaylaştırır. Bu, birçok önemli işlev içerir, bu yüzden bunu silmeyin.

Bu kodda dört ana sözdizimi parçası bulunmaktadır:

1. **`var`** anahtar kelimesi "yeni bir değişken oluştur" anlamına gelir; bu, biraz yazım tasarrufu sağlar.
2. **`greeting`** adında bir değişken çağırıyoruz. Değişkeninizi ne olarak adlandıracağınız size kalmış, ancak çoğu zaman açıklayıcı olmasını istersiniz.
3. **`=`** işareti, değişkene bir değer atar. Eşittir işareti etrafında boşluklara ihtiyacınız yoktur, ancak bu en yaygın stildir.
4. Atadığımız değer `"Merhaba, playground"` metnidir. Metnin nerede başladığını ve bittiğini Swift'e göstermek için çift tırnak içinde yazılmıştır.

Diğer dillerde semikolona ihtiyaç duyulmadığını fark etmiş olabilirsiniz. Swift, semikolonu destekler, ancak çok nadirdir – iki kod parçasını aynı satıra yazmanız gerekiyorsa kullanılır.

Bir değişken oluşturduğunuzda, onu zaman içinde değiştirebilirsiniz:

```
var name = "Ted"
name = "Rebecca"
name = "Keeley"
```
Bu, `name` adında yeni bir değişken oluşturur ve ona "Ted" değerini atar. Daha sonra bu değer iki kez değiştirilir, önce "Rebecca" ve ardından "Keeley" olur – yeni bir değişken oluşturmadığımız için tekrar `var` kullanmamıza gerek yoktur. Değişkenleri ihtiyaç duyduğunuz kadar değiştirebilirsiniz ve eski değer her seferinde silinir.

(Farklı metinler kullanmakta özgürsünüz, ancak ben Ted Lasso dizisinin büyük bir hayranıyım, bu yüzden "Ted" ismini kullandım. Ve evet, diğer Ted Lasso referanslarını ve daha fazlasını ilerleyen bölümlerde görebilirsiniz.)

Bir değeri hiç değiştirmek istemiyorsanız, bunun yerine bir sabit kullanmanız gerekir. Bir sabit oluşturmak, bir değişken oluşturmakla neredeyse aynı şekilde çalışır, tek fark `let` kullanmamızdır:

```swift
let character = "Daphne"
```
Artık `let` kullandığımızda bir sabit oluşturuyoruz, bu da değişmeyen bir değerdir. Swift gerçekten buna izin vermez ve denediğimizde büyük bir hata gösterir.

Bana inanmadınız mı? Bunu Xcode'a yazmayı deneyin:

```swift
let character = "Daphne"
character = "Eloise"
character = "Francesca"
```

Yine, ikinci ve üçüncü satırlarda `let` anahtar kelimeleri yok çünkü yeni sabitler oluşturmuyoruz, sadece mevcut olanı değiştirmeye çalışıyoruz. Ancak dediğim gibi, bu çalışmaz – bir sabiti değiştiremezsiniz, aksi takdirde sabit olmazdı!

Merak ediyorsanız, “let” matematik dünyasından gelir, burada “let x be equal to 5” gibi ifadeler kullanılır.

**Önemli:** Hata gösteren iki kod satırını silin – sabitleri gerçekten değiştiremezsiniz!

Swift öğrenirken, Xcode'dan herhangi bir değişkenin değerini yazdırmasını isteyebilirsiniz. Gerçek uygulamalarda bunu pek kullanmazsınız çünkü kullanıcılar yazdırılanları göremez, ancak verinizin içinde ne olduğunu görmek için basit bir yol sağlar.

Örneğin, bir değişkenin her ayarlandığında değerini yazdırabiliriz – playground'unuza şu kodu girin:

```
var playerName = "Roy"
print(playerName)

playerName = "Dani"
print(playerName)

playerName = "Sam"
print(playerName)
```
**İpucu:** Xcode playground'unuzda kodu çalıştırmak için sol taraftaki mavi oynat simgesine tıklayabilirsiniz. Mavi şeritte yukarı veya aşağı hareket ederseniz, oynat simgesinin de hareket ettiğini göreceksiniz – bu, kodu belirli bir noktaya kadar çalıştırmanıza olanak tanır, ancak genellikle son satıra kadar çalıştırmak istersiniz.

Değişkenimi `playerName` olarak adlandırdığımı ve `playername`, `player_name` veya başka bir alternatif kullanmadığımı fark etmiş olabilirsiniz. Bu bir tercihtir: Swift, sabitlerinizin ve değişkenlerinizin adlarını ne olarak adlandırdığınızı pek umursamaz, tek şartla her yerde aynı şekilde referans göstermelisiniz. Yani, önce `playerName` sonra `playername` kullanamazsınız – Swift bu iki ismi farklı olarak görür.

Swift, verilerimizi nasıl adlandırdığımıza önem vermese de, kullandığım adlandırma stili Swift geliştiricileri arasında standarttır – buna "konvansiyon" diyoruz. Merak ediyorsanız, bu stil "camel case" olarak adlandırılır, çünkü isimdeki ikinci ve sonraki kelimeler büyük harf ile başlar ve küçük bir çıkıntı oluşturur:

```swift
let managerName = "Michael Scott"
let dogBreed = "Samoyed"
let meaningOfLife = "Bir adam kaç yol yürümelidir?"
```
Mümkünse, değişkenler yerine sabitler kullanmayı tercih edin – bu sadece Swift'in kodunuzu biraz daha iyi optimize etme şansı verir, aynı zamanda Swift'in sabitin değerini yanlışlıkla değiştirmediğinizden emin olmasını sağlar.
