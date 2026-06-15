# 🤖 AI Agent & Orchestrator Boundaries (Conflict Prevention)

> **ZORUNLU OKUMA:** Bu proje, AI ajanlarının (Antigravity vb.) kod tabanında çakışma (conflict) yaratmasını engellemek için katı bir **Feature-Sliced Design (FSD)** izolasyon mimarisi kullanmaktadır.

Bir Yapay Zeka ajanı olarak bu projede çalışırken **AŞAĞIDAKİ KURALLARI ASLA İHLAL EDEMEZSİNİZ:**

## 1. Dizin ve Sorumluluk Sınırları (Klasör İzolasyonu)

Ajanların aynı dosyada çakışmaması için her yetenek paketi (Skill) kendi klasörüne hapsedilmiştir:

*   **`src/components/ui/`**: **SADECE** basit arayüz bileşenleri (Tailwind, Shadcn) buraya yazılacaktır. Bu klasöre KESİNLİKLE Three.js, GSAP veya veritabanı kodu eklenemez.
*   **`src/components/webgl/`**: **SADECE** 3D WebGL mantığı (`@react-three/fiber`, modeller) buraya eklenecektir. Bu bileşenler ağır olduğu için her zaman ana sayfalarda `next/dynamic` ile asenkron yüklenmelidir (Lazy load).
*   **`src/components/animations/`**: **SADECE** GSAP ScrollTrigger kuralları ve Lenis sarmalayıcıları (wrappers) buraya eklenecektir.
*   **`src/lib/db/`**: **SADECE** Prisma ve veritabanı (PostgreSQL) işlemleri burada barınır. Asla UI katmanına taşınamaz.

## 2. İkili-Motor (Dual-Engine) Kuralı

Eğer kullanıcı karmaşık bir istekte bulunursa (Örn: "Veritabanına kayıt yapan dönen bir 3D buton yap"), kodu tek bir devasa `page.tsx` içine **YAZAMAZSINIZ**. Görevi bölmek zorundasınız:
1.  Görsel 3D obje `webgl` içine.
2.  GSAP rotasyon animasyonu `animations` içine.
3.  Veritabanı API isteği `lib/db` içine.
Son olarak bu parçalar `page.tsx` içinde birleştirilir.

## 3. Kod Düzenleme Kısıtlamaları
Kodu değiştirirken tüm dosyayı baştan yaratıp ezmeyin. Sadece değişmesi gereken bloğu (AST Node veya hedef satır aralığını) hedefleyerek yama (Patch) yapın. Aksi takdirde diğer ajanın yazdığı kodları silersiniz.

## 4. Paket Yönetimi
Kullanıcı onaylamadan asla kendi başınıza `npm install` ile paket versiyonu yükseltmeyin veya düşürmeyin. Yeni bir teknoloji kurulacaksa daima `package.json` içindeki React ve Next.js peer-dependency kısıtlamalarına uyun.
