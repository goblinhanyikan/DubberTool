# DUB.TOOL

Tamamen tarayıcı üzerinde çalışan, yerel (local-first) bir seslendirme ve dublaj aracı. Bir video yükleyin, istediğiniz bölümün üzerine yeni diyalog kaydedin ve dublajlı hâlini dışa aktarın — hepsi tek bir HTML dosyası içinde, hiçbir şey kurulmadan, hiçbir şey sunucuya yüklenmeden.

---

## Ne için kullanılır

- Videonun tamamını ya da bir kısmını, tüm zaman çizelgesini baştan düzenlemeden yeniden seslendirmek.
- Sadece belirli noktalardaki diyaloğu değiştirmeniz gereken hızlı lokalizasyon/dublaj işleri.
- Hatalı okunan replikleri düzeltmek — tüm klibi değil, sadece bozuk kısmı yeniden kaydetmek.
- Başka bir uygulamada (DAW, video düzenleyici vb.) düzenlemek üzere karışık ses parçasını dışa almak.

Bu araç **tam bir video düzenleyici değildir** — video zaman çizelgesini kesmez, kırpmaz, başlık eklemez ya da görsel hiçbir şeye dokunmaz. Sadece işaretlediğiniz bölgelerdeki sesi değiştirir.

---

## Genel işleyiş

1. **Bir video yükleyin.** Dosyayı sürükleyip bırakın ya da tıklayıp seçin. Tamamen cihazınızda çözümlenir — hiçbir şey bilgisayarınızdan çıkmaz.
2. Ses dalgası üzerinde sürükleyerek **bir bölge seçin**.
3. Zamanlamayı görmek için sessize alınmış orijinali izlerken o bölgenin üzerine **yeni bir seslendirme kaydedin**.
4. Klibin istediğiniz kadar bölümü için bunu **tekrarlayın**.
5. Dışa aktarmadan önce son bir kontrol için kayıtlarınızın yerleştirilmiş hâliyle tüm klibi **önizleyin**.
6. **Dışa aktarın** — ister dublajlı bir video dosyası, ister başka bir yerde kullanmak üzere sadece karışık ses parçası (WAV/MP3).

---

## Tüm özellikler

### Yükleme
- Sürükle-bırak veya tıkla-seç ile video yükleme (mp4/webm/mov). Her şey tamamen tarayıcınızda, yerel olarak işlenir.

### Ses dalgası ve gezinme
- Video yüklendiğinde kaynak videonun tam ses dalgası çizilir.
- Uzun klipler üzerinde hassas düzenleme için ses dalgasında **yakınlaştırma/uzaklaştırma** — +/− düğmelerini, sıfırlamak için "sığdır" düğmesini ya da imlecinize odaklı yakınlaştırmak için **Ctrl/Cmd + fare tekerleği**ni kullanın.
- Yakınlaştırıldığında ses dalgası yatay olarak kayar, ve oynatma sırasında oynatma imleci ekrandan çıkarsa görünüme otomatik olarak geri kayar.

### Seçim ve kayıt
- Yeniden yapmak istediğiniz bölgeyi işaretlemek için ses dalgası üzerinde sürükleyin (seçim yapılırken kırmızı ile gösterilir).
- **Kayıt**a basın — gerçek kayıt başlamadan önce 3 biplik bir geri sayım duyarsınız, böylece kayıtta ölü an ya da yanlış başlangıç olmaz. Siz konuşurken video, seçili bölge boyunca (sessize alınmış olarak) oynar; mikrofonunuzun sinyal aldığını görebilmeniz için canlı kırmızı bir giriş göstergesi de bulunur.
- Kayıt, seçili bölgenin sonunda otomatik olarak durur.
- **Boşluk tuşu güvenliği**: kayıt aktifken boşluk tuşuna basmak, videonun kendi duraklat davranışını tetiklemek yerine (bu davranış eskiden oynatma ile kaydediciyi senkron dışı bırakıyordu) kaydı düzgünce durdurur.
- Mikrofon izni yalnızca bir kez istenir ve sonraki tüm kayıtlar için yeniden kullanılır — her seferinde tekrar izin istenmez.
- Birden fazla mikrofonunuz varsa, mikrofon açılır menüsünden belirli bir giriş cihazı seçebilirsiniz.

