# .Net kodu nedir nasıl derlenir ?

Microsoft’ un uygulama geliştirme platformunda farklı türlerde ve farklı programlama dilleri kullanılarak uygulama geliştirilebilir.
Örneğin, Windows üzerine çalışacak programlar, Windows Phone işletim sistemli (WP7,WP8) akıllı cihazlar için mobil uygulamalar ve web uygulamaları geliştirmek mümkündür.
.Net platformunda yazdığınız bir uygulama dilden ve platformdan bağımsızdır. Peki ama nasıl? Bu noktada platformun bileşenleri önemlidir. Yeni başlayanlar için oldukça karmaşık 
görünen platformda bir çok bileşen bulunur.
Örneğin C# ile yazdığınız bir kod derleyici ile ortak dil altyapısına (Common Language Infrastructure-CLI) uyarlanır.
Buradan sonra ortak ara dil derleyicisi (Common Intermediate Language-CIL) kodu platforma uygun dile dönüştürmek üzere ortak dil çalışma zamanı derleyicisine
(Common Language Runtime-CLR)  gönderir. CLR’ in işlevi CIL tarafından gönderilen kodu makine diline dönüştürmektir.
Böylece C# (yada diğer platform dilleri ile) yazılan kod derlenmiş ve çalıştırılabilir hale getirilmiş olur.  
[kaynak](https://www.teknologweb.com/microsoft-net-nedir)  
[kaynak](https://www.youtube.com/watch?v=MNywsguVPsc)

# Roslyn compiler ne işe yarar ?
.NET Derleyici Platformu ayrıca takma adıyla bilinen, Roslyn ,bir dizi açık-kaynak derleyici ve kod analizi için API'ler C # ve Visual Basic .NET gelen diller.
Proje özellikle C # ve VB.NET derleyicilerinin kendi kendini barındıran sürümlerini içerir
kendi dillerinde yazılan derleyiciler. Derleyiciler, geleneksel komut satırı programları aracılığıyla, ancak aynı zamanda .NET kodu içinden yerel olarak kullanılabilen
API'ler olarak da kullanılabilir. Roslyn , kodun sözdizimsel ( sözcüksel ) analizi, anlamsal analiz, CIL için dinamik derleme ve kod yayımı için modülleri ortaya çıkarır.
###Roslyn'in en önemli temel özellikleri şunlardır: 
- API'ler aracılığıyla hizmet olarak sunulan C # ve Visual Basic .NET dilleri için derleyiciler .
- Kod analizi ve yeniden düzenleme için API'ler .

# Restfull servisleri  nasıl çalışır ? Alternatifleri nelerdir?
REST, servis yönelimli mimari üzerine oluşturulan yazılımlarda kullanılan bir veri transfer yöntemidir. 
HTTP üzerinde çalışır ve diğer alternatiflere göre daha basittir, minimum içerikle veri alıp gönderdiği için de daha hızlıdır. 
İstemci ve sunucu arasında XML veya JSON verilerini taşıyarak uygulamaların haberleşmesini sağlar. 
REST standartlarına uygun yazılan web servislerine RESTful servisler diyoruz.
REST stateless‘dır, yani durum bilgisini saklamaz.REST standartlarında istemci-sunucu arasında taşınan verilerde ekstra başlık bilgileri saklanmaz, 
istemciye ait detaylar bulunmaz,bu bilgiler istemci-sunucu arasında taşınmaz. Dolayısıyla servis yönelimli uygulamalarda REST bize lightweight bir çözüm yapısı sunar.  
[kaynak ve detaylı bilgi](http://devnot.com/2016/rest-mimarisi-ve-restful-servisler/)

#Extension method nedir, nasıl yazılır?
Extension method, kelime anlamı ile genişletilebilir metod anlamına gelmektedir. Extension method bize .Net içerisinde bulunan sınıflara yeni metodlar eklememizi sağlamaktadır. 
Extension metodlar static class içerisinde static olarak tanımlanmaktadır.
Konu ile ilgili bir örnek yapalım. Int sınıfında ToString() metodu bulunmaktadır. Bu metod sayesinde biz int türünde olan bir değeri string türüne çevirebilmekteyiz.
```c#
int Sayi = 10;  
this.Text = Sayi.ToString();  
```
Fakat String sınıfında doğrudan string bir değeri int türüne çevirebileceğimiz bir metod bulunmamaktadır. Extension metod tamda burada işimize yaramaktadır.
Bu yapı ile kendimiz bir metod yazarak string bir değeri int türüne dönüştürebileceğiz.
```c#
public static class ExtensionClass  
{  
    public static int IntCevir(this string Deger)  
    {  
        return Int32.Parse(Deger);  
    }  
}  
```
Burada dikkat etmeniz gereken en önemli nokta parametrenin this anahtar kelimesi ile başlamasıdır. Bu ifade ile metodumuzun extension metod olduğunu belirtiyoruz. 
Sonrasında belirttiğimiz string ifadesi ile metodun hangi sınıflar üzerinde geçerli olacağını belirtmekteyiz.
[detaylı bilgi](https://www.hikmetokumus.com/makale/24/csharp-ile-extension-metod-kullanimi)  
# MVC nin alternatifleri nelerdir?
### MVC sorunları
- MVC Durum Bilgilidir

Yalnızca View ve View-Model bağlamasının durumsal olması mantıklıdır (böylece Model değiştiğinde Görünümü güncelleyebilir)

- MVC'nin Tek Bir Yorumu Yok

Her çerçeve kendi incelikli sürümünü kullanır.

- Oturum Açmak Nasıl Uygun?

Açıkça veri merkezli olmayan uygulama kodu uygulamanın neresine aittir?
 ## Alternatifler
 - HMVC - Hiyerarşik Model-Görünüm-Denetleyici
 - MVVM - Model-Görünüm-Görünüm Modeli
 - MVP - Model Görünümü Sunucusu
 - MVA - Model Görünümü Adaptörü
 - PAC - Sunum Soyutlama Kontrolü
 - RMR - Kaynak-Yöntem-Temsil
 - ADR - Eylem Etki Alanı Yanıtlayıcı
  [Daha fazla bilgi için](https://blog.ircmaxell.com/2014/11/alternatives-to-mvc.html)  
 
 # Architectural pattern nedir ?
 
Her model, çevremizde tekrar tekrar ortaya çıkan bir sorunu tanımlar ve ardından bu sorunun çözümünün özünü, 
bu çözümü, aynı şekilde iki kez yapmadan milyonlarca kez kullanabileceğiniz şekilde tanımlar.

-Christopher Alexander

Alt sistemlerin yapısını veya organizasyonunu etkilediği daha geniş bir bağlamda basitçe bir tasarım tekniği olarak tanımlayabiliriz.
İlişkileri kurar, sorumlulukları tanımlar ve genel mimarinin kurallarını ve yönergelerini sağlar.
[detaylı bilgi](https://towardsdatascience.com/10-common-software-architectural-patterns-in-a-nutshell-a0b47a1e9013)  

