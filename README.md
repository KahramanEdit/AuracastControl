📄 AuracastControl – Yeni README Taslağı

```markdown
# AuracastControl

**RedMagic 11 Pro** için **Auracast (LE Audio Broadcast)** yayınlarını başlatma, durdurma ve yönetme modülü.  
**KernelSU** tabanlıdır; hem **WebUI** hem de **komut satırı** arayüzü sunar.

## Ne İşe Yarar?

RedMagic OS (Nubia), donanım desteklemesine rağmen Auracast arayüzünü yazılımsal olarak kaldırmıştır. Bu modül, gizli Bluetooth Binder/API'lerine doğrudan erişerek bu engeli aşar ve şunları yapmanıza olanak tanır:

- Auracast yayınını **başlat / durdur**
- Yayın kodu ve metadata bilgisini **ayarlama**
- Mevcut Auracast yayınlarını **tarama**
- JBL Headphones gibi uyumlu cihazlarla **entegrasyon**

## Özellikler

- ✅ **Kullanıcı dostu WebUI** – Tarayıcı üzerinden kolay kontrol
- ✅ **Komut satırı desteği** – Termux veya adb shell ile yönetim
- ✅ **Yayın kodu belirleme** – Güvenli bağlantı için özel kod
- ✅ **Metadata düzenleme** – Yayın adı, dil vb. bilgiler
- ✅ **JBL Headphones tetikleme** – Kulaklık uygulamasını otomatik olarak Auracast tarama moduna geçirir
- ✅ **Kalıcı ayarlar** – Yapılandırma `/data/adb/` altında saklanır

## Kurulum

1. ZIP dosyasını indirin.
2. **KernelSU** uygulamasını açın.
3. **Modüller** sekmesine gidin.
4. **Yükle**'ye dokunun ve ZIP dosyasını seçin.
5. Cihazınızı **yeniden başlatın**.
6. KernelSU → Modüller → **AuracastControl** üzerine dokunarak WebUI'yi açın.

## WebUI Kullanımı

WebUI arayüzünde şunları yapabilirsiniz:
- Yayın durumunu görüntüleme
- Yayın başlatma / durdurma düğmeleri
- Yayın kodu girme
- Metadata alanlarını düzenleme
- Tarama sonuçlarını listeleme

## Komut Satırı Kullanımı (Termux / adb shell)

Aşağıdaki komutlar root yetkisi gerektirir:

```bash
su
# Yayın başlatmak için
auracast start

# Yayın durdurmak için
auracast stop

# Yayın kodu belirlemek için
auracast code 1234

# Metadata ayarlamak için
auracast metadata '{"program_info":"Termux Auracast","language":"tr"}'
```

Not: Komut adları örnek olarak verilmiştir; modülün gerçek script'i farklı isimlendirme kullanıyor olabilir. Lütfen /data/adb/modules/AuracastControl/ dizinindeki script dosyasını kontrol edin.

Teknik Detaylar

Bu modül, aşağıdaki sistem bileşenlerini kullanır:

· android.bluetooth.IBluetoothManager Binder servisi
· ServiceManager.getService("bluetooth_manager") erişimi
· Gizli IBluetooth arayüzü ve startLeAudioBroadcast metodu
· android.bluetooth.action.LE_AUDIO_BROADCAST_STATE_CHANGED intent'i
· JBL Headphones uygulamasının Auracast ekranını tetikleme

Bu nedenle modül, yalnızca root erişimi olan cihazlarda çalışır ve sistem seviyesinde değişiklikler yapar.

Ekran Görüntüleri

Screenshot_20260901_141518.jpg

Screenshot_20260901_141525.jpg

Screenshot_20260901_141532.jpg

Uyumluluk

· Test edilen cihaz: RedMagic 11 Pro
· Gereksinim: KernelSU root, Android 13 veya üzeri
· Diğer cihazlar: Test edilmemiştir, donanım/yazılım farklılıkları olabilir.

Uyarı ve Sorumluluk Reddi

KULLANIM RİSKİ SİZE AİTTİR.

· Bu modül, düşük seviyeli Bluetooth sistem servislerine müdahale eder.
· Yükleme ve kullanma sonucunda cihazınızda işlev kaybı, kararsızlık veya başka sorunlar oluşabilir.
· Geliştirici hiçbir zarardan sorumlu tutulamaz.
· Bu proje eğitim ve araştırma amaçlıdır.

Yüklemeden önce mutlaka yedek alın.

```

---

## 🛠️ Nasıl Uygulanır?

1. GitHub'da **AuracastControl** deposuna git.
2. `README.md` dosyasını aç.
3. Kalem ikonuna tıklayarak düzenleme moduna geç.
4. Yukarıdaki tüm içeriği kopyalayıp **mevcut README'nin yerine yapıştır**.
5. En alttaki **Commit changes** butonuna bas.

---

Bu README hem kullanıcılar hem de yapay zekâlar için yeterince bilgilendirici ve anahtar kelime açısından zengin. Dilersen içindeki komut satırı örneklerini gerçek script adlarına göre düzeltebilirim.

Başka bir adımda yardım ister misin? (Örneğin repo description güncellemesi veya sosyal medya tanıtımı)
