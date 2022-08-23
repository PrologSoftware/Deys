# Deys Kurulum İşlemleri

> Deys Kurulum ve güncelleme işlemleri aşağıda tanımlanmıştır. Güncelleme yapılacak ortamlarda 
işlemlere başlamadan önce veritabanı ve ürün dosyaları yedeğinin alınması şiddetle tavsiye edilir !!!



## Kurulum Dosyaları

   Kurulum dosyaları aşağıdadır. Kurulum yapmak istediğiniz versiyonu indiriniz. 
   
?> İndirilen rar dosyasını Logo Setinin kurulu olduğu dizin altınada arşivden çıkartılıp klasör ismin Deys olarak değiştirilir Örn : C:\LBS\TigerEnt3 dizini altında kurulum yapılmış set için oluşturulacak dizin C:\LBS\TigerEnt3\Deys olacaktar ve rar içerisindeki dosyaları buraya kopyalanmalıdır.
   
   

* [Deys 6.0.4](http://download.deys.com.tr)


## Kuruluma Başlama

Kurulum yapmak için Deys son sürüm, Logo klasörünün içerisine kopyalanır.

Kopyalama işlemi yapıldıktan sonra Deys klasörünün ismi Deys v6 olarak değiştirilir.

Deys v6 klasörünün içerisine girilir. Deys.System.exe çalıştırılır.  
(not. Çalışmazsa Logo klasöründeki REGISTER.BAT dosyasını yönetici konumunda çalıştır.)

Veritabanı Bilgileri ekranında Logo kullanıyorsak Logoyu, Netsis kullanıyorsak Netsisi seçiyoruz.

Seçim yapıldıktan sonra kaydet/devam seçilerek veritabanı oluşturma işlemini başlatıyoruz.

Veri tabanı otomatik oluştuktan sonra gelen ekranda müşterinin kullandığı aktif Logo firma dönem bilgileri seçilir.

Config dosyası (DeysConfiguration.config) oluşmuş olur. Dosya konumundan Deys.backoffice.exe çalıştırılır. Gelen ekranda kullanıcı adı ve şifre yazılarak giriş yapılır.
	
## ISS Kurulumu ve RestServis Eklenmesi

ISS Kurulum işlemleri  


Rest Servis Kurulum işlemleri


Deys klasöründen Deys.System.exe uygulamasını çalıştırıp Bağlantı Bilgisini Güncellemeye tıklıyoruz.

Logonun içindeki Deys klasörünün dosya konumuna gidilerek RestService klasörü kopyalanarak “C:\inetpub\wwwroot” dosya yoluna yapıştırılır.

El terminali ile database’in bağlantı kurabilmesi için IIS ayarlarının yapılması gerekmektedir. Bunun için server üzerinden IIS açılır. Siteler üzerinden sağa tıklayarak Web Sitesi Ekle denir.  
Gelen ekranda Site adı “Restservice” olarak yazılır. Daha sonra Fiziksel Yol bölümünden “C:\inetpub\wwwroot\RestService” seçilir. Bağ.Nok. (Bağlantı noktası)’na boştaki bir port verilir.  (Tercihen:8181)  

Verilen port için Windows’ta Gelişmiş Güvenlik özelliklerinden gelen ve giden kurallarının ayarlanması için ilk önce _Gelen Kural_ kısmı seçilerek Eylemler kısmından Yeni Kural tıklanır.  (daha sonra giden kısmı için de yapılacak)  Açılan yeni kural sihirbaz penceresinde bağlantı noktası seçilerek ileri denir.  
Çıkan pencerede port yazılır. (8181)  
  
İleriye tıklandıktan sonra Bağlantıya izin ver işaretlenerek tekrar ileri denilir.  
Devamında gelen Ad bölümüne Deys yazılarak işlem sonlandırılır.  
Aynı işlemler _Giden Kurallar_ için de yapılır.

Restservice’nin kurulumunu test etmek için IIS siteler Restservice üzerinde sağa tıklanıp Web sitesi yönet ve göz ata basılır. Açılan web tarayıcıdan [http://localhost:8181](http://localhost:8181/terminal/getall) adresine girilir. Deys versiyonu görülür ise sistem doğru çalışıyor demektir.
	

