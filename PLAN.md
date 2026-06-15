# 🚀 AI Auto-Prompter Protocol (The Master Plan)

> **YAPAY ZEKA İÇİN KESİN TALİMAT:** 
> Bu projeyi kodlarken asla tüm siteyi tek bir adımda (single-shot) oluşturmaya çalışma. Bu durum "Context Bloat" (Bağlam Şişkinliği) ve odak kaybı yaratır. Aşağıdaki **"Yinelemeli Otonom İş Akışı" (Iterative Autonomous Workflow)** protokolünü harfiyen uygulayacaksın.

## ⚙️ Çalışma Prensibi (Sistem Nasıl İşler?)

Kullanıcı seni bu projeye atadığında ve bu dosyayı (PLAN.md) referans gösterdiğinde şu adımları izleyeceksin:

1. **Brifing ve Analiz İste (Aksiyon Bekleme):** Kullanıcıdan şirketin adını, ne iş yaptığını ve eğer varsa şirkete ait fotoğrafları (mekan, ürün vs.) sisteme yüklemesini iste.
2. **Görsel ve Tema Analizi:** Kullanıcı fotoğrafları yüklediğinde görsel analiz (Vision) yeteneklerini kullanarak o fotoğraflardan şirketin renk paletini, ışık tarzını ve ruhunu çıkart.
3. **Master Planı Çiz:** Analiz bittikten sonra projeyi 5 mantıksal aşamaya böl (Aşağıdaki standart şablonu kullan).
4. **Auto-Prompter Modu (Kritik Adım):** Aşama 1'i kodlamaya **BAŞLAMA**. Önce Aşama 1 için kendinin uygulayacağı çok detaylı, profesyonel bir "İcraat Prompt'u" yaz ve kullanıcıya sun.
5. **Onay Bekle:** Kullanıcı sadece **"Çalıştır"** veya **"Onaylıyorum"** diyene kadar bekle.
6. **İcraat ve Döngü:** Kullanıcı onay verince Aşama 1'i kodla (AGENT_INSTRUCTIONS.md kurallarına uyarak). İşlem bitince Aşama 2'nin promptunu üret ve tekrar onay bekle.

---

## 🏗️ Standart 5 Aşamalı Mimari Planı

*   **Aşama 1: UI/UX Tasarım Sistemi (ux-ui-pro-max)** 
    *   *Hedef:* Global CSS, fontlar, renk paleti (analiz edilen renklere göre), Header ve Footer bileşenlerinin `src/components/ui/` içine kurulması.
*   **Aşama 2: Apple Scroll ve Animasyon (Hareket Katmanı)**
    *   *Hedef:* Lenis Smooth Scroll kurulumu ve `src/components/animations/` içerisine GSAP ScrollTrigger kurallarının yazılması.
*   **Aşama 3: 3D WebGL ve İnteraktif Ortam**
    *   *Hedef:* Şirketi yansıtan 3D objelerin (Three.js/Fiber) `src/components/webgl/` içine eklenmesi ve sayfayla entegrasyonu.
*   **Aşama 4: Backend, Veritabanı ve İş Mantığı**
    *   *Hedef:* Prisma şemalarının oluşturulması, API rotaları ve form/rezervasyon sistemlerinin `src/lib/db/` içerisine yazılması.
*   **Aşama 5: İletişim ve SEO Cilası**
    *   *Hedef:* Resend ile onay maillerinin ayarlanması, Next.js dinamik meta etiketleri ve Lighthouse hız optimizasyonları.

---

## 🎯 Ajan Başlatma Tetikleyicisi (Trigger)

**Sevgili AI Ajanı:** Eğer bu dosyayı okuduysan, protokolü anladığını belirtmek için kullanıcıya sadece şu cümleyi kur ve bekle:
*"Sistem anlaşıldı. Şirket bilgilerini, mekan/ürün fotoğraflarını ve vizyonunuzu bekliyorum Patron!"*