### Kayıtları yönetme
- Tamamlanan her kayıt, ses dalgası üzerinde bir **sarı işaret** olarak görünür; böylece hangi kısımların zaten dublajlandığını, hangilerinin hâlâ orijinal ses olduğunu her zaman görsel olarak takip edebilirsiniz.
- **Kayıtları yeniden adlandırın** — listedeki her kaydın düzenlenebilir bir isim alanı vardır; birkaç deneme yaptığınızda bunları birbirinden ayırt etmek için kullanışlıdır (örn. "sakin kayıt", "sinirli kayıt").
- **Sarı işareti sürükleyerek** zamanlamasını sola ya da sağa kaydırın — kaydınız biraz erken ya da geç düştüyse yeniden kaydetmenize gerek kalmaz, sadece senkronize olacak şekilde itin. Sürükleme, kayıtların birbiriyle çakışmaması için sınırlandırılmıştır.
- **Bir kaydın kenarlarını kırpın** — sarı işaretin sol/sağ kenarındaki küçük tutamaçları kullanarak başta ya da sonda kaydedilmiş sessizliği kesin. Bu hiçbir sesi silmez — sadece kaydın hangi kısmının kullanılacağını ayarlar, yani çok fazla kırparsanız her zaman geri sürükleyebilirsiniz.
- **Bir kaydı çalarak** orijinal videoyla senkronize şekilde, videonun sesi düşük seviyede (sessize alınmadan) çalınırken dinleyin; böylece zamanlamayı ve performansı gerçek görüntüyle karşılaştırabilirsiniz.
- İstemediğiniz herhangi bir kaydı silin.

### Önizleme
- **Tam dublajı önizle**, tüm video boyunca oynatma yapar; işaretlenen her bölgede otomatik olarak o kaydın sesine geçer, aralarda ise orijinal sese döner — dışa aktarmadan önce son bir kontrol için son hâlin canlı bir simülasyonudur.

### Dışa aktarma
- **Dublajlı klibi oluştur (.webm)** — kayıtlarınızın ses parçasına karıştırıldığı, orijinal video kareleriyle birleştirilmiş tam bir video dosyası üretir.
- **Sadece sesi dışa aktar** — karışımı başka bir düzenleyiciye aktarmak için:
  - **.wav** — sıkıştırılmamış, kayıpsız, her yerde uyumlu.
  - **.mp3** — sıkıştırılmış (192kbps), daha küçük dosya boyutu, tamamen tarayıcınızda kodlanır.

### Projeler (çalışmanızı kaydedip devam edin)
- **Projeyi kaydet**, kayıtlarınızı, bunların zamanlama/kırpma verilerini ve isimlerini içeren bir `.dubproj` dosyası (yeniden adlandırılmış bir zip) üretir — ancak orijinal videonun kendisini *içermez* (bu, dosyayı çok büyütürdü).
- **Proje yükle**, bir `.dubproj` dosyasını yeniden açar. Videonun kendisi saklanmadığı için, videoyu **yeniden bağlamanız** istenir — aynı kaynak dosyayı tekrar seçmeniz yeterlidir, her şey (kayıtlar, zamanlama, kırpmalar, isimler) otomatik olarak yerine oturur. Dosya isim/boyut olarak eşleşmezse bir uyarı alırsınız, ancak yine de yüklenir.

### Dil
- Sağ üstte tam bir **İngilizce / Türkçe** arayüz geçiş düğmesi bulunur (düğme, geçebileceğiniz *diğer* dili gösterir). İlk yüklemede tarayıcınızın dilini otomatik algılar ve sonrasında seçiminizi hatırlar.

---

## Pratik ipuçları

- **Sıkı diyaloglar için kayıttan önce yakınlaştırın.** Uzun bir klipte varsayılan "sığdır" yakınlaştırma seviyesinde yarım saniyelik bir bölgeyi doğru seçmek zor olabilir — önce yakınlaştırın.
- **Bir kaydın başında veya sonunda sadece biraz boşluk varsa yeniden kaydetmek yerine kırpma tutamaçlarını kullanın.** Başka bir kayıt yapmaktan çok daha hızlıdır.
- **Dışa aktarmadan önce tam dublajı önizleyin** — render adımı (özellikle uzun videolarda) gerçek zaman alır, çünkü videoyu yakalamak için gerçek zamanlı olarak oynatır; kötü bir düzenlemeyi önizleme aşamasında fark etmek, dışa aktarmayı tekrarlamaktan kurtarır.
- **Sadece sese ihtiyacınız varsa video dışa aktarmayı atlayın.** WAV/MP3 dışa aktarımı neredeyse anında render edilir (gerçek zamanlı oynatmaya gerek yoktur), çünkü birleştirilecek bir video yoktur.
- **Uzun bir dublaj oturumu yapıyorsanız projenizi düzenli olarak kaydedin** — kayıtlar, kırpmalar ve isimler yalnızca bir `.dubproj` dosyasına yazıldığında güvenli hâle gelir.

## Bilinen sınırlamalar

- Video dışa aktarımı `.mp4` değil `.webm` üretir — bu bir tarayıcı (`MediaRecorder`) sınırlamasıdır. `.mp4`'e ihtiyacınız varsa, WAV/MP3 ses dışa aktarımını kullanıp orijinal videonuzla başka bir araçta yeniden birleştirin.
- YouTube bağlantıları desteklenmez — tarayıcılar YouTube'un ses akışına doğrudan erişemez. Önce dosyayı yerel olarak indirin (örn. `yt-dlp` ile) ve normal bir video dosyası olarak yükleyin.
- Her şey tarayıcı sekmenizde çalışır — sekmeyi kapatmak kaydedilmemiş çalışmayı kaybettirir. Daha sonra devam etmek istiyorsanız kapatmadan önce projenizi kaydedin.
