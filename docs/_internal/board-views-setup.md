# Caner için — GitHub Projects Board Views Kurulum Rehberi

Selam Caner. Sunum bugün (19 Mayıs). Board üzerinde 5 view oluşturman lazım — GitHub'da elle yapılması gereken tek iş bu, gerisi otomatik kuruldu. **Toplam süre: 10-15 dakika.**

Her adım aşağıda yazılı. Sırayla git, atlama.

---

## Başlamadan önce

### 1. Yetki kontrolü

Sana project'e WRITER yetkisi verildi (Kaan ekledi, doğrulandı). Yani view oluşturabilir + ayarlayabilirsin.

### 2. Project URL

**https://github.com/users/kaanzapkinus/projects/2**

Aç. Üst kısımda "Brickly Project Board" başlığı var. Hemen altında bir tab göreceksin: muhtemelen "**View 1**" diye duruyor. Yanında küçük bir **`+`** ikonu var — yeni view eklemek için kullanacağız.

### 3. Genel UI mantığı

GitHub Projects v2'de view yapılandırma:
- Mevcut bir view'ın **adını çift tıklayarak** veya **yanındaki `▾` oka tıklayıp "Rename"** ile değiştirirsin.
- Sağ üstte **filtre çubuğu** + **`...` (üç nokta)** menüsü var. `...` → "**Group by**", "**Sort**", "**Fields**" gibi seçenekler buradan açılır.
- Veya alttaki **toolbar**'da `Group`, `Sort`, `Filter`, `Slice` butonları görülebilir.
- Değişiklik yaptıkça **sağ üstte mavi "Save changes" butonu** belirir — bu önemli, kaydetmeyi unutma. Aksi halde sayfa kapanınca değişiklikler gider.

> **Önemli:** Auto-save YOK. Her view ayarını değiştirdikten sonra "Save changes" → tıkla.

---

## VIEW 1: Sprint Board — mevcut "View 1"'i düzenle

### Niye gerekli
Klasik Kanban — Status sütunlarına bölünmüş (Todo / In Progress / Done). Sunumun "günlük çalışma" görünümü.

### Adımlar

1. Mevcut **"View 1"** tab'ına tıkla. Halihazırda açık olmalı.
2. Tab adının yanındaki **`▾`** okuna tıkla → açılan menüden **"Rename"** seç.
3. Yeni adı yaz: **`Sprint Board`** → Enter.
4. Sağ üstte **`...` (üç nokta)** menüsü → **"Group by"** → açılan listeden **`Status`** seç.
   - Eğer Status zaten seçiliyse, dokunma.
5. Sağ üstte **`...`** → **"Sort"** → 
   - **First sort:** `Priority` → `Descending` (yüksek priority önce)
   - **Add sort:** `Due Date` → `Ascending` (yakın tarih önce)
6. Sağ üstte **`Save changes`** butonu çıkarsa tıkla.

### Doğrulama (ne görmelisin)
- 4-5 sütun: **Todo** (27 issue), **In Progress** (boş), **Blocked** (boş), **In Review** (boş), **Done** (28 issue)
- Her sütundaki kartlar Critical/High/Medium/Low sırasına göre dizili
- Aynı priority içinde, due date'i yakın olan üstte

---

## VIEW 2: Timeline / Gantt — EN ÖNEMLİ VIEW

### Niye gerekli — sunumun hero'su
Bu view, sunumdaki **en kritik görsel**. PMBOK 5 fazının renkli Gantt çubukları görünür. Kaan demo'da "şimdi Timeline view'a geçiyoruz" deyip bu view'ı açacak. Hoca buna bakacak.

### Adımlar

