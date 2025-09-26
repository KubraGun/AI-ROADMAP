1. Tabular / Zaman Serisi Veri

Yaptýðýmýz: kolon bazlý eksiklik oraný, gap/blok analizi, ardýþýklýk, süre/uzunluk daðýlýmý.

Ek yaklaþýmlar: eksiklik mekanizmasý testi (MCAR testleri, Little’s MCAR test).

2. Görüntü (Image) Verisi

Eksik piksel analizi (bozuk sensör, maskelenmiþ alan, noise).

Genelde “inpainting” yöntemleri (CNN, diffusion, GAN) ile tamamlanýyor.

Analiz: eksikliðin konumu (ör. kenarlarda mý merkezde mi?), daðýlýmý (tekil mi blok halinde mi?).

3. Metin (Text / NLP) Verisi

Eksiklik: bozuk OCR çýktýsý, silinmiþ kelime, eksik etiket.

Analiz: “token missing rate” (kaç kelime boþ kalmýþ), “span gap” (kaç ardýþýk kelime kayýp).

Genelde mask-based dil modelleri (BERT, LLaMA) ile dolduruluyor.

4. Grafik / Að Verisi (Graph Data)

Eksiklik: eksik node veya eksik edge.

Analiz: “node missing ratio”, “edge density drop”, baðlanýrlýk testi (connectedness).

Doldurma: graph completion, link prediction.

5. Multimodal Veriler

Örneðin finansal haber + fiyat serisi senaryosunda, haber metinleri tam ama fiyat verisi eksik olabilir.

Eksikliði ayrý ayrý analiz etmek ve sonra fused imputasyon yapmak gerek (ör. haber embedding’leri yardýmýyla fiyat eksikliklerini tahmin etmek).

Özet:

Eksik veri analizi her veri tipinde var.

Tabular/zaman serisinde klasik metrikler (oran, gap, blok).

Görüntüde “mask distribution”, metinde “token drop”, grafikte “node/edge missing”.

Amaç hep ayný: eksikliðin oranýný, daðýlýmýný ve örüntüsünü anlamak.