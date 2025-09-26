1. Tabular / Zaman Serisi Veri

Yaptığımız: kolon bazlı eksiklik oranı, gap/blok analizi, ardışıklık, süre/uzunluk dağılımı.

Ek yaklaşımlar: eksiklik mekanizması testi (MCAR testleri, Little’s MCAR test).

2. Görüntü (Image) Verisi

Eksik piksel analizi (bozuk sensör, maskelenmiş alan, noise).

Genelde “inpainting” yöntemleri (CNN, diffusion, GAN) ile tamamlanıyor.

Analiz: eksikliğin konumu (ör. kenarlarda mı merkezde mi?), dağılımı (tekil mi blok halinde mi?).

3. Metin (Text / NLP) Verisi

Eksiklik: bozuk OCR çıktısı, silinmiş kelime, eksik etiket.

Analiz: “token missing rate” (kaç kelime boş kalmış), “span gap” (kaç ardışık kelime kayıp).

Genelde mask-based dil modelleri (BERT, LLaMA) ile dolduruluyor.

4. Grafik / Ağ Verisi (Graph Data)

Eksiklik: eksik node veya eksik edge.

Analiz: “node missing ratio”, “edge density drop”, bağlanırlık testi (connectedness).

Doldurma: graph completion, link prediction.

5. Multimodal Veriler

Örneğin finansal haber + fiyat serisi senaryosunda, haber metinleri tam ama fiyat verisi eksik olabilir.

Eksikliği ayrı ayrı analiz etmek ve sonra fused imputasyon yapmak gerek (ör. haber embedding’leri yardımıyla fiyat eksikliklerini tahmin etmek).

Özet:

Eksik veri analizi her veri tipinde var.

Tabular/zaman serisinde klasik metrikler (oran, gap, blok).

Görüntüde “mask distribution”, metinde “token drop”, grafikte “node/edge missing”.

Amaç hep aynı: eksikliğin oranını, dağılımını ve örüntüsünü anlamak.


# Eksik Veri Analizi – Veri Türlerine Göre Karşılaştırma

| Veri Türü              | Eksiklik Türü                                      | Analiz Yöntemleri                                                                 | Tipik Doldurma Yöntemleri                                                                 |
|------------------------|----------------------------------------------------|-----------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| **Tabular / Zaman Serisi** | Tekil NaN, ardışık blok (gap), sistematik eksiklik (ör. tatiller) | Eksik oranı (%), gap count, max gap, Little’s MCAR Test, pattern analizi          | Forward/Backward fill, Interpolasyon (lineer/spline), Model tabanlı (Kalman, ARIMA, ML)   |
| **Görüntü (Image)**    | Eksik piksel, sensör hatası, maskelenmiş bölgeler  | Eksik piksel oranı, mekânsal dağılım (blok mu rastgele mi?), mask dağılımı analizi | Inpainting (CNN, GAN, Diffusion), spline tabanlı görüntü doldurma                         |
| **Metin (Text/NLP)**   | Eksik kelime/token, bozuk OCR, eksik cümle/paragraf | Missing token ratio, span length distribution                                     | Masked Language Model (BERT), Seq2Seq tamamlama, Embedding tabanlı doldurma               |
| **Grafik / Ağ (Graph)**| Eksik düğüm (node), eksik kenar (edge), incomplete subgraph | Node missing rate, edge density, connectedness analizi                             | Link prediction, Graph completion (GCN, GAT)                                              |
| **Multimodal** (örn. Haber + Fiyat serisi) | Bir mod eksik (ör. fiyat var haber yok, haber var fiyat yok) | Mod bazlı eksik oranı, senkronizasyon analizi                                      | Cross-modal imputasyon (metin → sayı, görüntü → tablo), ortak embedding tabanlı tamamlama |
