<h1 align="center"> NLP With HuggingFace Transformers </h1>
<p align="center"> Berisi tentang pipeline dari HuggingFace Transformers untuk keperluan NLP (Natural Language Processing)</p>

<div align="center">
  <img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54">
  <img src="https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white">
</div>

<h2 align="center"> Analisis Pipeline Transformers pada HuggingFace </h2> 

### Zero-Shot Classification
Zero-Shot Classification adalah teknik di mana model dapat mengklasifikasikan teks tanpa pelatihan khusus pada label tertentu. Saya membuat objek classifier menggunakan pipeline `zero-shot-classification`. Dengan ini, saya bisa mengklasifikasikan teks tanpa memerlukan model yang dilatih secara khusus untuk kategori tertentu. Saya memberikan teks "The recent advancements in quantum computing could revolutionize data encryption methods." dengan label yang diberikan `["science", "finance", "sports", "literature", "art"]`. Model akan menganalisis teks dan menentukan kategori yang paling cocok. Karena teks ini berfokus pada "quantum computing" dan "encryption methods," model lebih cenderung mengklasifikasikannya di bawah label `science`. Teknik Zero-Shot Classification ini sangat fleksibel dalam berbagai penggunaan.

### Text Generation
Text Generation adalah proses otomatis untuk membuat teks baru berdasarkan input yang diberikan. Saya membuat objek `generator` yang digunakan untuk menghasilkan teks. Dengan pipeline `text-generation`, saya dapat menghasilkan teks berdasarkan input cerita awal yang diberikan, dan generator akan melanjutkan cerita tersebut. Dengan pipeline ini, pengguna bisa menyesuaikan model agar hasil teks yang dihasilkan lebih relevan dengan konteks yang diinginkan.

### Fill Mask
Fill Mask digunakan untuk memprediksi kata yang hilang dalam sebuah teks. Saya memberikan kalimat dengan kata yang hilang yang diganti dengan `<mask>`. Model akan menebak dua kata yang paling mungkin mengisi posisi tersebut. Saya juga menentukan `top_k=2`, yang berarti saya ingin mendapatkan dua prediksi teratas untuk kata yang dapat mengisi bagian yang hilang. Model akan menghasilkan dua kemungkinan kata untuk mengisi posisi `<mask>`: "gym" dan "cinema".

### Named Entity Recognition (NER)
Named Entity Recognition (NER) bertujuan untuk mengidentifikasi entitas bernama dalam sebuah teks, seperti nama orang, organisasi, atau lokasi. Saya membuat objek `ner` yang dirancang untuk melakukan tugas NER, mengelompokkan entitas yang sama dalam hasilnya dengan `grouped_entities=True`. Dalam contoh ini, model berhasil mengidentifikasi dua entitas: "Lisa" sebagai orang dan "Blackpink" sebagai organisasi.

### Question Answering
Question Answering adalah model yang dapat digunakan untuk menjawab pertanyaan berdasarkan konteks yang diberikan. Saya mendefinisikan konteks tentang cara kerja panel surya dan pertanyaan yang menanyakan tentang cara panel surya menghasilkan listrik. Model ini (distilbert-base-cased-distilled-squad) telah dilatih pada dataset SQuAD (Stanford Question Answering Dataset) untuk mencari jawaban yang relevan dari teks konteks. Aplikasi Question Answering ini dapat digunakan dalam asisten virtual, pencarian informasi, dan aplikasi serupa.

### Sentiment Analysis
Sentiment Analysis adalah proses otomatis untuk menandai data menurut sentimen, seperti positif, negatif, atau netral. Saya mengimpor pipeline dari pustaka transformers dan membuat objek `classifier` dengan tugas `sentiment-analysis`. Model yang digunakan adalah `distilbert-base-uncased-finetuned-sst-2-english`, yang terlatih untuk menentukan sentimen dari teks bahasa Inggris. Model menganalisis kalimat berdasarkan kata-kata dan konteks, meskipun ada elemen positif ("the food at this restaurant was good"), model menilai sentimen keseluruhan sebagai negatif karena penilaian negatif tentang layanan yang lambat.

### Summarization
Summarization adalah pipeline untuk meringkas teks menjadi versi yang lebih singkat dengan poin-poin utama. Model yang digunakan, `sshleifer/distilbart-cnn-12-6`, dirancang untuk menyaring informasi relevan dari teks panjang, seperti berita, dan merangkumnya menjadi versi pendek. Model ini bermanfaat untuk aplikasi seperti pembuatan ringkasan berita atau dokumen panjang.

### Translation (Indonesian to English)
Translation menggunakan model `Helsinki-NLP/opus-mt-id-en`, yang terlatih untuk menerjemahkan teks dari bahasa Indonesia ke bahasa Inggris. Saat diberikan teks dalam bahasa Indonesia, model menganalisis kata-kata dan struktur kalimat untuk menghasilkan terjemahan yang sesuai dalam bahasa Inggris.
