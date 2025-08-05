# Model Performance Results

## Dataset Summary
- **Location**: Melbourne area (Melbourne, Watsonia, Melbourne Airport)
- **Time Period**: 2008–2017
- **Total Records**: 7,557 after preprocessing
- **Class Distribution**: 76% No Rain, 24% Rain

## Model Comparison

### Initial Models

#### Random Forest Classifier
- **Best Parameters**: 
  - n_estimators: 100
  - max_depth: 20
  - min_samples_split: 2
- **Test Accuracy**: 83%
- **Precision (Rain)**: 0.69
- **Recall (Rain)**: 0.51
- **F1-Score (Rain)**: 0.59

#### Logistic Regression
- **Best Parameters**:
  - solver: liblinear
  - penalty: l2
  - class_weight: balanced
- **Test Accuracy**: 84%
- **Precision (Rain)**: 0.73
- **Recall (Rain)**: 0.52
- **F1-Score (Rain)**: 0.61

### Extended Evaluation

| Model Version                          | Precision (Rain) | Recall (Rain) | F1-Score (Rain) | Accuracy |
|---------------------------------------|------------------|---------------|------------------|----------|
| Original (Accuracy Optimized)         | 0.684            | 0.508         | 0.583            | 0.828    |
| Class Balanced                        | 0.684            | 0.508         | 0.583            | 0.828    |
| Best Threshold                        | 0.662            | 0.559         | 0.606            | 0.828    |
| Feature Enhanced                      | 0.515            | 0.737         | 0.606            | 0.773    |
| Feature Enhanced with Custom Threshold| 0.489            | 0.779         | 0.601            | 0.755    |

## Top 5 Most Important Features
1. **Humidity3pm** – Afternoon humidity levels
2. **Pressure9am** – Morning atmospheric pressure
3. **Sunshine** – Hours of bright sunshine
4. **Cloud3pm** – Afternoon cloud coverage
5. **WindGustSpeed** – Maximum wind gust speed

## Model Performance Analysis
- Both initial models perform well on the majority class (No Rain) with ~93–94% recall.
- Rain detection is more challenging with only ~51–52% recall initially.
- Feature engineering and threshold tuning significantly improved recall to **77.9%**.
- Precision dropped with increased recall, indicating a trade-off.

## Best Model By Criteria

🎯 **Best Recall (Rain Detection)**: Feature Enhanced with Custom Threshold  
→ Catches 77.9% of rainy days

🔍 **Best Precision (Fewer False Alarms)**: Original (Accuracy Optimized)  
→ 68.4% of rain predictions are correct

⚖️ **Best F1-Score (Balance)**: Feature Enhanced  
→ F1-Score: 0.606

📊 **Best Overall Accuracy**: Original (Accuracy Optimized)  
→ Accuracy: 82.8%

## Limitations
- Still misses ~22% of rainy days
- High false positive rate in high-recall models
- Only trained on Melbourne data – may not generalize

## Recommendations
- Use **Feature Enhanced with Custom Threshold** for rain-sensitive applications
- Use **Original** for fewer false alarms
- Use **Feature Enhanced** for balanced performance

## Future Improvements
- Use oversampling/SMOTE for better class balance
- Add time-series features or rolling weather metrics
- Try boosting models like XGBoost or LightGBM
- Explore recurrent models (LSTM) for temporal patterns
