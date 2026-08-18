# CLI Veri İşleme Egzersizi Notları (Ödev 1.2)

Bu belgede, sadece terminal araçları (Python kullanılmadan) kullanılarak büyük bir CSV veri seti üzerinde gerçekleştirilen veri işleme adımları ve komutları yer almaktadır.

## 1. Satır Sayısını Bulma
CSV dosyasındaki toplam satır sayısını (`wc` aracı ile) bulmak için kullanılan komut:
```bash
wc -l veri_seti.csv

Belirli bir kolondaki verilerin kaçar kez geçtiğini (frekansını) büyükten küçüğe sıralamak için kullanılan komut (cut, sort ve uniq kombinasyonu):
cut -d',' -f3 veri_seti.csv | sort | uniq -c | sort -nr

Belirli bir kritere (örneğin belirli bir kelimeyi içeren) uyan satırları filtreleyip yeni bir dosyaya aktarmak için kullanılan komut (awk veya grep):
awk -F',' '$1 == "aranan_deger"' veri_seti.csv > filtrelenmis_veri.csv

İki farklı CSV dosyasını ortak bir sütun (anahtar) üzerinden birleştirmek için kullanılan komut:
join -t',' -1 1 -2 1 dosya1.csv dosya2.csv > birlestirilmis_veri.csv
