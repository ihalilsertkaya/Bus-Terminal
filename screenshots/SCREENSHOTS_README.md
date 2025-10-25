# Ekran Görüntüleri Rehberi

Bu klasör projenin ekran görüntülerini içerir.

## Ekran Görüntülerini Oluşturma

Uygulamanın ekran görüntülerini almak için aşağıdaki adımları izleyin:

### 1. Uygulamayı Çalıştırın

```bash
./mvnw javafx:run
```

### 2. Gerekli Ekran Görüntüleri

Aşağıdaki ekranların görüntülerini alın:

#### a) Giriş Ekranı (`giris-ekrani.png`)
- Uygulama başladığında açılan ilk ekran
- Kullanıcı adı ve şifre alanları görünür olmalı
- Yazhane seçim combobox'ı görünür olmalı
- **Boyut önerisi:** 1200x800px

#### b) Karşılama Ekranı (`splash-screen.png`)
- Başarılı giriş sonrası gösterilen splash screen
- Progress bar animasyonu görünür olmalı
- Hoşgeldiniz mesajı okunabilir olmalı
- **Boyut önerisi:** 800x600px

#### c) Ana Panel (`ana-panel.png`)
- Yetkili ana ekranı (YetkiliController)
- Tüm sekmeler görünür olmalı (Sefer Ekle, Bilet Ekle, İstatistik)
- Tablolarda bazı örnek veriler olmalı
- **Boyut önerisi:** 1400x900px

#### d) Koltuk Seçimi - 40 Koltuk (`koltuk-secimi-40.png`)
- 40 koltuklu otobüs düzeni
- Bazı koltuklar dolu olarak işaretlenmiş olmalı
- Erkek (mavi) ve kadın (pembe) renkleri görünür olmalı
- **Boyut önerisi:** 600x800px

#### e) Koltuk Seçimi - 46 Koltuk (`koltuk-secimi-46.png`)
- 46 koltuklu otobüs düzeni
- Bazı koltuklar dolu olarak işaretlenmiş olmalı
- Erkek (mavi) ve kadın (pembe) renkleri görünür olmalı
- **Boyut önerisi:** 600x900px

#### f) Bilet Ekranı (`bilet-ekrani.png`)
- Oluşturulan bilet görüntüsü
- Yolcu bilgileri, sefer bilgileri görünür olmalı
- Barkod görseli görünür olmalı
- Koltuk numarası belirtilmiş olmalı
- **Boyut önerisi:** 500x700px

#### g) İstatistik Paneli (`istatistik.png`)
- İstatistik sekmesi açık
- Tabloda seferlere göre cinsiyet analizi görünür olmalı
- Örnek verilerle dolu olmalı
- **Boyut önerisi:** 1200x700px

### 3. Ekran Görüntüsü Alma İpuçları

#### Windows
- **Tam Ekran:** `Win + PrtScr` veya `PrtScr` tuşu
- **Pencere:** `Alt + PrtScr`
- **Özel Bölge:** `Win + Shift + S` (Snipping Tool)

#### macOS
- **Tam Ekran:** `Cmd + Shift + 3`
- **Pencere:** `Cmd + Shift + 4` sonra `Space`
- **Özel Bölge:** `Cmd + Shift + 4`

#### Linux
- **GNOME:** `PrtScr` veya `Shift + PrtScr`
- **Araç:** GNOME Screenshot, Flameshot, Spectacle

### 4. Görüntü Düzenleme

Ekran görüntülerini almadan önce:

1. **Test Verileri Oluşturun**
   - Veritabanına örnek seferler ekleyin
   - Birkaç bilet oluşturun
   - Farklı cinsiyetlerde yolcular ekleyin

2. **Pencere Boyutunu Ayarlayın**
   - Uygulamayı uygun boyutta açın
   - Tüm önemli öğeler görünür olmalı
   - Çok fazla boşluk bırakmayın

3. **Görüntüyü Düzenleyin**
   - PNG formatında kaydedin
   - Gerekirse kırpın
   - Hassas bilgileri (gerçek TC numaraları vb.) bulanıklaştırın
   - Boyutu optimize edin (ideal 200-500KB arası)

### 5. Dosya Adlandırma

Dosyaları tam olarak README.md'de belirtildiği gibi adlandırın:
- `giris-ekrani.png`
- `splash-screen.png`
- `ana-panel.png`
- `koltuk-secimi-40.png`
- `koltuk-secimi-46.png`
- `bilet-ekrani.png`
- `istatistik.png`

### 6. Alternatif: Otomatik Ekran Görüntüsü

JavaFX'te otomatik ekran görüntüsü almak için:

```java
import javafx.scene.image.WritableImage;
import javafx.scene.SnapshotParameters;
import javafx.embed.swing.SwingFXUtils;
import javax.imageio.ImageIO;
import java.io.File;

// Bir Scene'in ekran görüntüsünü al
WritableImage snapshot = scene.snapshot(null);
File file = new File("screenshots/screenshot.png");
ImageIO.write(SwingFXUtils.fromFXImage(snapshot, null), "png", file);
```

## Örnek Veriler

Ekran görüntüleri için önerilen test verileri:

### Yetkili (Kullanıcı)
- Kullanıcı Adı: `admin`
- Şifre: `admin123`

### Seferler
1. Ankara - İstanbul, 09:00
2. İzmir - Antalya, 14:30
3. Bursa - Ankara, 18:00

### Yolcular
1. Ahmet Yılmaz (Erkek, 35)
2. Ayşe Demir (Kadın, 28)
3. Mehmet Kaya (Erkek, 42)
4. Fatma Şahin (Kadın, 31)

## Kalite Kontrol

Ekran görüntülerini yüklemeden önce kontrol edin:

- [ ] Tüm 7 ekran görüntüsü mevcut
- [ ] Dosya adları doğru
- [ ] PNG formatında
- [ ] Okunabilir çözünürlük (minimum 800px genişlik)
- [ ] Hassas bilgiler gizlenmiş
- [ ] Dosya boyutu makul (her biri < 1MB)
- [ ] Ekran görüntüleri profesyonel görünüyor

## Notlar

- Ekran görüntülerini alırken karanlık tema kullanıyorsanız, uygulama stiliyle uyumlu olacaktır
- Eğer veritabanı bağlantısı yoksa, önce veritabanını kurun
- Mock veriler kullanıyorsanız, gerçekçi görünmesine dikkat edin
- GitHub'da gösterilecekse, light background kullanın

---

**Bu dosyayı silmeyin!** Gelecekte ekran görüntülerini güncellemek isteyenler için yararlı olacaktır.
