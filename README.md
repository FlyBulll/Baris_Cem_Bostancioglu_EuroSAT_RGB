# EuroSAT RGB Land Cover Classification

Bu depo, EuroSAT RGB veri kümesi üzerinde arazi örtüsü/arazi kullanımı sınıflandırması için hazırlanan derin öğrenme proje dosyalarını içerir. Çalışmada baseline CNN modelleri ve transfer learning tabanlı MobileNetV2, DenseNet121 ve InceptionV3 mimarileri karşılaştırılmıştır.

## Klasör Yapısı

```text
data/
figures/
models/
notebooks/
reports/
```

### `data/`

Veri seti dosyalarını ve eğitim/doğrulama/test bölünmelerini içerir.

- `data/raw/`: EuroSAT RGB veri setinin ham hali.
- `data/processed/eurosat_split_seed42.zip`: Projede kullanılan train/validation/test split çıktısı.
- `data/train/`, `data/valid/`, `data/test/`: Sınıflara ayrılmış eğitim, doğrulama ve test görüntüleri.

### `notebooks/`

Deneylerin adım adım çalıştırıldığı Jupyter Notebook dosyalarıdır.

- `01_dataset_preparation.ipynb`: Veri setinin hazırlanması, sınıf dağılımları ve train/validation/test bölünmesi.
- `02_baseline_cnn.ipynb`: Veri artırma kullanılmayan baseline CNN deneyi.
- `02b_baseline_cnn.ipynb`: Veri artırma kullanılan baseline CNN deneyi.
- `03_transfer_learning_mobilenetv2.ipynb`: MobileNetV2 ile feature extraction ve fine-tuning deneyleri.
- `04_transfer_learning_densenet121.ipynb`: DenseNet121 ile feature extraction ve fine-tuning deneyleri.
- `05_transfer_learning_inceptionv3.ipynb`: InceptionV3 ile feature extraction ve fine-tuning deneyleri.
- `06_model_comparison_analysis.ipynb`: Modellerin karşılaştırılması, hata analizi ve sonuç grafiklerinin üretilmesi.

### `models/`

Eğitim sonunda kaydedilen model ağırlıklarını içerir.

- `baseline_cnn_best.keras`: Veri artırma kullanılmayan baseline CNN için en iyi checkpoint.
- `baseline_cnn_b_best.keras`: Veri artırma kullanılan baseline CNN için en iyi checkpoint.
- `mobilenetv2_feature_best.keras`: MobileNetV2 feature extraction aşamasındaki en iyi checkpoint.
- `mobilenetv2_finetuned_best.keras`: MobileNetV2 fine-tuning sonrasındaki en iyi checkpoint.
- `densenet121_feature_best.keras`: DenseNet121 feature extraction aşamasındaki en iyi checkpoint.
- `densenet121_finetuned_best.keras`: DenseNet121 fine-tuning sonrasındaki en iyi checkpoint.
- `inceptionv3_feature_best.keras`: InceptionV3 feature extraction aşamasındaki en iyi checkpoint.
- `inceptionv3_finetuned_best.keras`: InceptionV3 fine-tuning sonrasındaki en iyi checkpoint.

### `reports/`

Deneylerden elde edilen sayısal sonuçları ve analiz dosyalarını içerir.

- `*_metrics.json`: Her model için temel test metrikleri.
- `*_history.csv`: Eğitim ve doğrulama accuracy/loss geçmişi.
- `*_classification_report.csv`: Sınıf bazlı precision, recall ve F1-score değerleri.
- `model_comparison_summary.csv`: Modellerin genel performans karşılaştırması.
- `class_f1_comparison.csv`: Sınıf bazında F1-score karşılaştırması.
- `experiment_parameter_summary.csv`: Deneylerde kullanılan temel parametrelerin özeti.
- `densenet121_test_predictions.csv`: DenseNet121 test tahminleri.
- `densenet121_misclassified_examples.csv`: DenseNet121 için yanlış sınıflandırılan örnekler.
- `densenet121_top_misclassification_pairs.csv`: En sık karıştırılan sınıf çiftleri.
- `final_model_recommendation.json`: Nihai model seçimine ilişkin özet bilgi.

### `figures/`

Analiz için kullanılan grafik ve görsel çıktılarını içerir.

- Eğitim/doğrulama accuracy ve loss grafikleri.
- Confusion matrix görselleri.
- Model karşılaştırma grafikleri.
- Sınıf dağılımı ve veri artırma örnekleri.
- Yanlış tahmin edilen örnek görselleri.
