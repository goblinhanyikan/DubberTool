# DUB.TOOL

A local-first, browser-based voiceover and dubbing bench. Drop in a video, record new dialogue over any part of it, and export a dubbed version — all inside a single HTML file, nothing installed, nothing uploaded to a server.
DISCLAIMER: This is a Vibe-Coded Application. If you are avoiding AI generated softwares for any reason, you deserve to know.
To access the app online, you can visit https://goblinhanyikan.github.io/DubberTool/

---

## What it's good for

- Re-voicing part or all of a video clip without re-editing the whole timeline in a full NLE.
- Quick localization/dubbing passes where you just need to swap dialogue in specific spots.
- Cleaning up flubbed lines — record a fresh take over just the bad section instead of the whole clip.
- Pulling a mixed-down audio track out for further editing in another app (DAW, video editor, etc).

It is **not** a full video editor — it doesn't cut, trim the video timeline, add titles, or touch anything visual. It only replaces audio in the regions you mark.

---

## How it works, at a glance

1. **Load a video.** Drop a file in, or click to browse. It's decoded entirely on your device — nothing leaves your computer.
2. **Select a region** by dragging on the waveform.
3. **Record** a new voiceover over that region, watching the muted original for timing.
4. **Repeat** for as many parts of the clip as you want.
5. **Preview** the whole thing with your takes swapped in, to sanity-check before exporting.
6. **Export** — either a dubbed video file, or just the mixed audio track (WAV/MP3) for use elsewhere.

---

## Full feature list

### Loading
- Drag-and-drop or click-to-browse video loading (mp4/webm/mov). Everything is processed locally in your browser.

### Waveform & navigation
- Full audio waveform of your source video, rendered on load.
- **Zoom in/out** on the waveform for precise editing on longer clips — use the +/− buttons, the "fit" button to reset, or **Ctrl/Cmd + scroll wheel** to zoom anchored to your cursor.
- The waveform scrolls horizontally once zoomed in, and the playhead auto-scrolls into view during playback so you never lose track of where you are.

### Selecting & recording
- Drag on the waveform to mark a region you want to redub (shown in red while selecting).
- Hit **record** — you'll get a 3-beep countdown before it actually starts, so there's no dead air or false starts in your take. The video plays (muted) through the selected region while you speak, with a live red input scope so you can see your mic is picking up signal.
- Recording auto-stops at the end of the selected region.
- **Spacebar safety**: while actively recording, pressing spacebar stops the recording cleanly instead of triggering the video's native pause (which used to desync playback and the recorder).
- Microphone permission is requested once and reused for all subsequent takes — you won't be re-prompted every time.
- Choose a specific input device from the mic dropdown if you have more than one microphone connected.

### Managing takes
- Every finished recording appears as a **yellow marker** on the waveform, so you always have a visual map of what's already been redubbed vs. what's still original audio.
- **Rename takes** — each take in the list has an editable name field, useful once you've got several attempts and want to tell them apart (e.g. "calm take", "angry take").
- **Drag a yellow marker** to shift its timing left or right, in case your recording landed slightly early or late — no need to re-record, just nudge it into sync. Dragging is clamped so takes can't overlap each other.
- **Crop a take's edges** — grab the small handles at the left/right edge of a yellow marker to trim recorded silence off the start or end. This doesn't discard any audio — it just adjusts what portion of the recording gets used, so you can always drag a crop back out if you cut too much.
- **Play a take** to hear it synced against the original video, played back at low (not muted) volume, so you can judge timing and delivery against the real footage.
- Delete any take you don't want.

### Previewing
- **Preview full dub** plays through the entire video, automatically swapping to each take's audio during its marked region and back to the original audio in between — a live simulation of the final export, useful for a last check before rendering.

### Exporting
- **Render dubbed clip (.webm)** — produces a full video file with your takes mixed into the audio track, muxed with the original video frames.
- **Export audio only** — for handing the mix off to another editor:
  - **.wav** — uncompressed, lossless, universally compatible.
  - **.mp3** — compressed (192kbps), smaller file size, encoded entirely in your browser.

### Projects (save/resume your work)
- **Save project** produces a `.dubproj` file (a renamed zip) containing your take recordings, their timing/crop data, and take names — but *not* the original video itself (that would make the file huge).
- **Load project** reopens a `.dubproj` file. Since the video itself isn't stored, you'll be asked to **relink** it — just reselect the same source file, and everything (takes, timing, crops, names) snaps back into place. If the file doesn't match by name/size, you'll get a warning but it'll still load.

### Language
- Full **English / Turkish** interface toggle in the top-right (button shows the *other* language you can switch to). It auto-detects your browser's language on first load and remembers your choice after that.

---

## Practical tips

- **Zoom in before recording tight dialogue.** At the default "fit" zoom on a long clip, a half-second region can be hard to select accurately — zoom in first.
- **Use the crop handles instead of re-recording** whenever a take just has a bit of dead air at the start or end. It's much faster than doing another take.
- **Preview the full dub before exporting** — the render step (especially for longer videos) takes real time since it plays through the video in real time to capture it; catching a bad edit at the preview stage saves you from redoing an export.
- **If you only need audio, skip the video export.** The WAV/MP3 export renders near-instantly (no real-time playback needed) since there's no video to mux.
- **Save your project regularly** if you're doing a long dubbing session — takes, crops, and names are only safe once written to a `.dubproj` file.

## Known limitations

- Video export produces `.webm`, not `.mp4` — this is a browser (`MediaRecorder`) limitation. If you need `.mp4`, use the WAV/MP3 audio export and remux with your original video in another tool.
- YouTube links are not supported — browsers can't access YouTube's audio stream directly. Download the file locally first (e.g. with `yt-dlp`) and load it as a regular video file.
- Everything runs in your browser tab — closing the tab loses unsaved work. Save your project before closing if you want to come back to it.


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
