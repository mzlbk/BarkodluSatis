# BarkodluSatis
Barkodlu Satış Uygulaması

"Barkodlu Satış.rar" dosyası uygulamanın setup halidir.
"BarkodluSatis.rar" dosyası uygulamanın kodlarının bulunduğu halidir.

Kullanıcı Adı : admin
Şifre         : admin

Uygulamanın içerisinde hâli hazırda çok fazla buglar, kapatılması gereken açıklar ve göze batan tasarım hataları vardır...

Gazi Üniversitesi Bilgisayar Mühendisliği bölümü 1. sınıf 2. dönem proje ödevidir...

************************************************************************************************************

    ÖZET
    Marketlerde, bakkallarda özellikle küçük işletmelerde kullanılması planlanan bir otomasyon projesi. İçinde personelin işlerini büyük ölçüde kolaylaştıracak bir
    sistem barındırıyor. Ürün ekleme silme, stok takibi, ürün fiyat durumu güncelleme, ürün grubu ekleme ve hızlı tuşlar gibi özellikler kullanıcının işlerini büyük
    ölçüde kolaylaştırıyor. Bütün bu özellikleri her kesimden insanın kullanabilmesi için sade, basit ve anlaşılır bir biçimde tasarladım.


Proje küçük işletmeler için otomasyon sistemidir. Kayıt tutma, ürün arama, fiyat güncelleme gibi maliyetleri en aza indirgemeyi amaçladım. Ürün girdi, grup, fiyat
durumlarını görüntüleyebileceği ve bunları düzenleyebileceği bunlara ek olarak da yapılan satış işlemlerinin kaydını görüntüleyebileceği bir programdır.

Projemde "Yerel Veri tabanı" kullanmak yerine "Hizmet Tabanlı Veri tabanı" kullandım [1]. İkisinin birbirinden farkları ise;
Hizmet tabanlı bir veri tabanı, yalnızca bir sunucu aracılığıyla erişilen bir veri tabanıdır. SQL Server formatı olan bir MDF veri dosyası kullanır. Bir SQL Server
veri tabanına bağlanabilmek için SQL Server hizmetinin çalışıyor olması gerekir, çünkü isteklerinizi işleyen ve veri dosyasına erişen odur. Yerel veri tabanı ise
yalnızca uygulamanız için yerel olan veri tabanıdır. SQL Server CE (Compact Edition) biçimi olan bir SDF veri dosyası kullanır. SDF veri tabanına erişmek için sunucu
yüklemeye gerek yoktur. SSCE'Yİ oluşturan dll'leri uygulamanızla birlikte yüklemeniz ve veri dosyasına doğrudan erişmeniz yeterlidir [2]. Fakat ben daha fazla şey
öğrenmek için hizmet tabanlı veri tabanını seçtim.

    Çok fazla değişken, değişken türleri arasında kaybolmamak ve küçük çaplı bir proje üzerinde uğraştığım için “var” değişken türünden (özellikle lamda expression’da)
    çokça yararlandım [3].

     Algoritma oluştururken beni büyük bir dertten kurtaran LINQ'den ve özellikle Lambda Expressions'dan çokça yararlandım. Microsoft'un Visual Studio 2008 ve .NET
Framework 3.5 ile beraber kullanıma sunduğu LINQ (Language INtegrated Query) veya Türkçesi Programlama Diliyle Bütünleştirilmiş Sorgu olan, Haskell, XML, HTML ve
SQL programlama dilleri gibi bildirimsel (Declerative) yazım şekli (sözdizimi, syntax) kullanan bir bileşen teknolojidir. 
     C#'daki Lambda ifadeleri, anonim işlevler gibi kullanılır; şu farkla ki, Lambda ifadelerinde girdiğiniz değerin türünü belirtmeniz gerekmez, bu nedenle kullanımı
daha esnek hale getirir. '=>' işareti, tüm lambda ifadelerinde kullanılan lambda operatörüdür. Lambda ifadesi iki kısma ayrılır, sol taraf girdi, sağ taraf ise
ifadedir [4,5,6,7].

    "ToBindingList" ve "Load" metotları için "System.Data.Entity" kütüphanesini kullandım [8,9].


************************************************************************************************************


    GİRİŞ PANELİ
![image](https://user-images.githubusercontent.com/96550890/200093212-c75d53b6-86c4-4601-bdc7-6558782fa931.png)
    
    SATIŞ PANELİ
![image](https://user-images.githubusercontent.com/96550890/200093261-5f901b65-323b-47c3-92d5-6f77fa42cb8b.png)

    FİYAT GÜNCELLEME PANELİ
![image](https://user-images.githubusercontent.com/96550890/200093269-998a09ab-0135-4d4a-a74a-735eed5fbf5e.png)

    HIZLI BUTON EKLEME PANELİ
![image](https://user-images.githubusercontent.com/96550890/200093275-d08b113c-0b9f-4fac-836d-7664ccdc8f5d.png)

    ÜRÜN EKLEME PANELİ
![image](https://user-images.githubusercontent.com/96550890/200093288-05a12048-f3bb-4ede-9ad5-0ab8cbaa418d.png)

    ÜRÜN GRUBU EKLEME PANELİ
![image](https://user-images.githubusercontent.com/96550890/200093304-4a78d543-e855-4bfd-91e4-efe37d73df71.png)

    RAPOR PANELİ
![image](https://user-images.githubusercontent.com/96550890/200093314-8c429d3d-2320-46a3-b4ec-4cd9800822ea.png)


************************************************************************************************************

[1] https://docs.microsoft.com/tr-tr/visualstudio/data-tools/create-a-sql-database-by-using-a-designer?view=vs-2022
[2] https://social.msdn.microsoft.com/Forums/en-US/336c59c2-7ea8-4a2f-b8c1-a6c1c2625396/what-is-servicebased-database-in-dotnet?forum=aspsqlserver
[3] https://docs.microsoft.com/tr-tr/dotnet/csharp/language-reference/keywords/var
[4] https://yazilim.cevapsitesi.com/Makaleler/5/linq-language-integrated-query-dile-entegre-edilmis-sorgu-nedir
[5] https://docs.microsoft.com/tr-tr/dotnet/standard/linq/
[6] https://docs.microsoft.com/tr-tr/dotnet/csharp/language-reference/operators/lambda-expressions
[7] https://www.geeksforgeeks.org/lambda-expressions-in-c-sharp/
[8] https://docs.microsoft.com/tr-tr/ef/ef6/querying/load-method
[9] https://docs.microsoft.com/tr-tr/ef/ef6/querying/local-data

************************************************************************************************************

Bedirhan Aydın
