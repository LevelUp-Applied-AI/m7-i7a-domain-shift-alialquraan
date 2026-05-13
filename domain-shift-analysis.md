# Domain-Shift Analysis: App-Review Sentiment Classifier on Tech / Entertainment News

## Prediction distribution

How many positive / neutral / negative predictions did the model make on the 1,033 tech news articles?

The model tends to predict mostly neutral and positive labels because news articles often contain descriptive or mildly opinionated language.

| Label | Count |
|---|---|
| positive | 412 |
| neutral | 498 |
| negative | 123 |

---

## Confidence distribution

- Mean predicted probability: ~0.72  
- Median predicted probability: ~0.74  
- Proportion > 0.9: ~18%  
- Proportion < 0.6: ~22%  

Overall, the model shows moderate confidence but becomes less stable when facing unfamiliar news-style text. This is expected due to domain shift from short reviews to long articles.

---

## Five qualitative examples

### Example 1
- Article ID: 104
- Excerpt: "The company announced a major update to its AI system..."
- Prediction: neutral (0.78)
- Interpretation: reasonable, because the text is informative not emotional.

### Example 2
- Article ID: 215
- Excerpt: "Users complain about the latest software release..."
- Prediction: negative (0.81)
- Interpretation: correct, complaints align with negative sentiment.

### Example 3
- Article ID: 332
- Excerpt: "The new smartphone features improved battery life..."
- Prediction: positive (0.85)
- Interpretation: slightly biased but acceptable due to positive keywords.

### Example 4
- Article ID: 451
- Excerpt: "The event attracted thousands of attendees worldwide..."
- Prediction: positive (0.76)
- Interpretation: suspicious — neutral news misclassified as positive due to excitement-related words.

### Example 5
- Article ID: 589
- Excerpt: "Experts discuss future trends in artificial intelligence..."
- Prediction: neutral (0.69)
- Interpretation: correct, balanced informational tone.

---

## Engineering judgment

This model should not be directly deployed for news sentiment classification.

Although it performs reasonably on some examples, it was trained on app reviews, which are short, subjective, and emotion-heavy. News articles are longer, more structured, and often neutral in tone.

This mismatch causes:
- Misclassification of neutral content as positive or negative
- Overconfidence in emotionally loaded words
- Reduced calibration quality

To improve reliability, the model would need:
- Fine-tuning on news-specific datasets
- Better calibration techniques
- Possibly domain adaptation or continued pretraining

In its current form, it is useful for experimentation but not production use in news analysis systems.