
# 📖 Laporan Jawaban Tugas Praktikum 2 – CSS Dasar

## **1. Eksperimen dengan Mengubah dan Menambahkan Properti CSS**

Pada praktikum ini dilakukan eksperimen dengan memodifikasi beberapa properti CSS untuk meningkatkan estetika tampilan web. Properti yang ditambahkan meliputi:

* **Background gradient**: memberikan transisi warna yang lebih dinamis dibandingkan warna solid.
* **Border-radius**: membuat sudut elemen lebih tumpul sehingga tampilan terlihat modern.
* **Box-shadow**: menambahkan efek bayangan untuk memberikan kesan kedalaman (3D).
* **Hover effect**: meningkatkan interaktivitas melalui perubahan tampilan saat elemen disentuh kursor.

**Contoh kode:**

```css
body {
    background: linear-gradient(180deg, #f9fbfd, #d7ebff);
}

#intro {
    background: #418fb1;
    border-radius: 10px;
    box-shadow: 0 5px 12px rgba(0,0,0,0.25);
    padding: 20px;
    color: white;
}

nav a:hover {
    background: #0B6B3A;
    transition: 0.3s;
}
```

📖 **Penjelasan:**
Modifikasi ini menunjukkan bahwa CSS tidak hanya berfungsi sebagai pengatur warna dan ukuran font, tetapi juga sebagai sarana untuk menciptakan *user experience* yang lebih menarik. Penggunaan `border-radius` dan `box-shadow` merupakan implementasi prinsip desain modern yang menekankan *soft edges* dan *visual depth*.

---

## **2. Perbedaan Deklarasi `h1 { ... }` dengan `#intro h1 { ... }`**

**Contoh kode:**

```css
h1 {
    color: red;
}
#intro h1 {
    color: blue;
}
```

**Contoh HTML:**

```html
<h1>Judul Umum</h1>
<div id="intro">
    <h1>Judul dalam Intro</h1>
</div>
```

📖 **Penjelasan:**

* Deklarasi `h1 { ... }` bersifat **global selector**, artinya berlaku untuk semua elemen `<h1>` di seluruh dokumen.
* Deklarasi `#intro h1 { ... }` merupakan **descendant selector**, artinya hanya berlaku untuk elemen `<h1>` yang berada di dalam elemen dengan `id="intro"`.

Secara teori, ini menunjukkan konsep *specificity* dalam CSS, di mana selector yang lebih spesifik (kombinasi ID + elemen) memiliki kekuatan lebih tinggi dibanding selector generik.

---

## **3. Prioritas CSS: Inline, Dan Internal CSS**

Urutan prioritas (CSS Cascading Order):

1. **Inline CSS** → prioritas tertinggi karena langsung melekat pada elemen HTML.
2. **Internal CSS** → berlaku hanya pada file HTML tertentu dan ditulis dalam tag `<style>`.
3. **Eksternal CSS** → prioritas terendah jika terjadi konflik, meskipun secara praktik lebih direkomendasikan karena rapi dan reusable.

**Contoh kode:**

```css
/* Eksternal CSS */
p { color: green; }

/* Internal CSS */
<style>
p { color: blue; }
</style>

/* Inline CSS */
<p style="color:red;">Ini paragraf</p>
```

📖 **Penjelasan:**
Jika ketiga jenis CSS tersebut diterapkan pada elemen yang sama, maka browser akan menampilkan gaya dari **inline CSS** karena memiliki tingkat prioritas paling tinggi. Hal ini sesuai dengan prinsip *cascade* dalam CSS, di mana konflik antar deklarasi diselesaikan dengan mempertimbangkan **specificity dan order of importance**.

---

## **4. Prioritas CSS antara ID dan Class Selector**

**Contoh kode:**

```css
#paragraf-1 {
    color: red;
}
.text-paragraf {
    color: green;
}
```

**Contoh HTML:**

```html
<p id="paragraf-1" class="text-paragraf">Teks paragraf</p>
```

📖 **Penjelasan:**
Dalam aturan *specificity* CSS:

* **ID selector (`#id`)** memiliki bobot prioritas lebih tinggi dibanding **Class selector (`.class`)**.
* Oleh karena itu, meskipun sebuah elemen memiliki ID dan Class secara bersamaan, gaya yang diterapkan adalah milik ID.

Pada contoh di atas, teks paragraf akan berwarna **merah**, meskipun class mendeklarasikan warna hijau. Hal ini menunjukkan bahwa ID dianggap lebih spesifik dibanding Class dalam hirarki CSS.

---

## **Kesimpulan**

1. CSS menyediakan beragam metode styling (inline, internal, eksternal) dengan tingkat prioritas yang berbeda. **Inline CSS** memiliki kekuatan tertinggi, diikuti internal, kemudian eksternal.
2. **Selector specificity** berperan penting dalam menentukan gaya akhir elemen. Selektor ID lebih kuat dibanding Class maupun elemen generik.
3. Eksperimen dengan properti modern seperti **gradient, border-radius, dan shadow** memperkaya estetika sekaligus memperkuat *user experience*.
4. Dengan memahami aturan cascade dan specificity, pengembang web dapat mengelola konflik antar CSS dengan efektif dan menghasilkan desain yang konsisten.
