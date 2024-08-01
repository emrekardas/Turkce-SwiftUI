# String Nasıl Oluşturulur

Bir sabite veya değişkene metin atadığınızda, buna "string" denir – bunu, bir kelime oluşturmak için bir ip üzerine Stringlmiş Scrabble harfleri gibi düşünebilirsiniz.

Swift'in Stringleri çift tırnaklarla başlar ve biter, ancak tırnakların içine ne koyacağınız size bağlıdır. Kısa alfabetik metinler kullanabilirsiniz, örneğin:

```swift
let actor = "Denzel Washington"
```

Noktalama işaretleri, emoji ve diğer karakterleri de kullanabilirsiniz, örneğin:

```swift
let filename = "paris.jpg"
let result = "⭐️ You win! ⭐️"
```
Ve hatta, Stringnizin içinde başka çift tırnaklar kullanabilirsiniz, yeter ki önlerine bir ters eğik çizgi (`\`) koyduğunuzdan emin olun, böylece Swift bunları Stringnin sonu olarak değil, Stringnin içi olarak anlayacaktır:

```swift
let quote = "Then he tapped a sign saying \"Believe\" and walked away."
```
Endişelenmeyin – ters eğik çizgiyi unutursanız, Swift kodunuzun doğru olmadığını yüksek sesle belirtecektir.

Stringlerinizin uzunluğu için gerçekçi bir sınır yoktur, yani çok uzun bir şey, örneğin Shakespeare'in tamamlanmış eserlerini saklamak için bir String kullanabilirsiniz. Ancak, Swift'in Stringlerinde satır sonları hoş karşılanmaz. Bu tür bir kod geçerli değildir:

```swift
let movie = "A day in
the life of an
Apple engineer"
```
Bu, birden fazla satıra yayılmış Stringler oluşturamayacağınız anlamına gelmez, sadece Swift'in bunları özel bir şekilde ele alması gerektiği anlamına gelir: Stringnizin her iki tarafında birer çift tırnak yerine, üçlü tırnak kullanırsınız, şu şekilde:

```swift
let movie = """
A day in
the life of an
Apple engineer
"""
```
Bu çok satırlı Stringler pek sık kullanılmaz, ancak nasıl yapıldığını görebilirsiniz: başlangıç ve bitişteki üçlü tırnaklar kendi satırlarında bulunur ve Stringniz arada yer alır.

Stringniz oluşturulduktan sonra, Swift’in içeriğiyle çalışmak için bazı kullanışlı işlevler sunduğunu göreceksiniz. Bu işlevleri zamanla daha fazla öğreneceksiniz, ancak burada size üç şeyi tanıtmak istiyorum.

İlk olarak, bir Stringnin uzunluğunu . ardından .count yazarak öğrenebilirsiniz:

```swift
print(actor.count)
```
Çünkü actor Stringsi "Denzel Washington" metnini içeriyor, bu 17'yi yazdırır – isimdeki her harf için bir tane ve ortadaki boşluk için bir tane daha.

Stringnin uzunluğunu doğrudan yazdırmak zorunda değilsiniz – başka bir sabite atayabilirsiniz, şu şekilde:

```swift
let nameLength = actor.count
print(nameLength)
```
İkinci kullanışlı işlev uppercased(), Stringyi büyük harflere dönüştürür ve aynı Stringyi döndürür:

```swift
print(result.uppercased())
```
Evet, burada açık ve kapalı parantezler gereklidir, ancak .count ile gerekli değildir. Bunun nedeni daha sonra daha net anlaşılacaktır, ancak Swift öğreniminizin bu erken aşamasında ayrım şu şekilde açıklanabilir: Swift'ten veri okumanızı istiyorsanız parantezler gerekli değildir, ancak Swift'ten iş yapmasını istiyorsanız parantezler gereklidir. Bu tamamen doğru değildir ama şu an için ileriye gitmeniz için yeterlidir.

Son yardımcı String işlevi hasPrefix() olarak adlandırılır ve bir Stringnin belirli harflerle başlayıp başlamadığını bilmemizi sağlar:

```swift
print(movie.hasPrefix("A day"))
```
Ayrıca, bir Stringnin belirli bir metin ile bitip bitmediğini kontrol eden hasSuffix() işlevi de vardır:

```swift
print(filename.hasSuffix(".jpg"))
``` 
Önemli: Swift'te Stringler büyük/küçük harf duyarlıdır, bu nedenle filename.hasSuffix(".JPG") kullanmak, Stringnin harfleri küçük olduğu için false döndürecektir.

Stringler Swift'te gerçekten güçlüdür ve daha sadece yüzeyine dokunmuş durumdayız!
