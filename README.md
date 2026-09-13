# Loyiha Kartalari

Tasodifiy IT loyiha g'oyalari generatori — hech kim hali qilmagan 56 ta original loyiha g'oyasidan iborat, "yopiq karta" ko'rinishidagi interaktiv sayt.

**Jonli demo:** https://claude.ai/code/artifact/9109dbfb-a69a-4430-8a5f-17df921ce77d

## Qanday ishlaydi

- Butun sahifa bo'ylab 4 qatorda yopiq kartalar chapga/o'ngga uzluksiz aylanib yuradi
- Istalgan kartani bossangiz — tasodifiy bitta loyiha g'oyasi ochiladi
- Har bir g'oya uchun: nomi, qisqa tavsifi, qiyinlik darajasi (Oson / O'rta / Qiyin) va kerakli texnologiyalar (teglar) ko'rsatiladi
- **Kalitlar** — bosilganda ochiladigan tayyor so'rovlar:
  - `$ ai --ask` — AI'dan (ChatGPT, Claude va h.k.) loyiha haqida to'liq ma'lumot, MVP funksiyalari va boshlash rejasini so'rash uchun tayyor matn
  - `$ google --search` — Google'da mavjud yechimlar va raqobatchilarni qidirish uchun tayyor so'rov
  - Ikkalasini ham bir bosishda nusxalash mumkin
- **Tanaffus vaqti** — karta ochilgach, keyingi kartani tortish uchun qiyinlik darajasiga qarab kutish talab qilinadi:
  - Oson → 1.5 soat
  - O'rta → 2 soat
  - Qiyin → 3 soat
  
  Bu holat brauzerning `localStorage`'ida saqlanadi — sahifani yangilash yoki qayta ochish tanaffusni buzmaydi.

## Dizayn

Sayt "dasturchi terminali" uslubida qurilgan: och krem fon, nuqtali panjara, yagona JetBrains Mono shrifti. Natija haqiqiy terminal chiqishi (`$ karta --draw`) kabi, teglar `#hashtag` uslubida, tugmalar esa `yana_tort()` kabi funksiya chaqiruvlariga o'xshatib yozilgan.

## Texnologiyalar

Toza HTML, CSS va vanilla JavaScript — hech qanday freymvork yoki qurish (build) jarayoni yo'q. Shrift Google Fonts orqali ulanadi.

## Ishga tushirish

`index.html` faylini istalgan brauzerda oching — server yoki o'rnatish shart emas.

```bash
xdg-open index.html   # Linux
```

## Loyihaga g'oya qo'shish

`index.html` ichidagi `PROJECTS` massiviga yangi obyekt qo'shing:

```js
{ name: "Loyiha nomi", difficulty: "Oson" | "O'rta" | "Qiyin", desc: "Qisqa tavsif.", tags: ["Tag1", "Tag2"] }
```