1. View tab'larının yanındaki **`+`** ikonuna tıkla.
2. Açılan "New view" panelinde **"Roadmap"** seç → **"Create"** tıkla.
3. Yeni view açılır. Üstteki yeni tab'ın adını **çift tıkla** veya `▾` → "Rename" → **`Timeline / Gantt`** yaz, Enter.
4. Sağ üstte **`...` (üç nokta)** menüsü açılır.
5. **`Group by`** → **`Phase`** seç. (5 yatay band oluşacak: Phase 1 Initiation, Phase 2 Planning, vb.)
6. **`Date fields`** (Roadmap-spesifik) →
   - **Start date:** **`No date field`** veya boş bırak — bizim issue'larımızda sadece due date var.
   - **Target date:** **`Due Date`** seç.
7. **Zoom level** (sağ üstte): **`Day`** seç. (Default `Month` olabilir, day'e çek.)
8. **`Save changes`** → tıkla.

### Doğrulama (ne görmelisin)
- Yatay zaman ekseni: solda 5 Mayıs, sağda 18 Mayıs civarı görünmeli
- 5 yatay band, her biri bir PMBOK fazı:
  - **Phase 1 — Initiation** (5 Mayıs civarı, 6 çubuk)
  - **Phase 2 — Planning** (6-8 Mayıs, 15 çubuk)
  - **Phase 3 — Execution** (11-15 Mayıs, 25 çubuk)
  - **Phase 4 — Monitoring** (5-18 Mayıs, dağılmış 4 çubuk)
  - **Phase 5 — Closure** (18 Mayıs, 5 çubuk)
- Çubukların rengi otomatik (GitHub belirler)
- Bir çubuğa tıklayınca o issue açılır

> Bu görünüm hoca için en görsel artefakt. Yamuk durmasın diye dikkatli yapılandır.

---

## VIEW 3: Master Backlog (Table layout)

### Niye gerekli
Tablo görünümü — 55 issue + tüm custom field'lar yan yana. Sunumda "detayın yaşadığı yer" diye gösteriyoruz. Hoca burada effort hours, priority, due date sütunlarını görür.

### Adımlar

1. View tab'larının yanındaki **`+`** → **"Table"** → **"Create"**.
2. Tab adını **`Master Backlog`** yap.
3. Sağ üstte **`...`** → **`Group by`** → **`Milestone`** seç.
4. **`...`** → **`Sort`** →
   - **First:** `Phase` → `Ascending`
   - **Add:** `Priority` → `Descending`
5. **`...`** → **`Fields`** (görünür sütunları seç) → şu sütunlar **işaretli** olsun:
   - ✓ Title
   - ✓ Assignees
   - ✓ Status
   - ✓ Priority
   - ✓ Effort (hours)
   - ✓ Phase
   - ✓ Sprint
   - ✓ Due Date
   - ✓ Milestone
   - ✓ Labels
6. **`Save changes`** → tıkla.

### Doğrulama (ne görmelisin)
- 5 grup başlığı: "Phase 1 — Initiation (6)", "Phase 2 — Planning (15)", vb.
- Her grup açılıp kapanabilir (sol başlarındaki `▾` ile)
- 10+ sütun yan yana
- Sıralama: önce Phase ascending, sonra Priority descending (Critical → Low)

---

## VIEW 4: By Assignee (Board layout, group by Assignees)

### Niye gerekli
"Sorumlulukları nasıl böldünüz?" sorusunun cevabı bu view'da. İki sütun yan yana: kaanzapkinus + Canerakcasu. Hoca tek bakışta iş bölümünü görüyor.

### Adımlar

1. **`+`** → **"Board"** → **"Create"**.
2. Tab adını **`By Assignee`** yap.
3. Sağ üstte **`...`** → **`Group by`** → **`Assignees`** seç.
4. **`...`** → **`Sort`** → **`Priority`** → **`Descending`**.
5. **`Save changes`** → tıkla.

### Doğrulama
- 2 ana sütun: **kaanzapkinus**, **Canerakcasu**
- (Belki "No assignees" diye 3. sütun da olabilir — eğer varsa o sütun boş olmalı)
- Kaan sütununda: çoğunlukla `type: docs`, `type: design`, `type: frontend` issue'ları
- Caner sütununda: çoğunlukla `type: backend`, `type: ai`, `type: testing` issue'ları
- **Both** assignment olan issue'lar her iki sütunda da görünür

---

## VIEW 5: PMBOK Phase View (Board layout, group by Phase)

### Niye gerekli
PMBOK framework alignment'ı tek ekranda. 5 sütun, her biri bir faz. Bu, "biz PMBOK methodology'sini gerçekten uyguladık" mesajının görsel ispatı.

### Adımlar

1. **`+`** → **"Board"** → **"Create"**.
2. Tab adını **`PMBOK Phase View`** yap.
3. Sağ üstte **`...`** → **`Group by`** → **`Phase`** seç.
4. **`...`** → **`Sort`** → **`Due Date`** → **`Ascending`**.
5. **`Save changes`** → tıkla.

### Doğrulama
- 5 sütun (soldan sağa):
  1. **1 - Initiation** — 6 kart
  2. **2 - Planning** — 15 kart
  3. **3 - Execution** — 25 kart
  4. **4 - Monitoring** — 4 kart
  5. **5 - Closure** — 5 kart
- Toplam: 6+15+25+4+5 = **55 kart** ✓
- Her sütundaki kartlar due date'e göre dizili

---

## SON ADIM: Tab sırası

Sunum demo flow'una göre tab'ların sırası önemli. Bunu da düzelt:

Olması gereken sıra (soldan sağa):

1. **Sprint Board** (default, ilk açılan)
2. **Timeline / Gantt** ← hero shot, demo'da 2. açılan
3. **PMBOK Phase View**
4. **Master Backlog**
5. **By Assignee**

### Tab sırasını nasıl değiştirilir
- Bir tab'a **sağ tıkla** → "Move left" / "Move right" çıkar
- Veya tab'ı **sürükle-bırak** ile yerine koy

---

## Bitince — kontrol checklist'i

5 view bittikten sonra şunları kontrol et:

- [ ] 5 view görünüyor (Sprint Board, Timeline / Gantt, Master Backlog, By Assignee, PMBOK Phase View)
- [ ] Tab sırası yukarıdaki gibi
- [ ] Timeline / Gantt'ta 5 renkli band görünüyor (Phase 1-5)
- [ ] Master Backlog'da 10+ sütun var ve milestone'a göre gruplanmış
- [ ] By Assignee'de 2 sütun yan yana (Kaan + Caner)
- [ ] PMBOK Phase View'de 5 sütun var ve toplam 55 kart
- [ ] Her view'ın sağ üstünde "Save changes" butonu **görünmüyor** (yani hepsi kaydedildi)

---

## Sorun çıkarsa

### "Group by Phase yok, sadece Status, Milestone, vb. var"
Custom field "Phase" projeye ekli ama görünmüyor olabilir. **`...`** → **`Fields`** kontrol et — "Phase" görünür mü? Değilse görünür yap.

### "Roadmap layout görünmüyor / yamuk duruyor"
- Tarayıcıyı yenile (Ctrl+F5).
- Date fields kontrol et — "Target date" `Due Date` mi?
- Zoom level "Day" mi? "Month" ise çubuklar üst üste binmiş gibi görünür.

### "Tab adı değişmiyor"
- **`▾`** dropdown'ından "Rename" yerine doğrudan tab adına çift tıkla.
- Veya tab adına sağ tıkla → "Rename".

### "Save changes butonu sürekli kalıyor"
- Tıkla. Save edilmediği için kalıyor. Save sonrası tab'ın yanında küçük bir mavi nokta `●` olmamalı.

### "Yetkim yok diyor"
- Kaan'a yaz, project Settings → Manage access'ten yetkin doğru ayarlanmış mı kontrol etsin (WRITER veya ADMIN olmalı).

---

## Bittiğinde

WhatsApp'tan Kaan'a yaz: **"5 view tamam, board hazır"**. Kaan provada sırayı kontrol edecek.

Bu son adımdı. Sonra sadece sunum prova ve gerçek sunum kaldı.

🧱 Brickly hazır.
