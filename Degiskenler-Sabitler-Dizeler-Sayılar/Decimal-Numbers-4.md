# Ondalık Sayıları Depolama

Ondalık sayılarla çalışırken (örneğin 3.1, 5.56 veya 3.141592654), Swift’in "kayan noktalı sayılar" olarak adlandırdığı veri tipini kullanıyorsunuz. Bu isim, bilgisayarınızın sayıları depolama yönteminin karmaşıklığından gelir: bilgisayar, çok büyük sayıları (örneğin 123.456.789) ile çok küçük sayıları (örneğin 0.0000000001) aynı miktarda alanda depolamaya çalışır ve bunu yapmak için ondalık noktayı sayının boyutuna göre hareket ettirir.

Bu depolama yöntemi, ondalıklı sayıların programcılar için genellikle sorun yaratmasına neden olur. Bunu Swift kodu ile görebilirsiniz:

```swift
let number = 0.1 + 0.2
print(number)
```
Bu kod çalıştırıldığında 0.3 yerine 0.30000000000000004 yazdırır – bu, 0.3, ardından 15 sıfır ve sonrasında bir 4. Bu karmaşıklığı daha sonra açıklayacağım, ancak önce önemli olan noktalar üzerinde duralım.

Öncelikle, bir kayan nokta sayısı oluşturduğunuzda Swift bunu Double olarak kabul eder. Double, "çift hassasiyetli kayan noktalı sayı" anlamına gelir, ki bu isim biraz garip görünebilir – kayan noktalı sayılarla nasıl çalıştığımız yıllar içinde çok değişti ve Swift bunu basit hale getirse de bazen daha eski kodlarla karşılaşabilirsiniz. Bu, Swift’in, bazı eski dillerin yapabildiğinden iki kat fazla depolama alanı ayırdığı anlamına gelir ve bu nedenle Double, son derece büyük sayıları depolayabilir.

İkincisi, Swift ondalıklı sayıları tam sayılardan tamamen farklı bir veri türü olarak değerlendirir; bu da onların bir arada kullanılamayacağı anlamına gelir. Sonuçta, tam sayılar her zaman %100 doğruyken, ondalıklı sayılar doğru olmayabilir, bu yüzden Swift, iki türü birlikte kullanmanıza izin vermez, ancak bunu özellikle talep ederseniz yapar.

Pratikte, bu demektir ki, bir tam sayıyı ondalıklı bir sayıya ekleyemezsiniz, bu nedenle şu tür bir kod hata verecektir:

```swift
let a = 1
let b = 2.0
let c = a + b
```
Evet, b'nin aslında 2 olarak maskelenmiş bir ondalıklı sayı olduğunu görebiliyoruz, ama Swift yine de bu kodun çalışmasına izin vermez. Bu, "tip güvenliği" olarak adlandırılır: Swift, farklı veri türlerini kazara karıştırmanıza izin vermez.

Bunun olmasını istiyorsanız, Swift’e b'deki Double’ı bir Int olarak işlemeyi veya a'daki Int'i bir Double olarak işlemeyi açıkça belirtmelisiniz:


```swift
let c = a + Int(b)

```
Veya:

```swift
let c = Double(a) + b
```
Üçüncüsü, Swift, sağladığınız sayıya göre bir Double mı yoksa Int mi oluşturmak istediğinizi belirler – eğer noktalar varsa, bu bir Double’dır, aksi takdirde bir Int. Evet, noktadan sonraki sayılar 0 bile olsa.

Örneğin:

```swift
let double1 = 3.1
let double2 = 3131.3131
let double3 = 3.0
let int1 = 3
```
Tip güvenliği ile birlikte, bu Swift’in bir sabit veya değişkenin hangi veri türünü sakladığını belirledikten sonra, her zaman aynı veri türünü sakaması gerektiği anlamına gelir. Yani, bu kod doğru:

```swift
var name = "Nicolas Cage"
name = "John Travolta"
```
Ancak bu kod doğru değildir:

```swift
var name = "Nicolas Cage"
name = 57
```
Bu kod, Swift’e name'in bir string saklayacağını söyler, ancak ardından bir tam sayıyı oraya koymaya çalışır.

Son olarak, ondalıklı sayılar, tam sayılarla aynı aralıkta operatörler ve bileşik atama operatörlerine sahiptir:

```swift
var rating = 5.0
rating *= 2
```
Birçok eski API, ondalıklı sayıları saklamanın biraz farklı bir yolunu kullanır, bu da CGFloat olarak adlandırılır. Neyse ki, Swift, bir CGFloat beklenen her yerde normal Double sayılarını kullanmamıza izin verir, bu nedenle CGFloat’i zaman zaman görseniz de bunu görmezden gelebilirsiniz.

Merak ediyorsanız, kayan noktalı sayıların karmaşık olmasının nedeni bilgisayarların karmaşık sayıları ikili sistemle depolamaya çalışmasıdır. Örneğin, 1’i 3’e böldüğünüzde 1/3 elde edersiniz, ancak bu ikili sistemde depolanamaz, bu yüzden sistem çok yakın tahminler yaratacak şekilde tasarlanmıştır. Bu son derece verimlidir ve hata o kadar küçüktür ki genellikle önemsizdir, ancak en azından Swift’in Int ve Double’ı kazara karıştırmanıza neden izin vermediğini biliyorsunuz!
