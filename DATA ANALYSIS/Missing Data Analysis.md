1. Tabular / Zaman Serisi Veri

Yapt���m�z: kolon bazl� eksiklik oran�, gap/blok analizi, ard���kl�k, s�re/uzunluk da��l�m�.

Ek yakla��mlar: eksiklik mekanizmas� testi (MCAR testleri, Little�s MCAR test).

2. G�r�nt� (Image) Verisi

Eksik piksel analizi (bozuk sens�r, maskelenmi� alan, noise).

Genelde �inpainting� y�ntemleri (CNN, diffusion, GAN) ile tamamlan�yor.

Analiz: eksikli�in konumu (�r. kenarlarda m� merkezde mi?), da��l�m� (tekil mi blok halinde mi?).

3. Metin (Text / NLP) Verisi

Eksiklik: bozuk OCR ��kt�s�, silinmi� kelime, eksik etiket.

Analiz: �token missing rate� (ka� kelime bo� kalm��), �span gap� (ka� ard���k kelime kay�p).

Genelde mask-based dil modelleri (BERT, LLaMA) ile dolduruluyor.

4. Grafik / A� Verisi (Graph Data)

Eksiklik: eksik node veya eksik edge.

Analiz: �node missing ratio�, �edge density drop�, ba�lan�rl�k testi (connectedness).

Doldurma: graph completion, link prediction.

5. Multimodal Veriler

�rne�in finansal haber + fiyat serisi senaryosunda, haber metinleri tam ama fiyat verisi eksik olabilir.

Eksikli�i ayr� ayr� analiz etmek ve sonra fused imputasyon yapmak gerek (�r. haber embedding�leri yard�m�yla fiyat eksikliklerini tahmin etmek).

�zet:

Eksik veri analizi her veri tipinde var.

Tabular/zaman serisinde klasik metrikler (oran, gap, blok).

G�r�nt�de �mask distribution�, metinde �token drop�, grafikte �node/edge missing�.

Ama� hep ayn�: eksikli�in oran�n�, da��l�m�n� ve �r�nt�s�n� anlamak.