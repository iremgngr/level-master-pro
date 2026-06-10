# Level Master Pro 🚛 Eğim ve Güvenlik Otomasyon Sistemi / Tilt & Safety Automation System

<p align="center">
  <a href="#-türkçe-dokümantasyon">🇹🇷 Türkçe Dokümantasyon</a> | 
  <a href="#-english-documentation">🇺🇸 English Documentation</a>
</p>

---

## 🇹🇷 Türkçe Dokümantasyon

**Level Master Pro**, endüstriyel damperli araçlar ve tır lojistiği için geliştirilmiş, ESP32 mimarisi ve MPU6500 6-eksenli ivmeölçer/jiroskop tabanlı kapalı devre bir **kablosuz telemetri ve güvenlik sistemidir**. 

Bu proje; donanım entegrasyonu, gömülü yazılım sinyal işleme algoritmaları ve modern web teknolojilerini bir araya getiren endüstriyel bir Nesnelerin İnterneti (IoT) başyapıtıdır.

> 🔒 **Fikri Mülkiyet Bilgilendirmesi:** Bu proje ticari bir ürün olarak geliştirildiğinden, kaynak kodları (C++ / HTML5) kamuya kapalıdır. Bu depoda projenin mimarisi, mühendislik yaklaşımları ve telemetri çıktıları belgelenmiştir.

### 📺 Canlı Ürün Demosu (Geliştirici Sürümü)
Sistemin şantiye sarsıntılarını sönümleme kararlılığı ve kritik limit aşımında sürücüyü uyaran anlık renk geçiş mimarisi:

![Safety Alarms Demo](safety-alarms.gif)

### 🛠️ Teknolojik Altyapı (Tech Stack)
* **Mikrodenetleyici & Ağ:** ESP32 (Asynchronous Web Server, WiFi Access Point, DNS Captive Portal Server).
* **Donanım & Haberleşme:** MPU6500 İvmeölçer, I2C Protokolü, Kalıcı Hafıza Yönetimi (Preferences/EEPROM).
* **Ön Yüz (UI/UX):** Vanilla JavaScript (AJAX/Fetch API, JSON Parsing), SVG Grafik Matematik Haritalama, CSS Grid & Flexbox, Cross-Browser Mobile Engine Optimization.

### 🧠 Öne Çıkan Mühendislik Çözümleri
1. **Yazılımsal Sinyal Sönümleme (Moving Average Filter):** Tır motorunun yüksek rölanti titreşimleri ve şantiye sarsıntıları, sensörden gelen ham verilerde gürültülere yol açar. Bunu engellemek için gömülü yazılım tarafında **20 elemanlı Hareketli Ortalama Filtresi** kurulmuştur. Sistem her 250ms'de bir güncel 20 ölçümün ortalamasını alarak stabil bir veri akışı sunar.
2. **Akıllı Güvenlik ve Dinamik Eşik Yönetimi:** Sürücü, kabin içindeki dijital paneli kullanarak limitleri anlık güncelleyebilir. Belirlenen bu limitler ESP32'nin flash hafızasına kalıcı olarak işlenir.
   
   ![Dynamic Limits Demo](dynamic-limits.gif)
   
3. **Sıfır Yapılandırma Ağ Yönetimi (Captive Portal):** İnternete ihtiyaç duymadan lokal bir Access Point ağı yayınlar. DNS sunucusu sayesinde tarayıcıya girilen herhangi bir adres otomatik olarak cihazın arayüzüne yönlendirilir.

### 📱 Arayüz Durum Yönetimi (UI State Management)
| Sistem Durumu: Kararlı / Güvenli Operasyon | Ağ Bağlantısı Kesildiğinde (Hata Yakalama) |
|:---:|:---:|
| ![Dashboard Normal](dashboard-normal.png) | ![Dashboard Disconnected](dashboard-disconnected.png) |

### 🎛️ Donanım ve Başlatma Logları (Serial Monitor)
![Terminal Logs](terminal-log.png)

---

## 🇺🇸 English Documentation

**Level Master Pro** is a closed-loop **wireless telemetry and safety system** developed for industrial dump trucks and heavy-duty logistics, powered by the ESP32 architecture and MPU6500 6-axis accelerometer/gyroscope.

This project stands out as an industrial IoT masterpiece that merges hardware integration, embedded signal processing algorithms, and responsive modern web technologies.

> 🔒 **Intellectual Property Notice:** Since this project was developed as a commercial product, the source codes (C++ / HTML5) are kept private. This repository serves as documentation for the system architecture, engineering methodologies, and telemetry outputs.

### 📺 Live Product Demo (Developer Edition)
Demonstration of signal stabilization against site vibrations and the real-time color-coded warning system when critical limits are breached:

![Safety Alarms Demo](safety-alarms.gif)

### 🛠️ Tech Stack
* **Microcontroller & Networking:** ESP32 (Asynchronous Web Server, WiFi Access Point, DNS Captive Portal Server).
* **Hardware & Communication:** MPU6500 Accelerometer, I2C Protocol, Non-Volatile Memory Management (Preferences/EEPROM).
* **Frontend (UI/UX):** Vanilla JavaScript (AJAX/Fetch API, JSON Parsing), SVG Graphical Math Mapping, CSS Grid & Flexbox, Cross-Browser Mobile Engine Optimization.

### 🧠 Core Engineering Solutions
1. **Software Signal Smoothing (Moving Average Filter):** High-frequency vibrations from heavy machinery corrupt raw sensor data. To prevent visual flickering on the driver's screen, a **20-element Moving Average Filter** was implemented in the firmware, serving an analog-like smooth data flow.
2. **Smart Safety & Dynamic Threshold Management:** Drivers can instantly update Pitch and Roll thresholds via the digital panel. These limits are stored permanently inside the ESP32's flash memory.
   
   ![Dynamic Limits Demo](dynamic-limits.gif)
   
3. **Zero-Configuration Network (Captive Portal):** Broadcasts a local Access Point network without requiring internet. Built-in **DNS Hijacking** intercepts any browser request and redirects the user directly to the device interface.

### 📱 UI State Management
| System Status: Stable / Safe Operation | Connection Lost (Error Handling) |
|:---:|:---:|
| ![Dashboard Normal](dashboard-normal.png) | ![Dashboard Disconnected](dashboard-disconnected.png) |

### 🎛️ Hardware Initialize & Telemetry Logs (Serial Monitor)
![Terminal Logs](terminal-log.png)

---

## 📈 Sürüm ve Üretim / Production Info
* **Geliştirici Sürümü / Developer Ed. (v2.1):** Active telemetry panel for raw X, Y, Z G-Force visualization.
* **Endüstriyel Üretim / Industrial Ed. (v2.2):** Clean, distraction-free interface optimized for fleet operations.

**Geliştirici / Developer:** Computer Engineering Graduate  
**Kurumsal Altyapı / Corporate Infrastructure:** Odikon Elektronik&reg;