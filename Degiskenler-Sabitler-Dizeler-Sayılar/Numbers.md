# Tam Sayıları Nasıl Saklarız

3, 5, 50 veya 5 milyon gibi tam sayılarla çalışırken, Swift'in "integer" olarak adlandırdığı, kısaca `Int` dediği bir veri tipi ile çalışıyorsunuz – "integer" kelimesi köken olarak Latince'de "bütün" anlamına gelir, merak ediyorsanız.

Yeni bir tam sayı oluşturmak, bir dizi oluşturmakla aynı şekilde çalışır: sabit veya değişken olup olmamasına bağlı olarak `let` veya `var` kullanın, bir isim verin ve ardından bir değer atayın. Örneğin, şöyle bir skor sabiti oluşturabiliriz:

```swift
let score = 10
```
Tam sayılar gerçekten çok büyük olabilir – milyarlar, trilyonlar, katrilyonlar ve hatta kentilyonlar ötesinde, ama aynı zamanda çok küçük de olabilirler – kentilyonlara kadar negatif sayıları saklayabilirler.

Sayıları el ile yazarken, ne olduğunu görmek zor olabilir. Örneğin, bu sayı nedir?

```swift
let reallyBig = 100000000
```
Eğer bunu el ile yazsaydık, muhtemelen “100,000,000” şeklinde yazardık ve böylece sayının 100 milyon olduğunu net bir şekilde görürdük. Swift’in buna benzer bir özelliği vardır: sayıları istediğiniz gibi ayırmak için alt çizgi (_) kullanabilirsiniz.

Bu nedenle, önceki kodumuzu şu şekilde değiştirebiliriz:
```swift
let reallyBig = 100_000_000
```
Swift aslında alt çizgilerle ilgilenmez, bu yüzden isterseniz bunu da yazabilirsiniz:

```swift
let reallyBig = 1_00__00___00____00
```
Sonuç aynı olacaktır: reallyBig 100,000,000 değerine sahip bir tam sayı olarak ayarlanır.

Elbette, tam sayıları diğer tam sayılardan oluşturabilirsiniz; okulda öğrendiğiniz aritmetik operatörleri kullanarak: toplama için +, çıkarma için -, çarpma için *, ve bölme için /.

Örneğin:

```swift
let lowerScore = score - 2
let higherScore = score + 10
let doubledScore = score * 2
let squaredScore = score * score
let halvedScore = score / 2
print(score)
```
Yeni sabitler oluşturmak yerine, Swift bazı özel işlemler sağlar; bu işlemler bir tam sayıyı belirli bir şekilde ayarlar ve sonucu orijinal sayıya geri atar.

Örneğin, bu kod bir counter değişkeni oluşturur ve ona 10 değerini atar, ardından 5 ekler:

```swift
var counter = 10
counter = counter + 5
```
counter = counter + 5 yerine, += kısa yol operatörünü kullanabilirsiniz, bu da sayıyı doğrudan ilgili tam sayıya ekler:

```swift
counter += 5
print(counter)
```
Bu, aynı şeyi yapar, sadece daha az yazı gerektirir. Buna bileşik atama operatörleri diyoruz ve diğer biçimleri de vardır:

```swift
counter *= 2
print(counter)
counter -= 10
print(counter)
counter /= 2
print(counter)
```
Tam sayılarla işimiz bitmeden son olarak bir şey daha belirtmek istiyorum: diziler gibi, tam sayıların da bazı kullanışlı işlevleri vardır. Örneğin, bir tam sayının başka bir tam sayının katı olup olmadığını öğrenmek için isMultiple(of:) çağırabilirsiniz.

Bu nedenle, 120'nin üçün katı olup olmadığını şu şekilde sorabiliriz:

```swift
let number = 120
print(number.isMultiple(of: 3))
```
Burada isMultiple(of:) işlevini bir sabite çağırıyorum, ancak doğrudan sayıyı da kullanabilirsiniz:

```swift
print(120.isMultiple(of: 3))
```


