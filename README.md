# Tamil-Text-Summarization-using-NLP-techniques-and-LLMS
This project develops a Speech-to-Speech Translation system to convert Tamil speech to Telugu. It integrates ASR, MT, and TTS technologies, using Whisper for ASR, AI4Bharat’s IndicTrans for translation, and Facebook MMS for TTS. The project improves multilingual communication, with future work aiming to reduce latency and enhance accuracy.

---

## Dataset Information

- **Training Data**: 350+ Wikipedia articles
- **Validation Data**: 90 Wikipedia articles

---

## Preprocessing Steps

1. **Text Cleaning**: Removing special characters.
2. **Tokenization**: Using n-grams and NLTK.
3. **Analysis of Document Lengths**: Truncating documents to 448 tokens.
4. **Saving Preprocessed Data**: Storing the cleaned data for training.
5. **Features Extraction**: TF, IDF, TF-IDF, and stopword removal.

---

## Model Selection

- **MTM Model by Facebook**
- **MT5 Model by Facebook**
- **mBART Model**

### Extractive vs. Abstractive Summarization

- **Extractive Approach**: Selects key sentences from the original text.
- **Abstractive Approach**: Generates new sentences based on the understanding of the text.

---

## Sentence Scoring Method

### Methodology:

- **Surface Score Components**:
  - Position Score
  - Length Score
  - Paragraph Score
  - Heading Score

Sentences are scored based on these components, and the highest-scoring sentences are selected for summarization.

### Sentence Weighing:

- **Methodology**:
  - Edit Distance Calculation for Sentence Length Score Weight (LSW).
  - Combines LSW and word frequency to rank sentences.
  - Higher-ranked sentences are selected for summarization.

---

## Sentence Clustering

Sentences are grouped into clusters based on their feature representations, and representative sentences are selected to form a coherent summary.

### Methodology:

1. **Feature Representation**: Extract features to represent the importance of terms in each sentence.
2. **Clustering**: Use the KMeans algorithm to partition sentences into clusters.
3. **Sentence Selection**: Choose representative sentences based on proximity to the cluster centroid.

---

## Models Used

- **mBART**: Finetuned for Tamil text summarization.
- **MT5**: Another abstractive summarization model.
- **M2M100**: For multilingual text summarization tasks.

### Training Configuration

- **Learning Rate**
- **Batch Size**
- **Number of Epochs**
- **Warmup Steps**
- **Weight Decay**
- **Logging Steps**

---

## Evaluation Metrics

- **ROUGE-1, ROUGE-2, and ROUGE-L**: Metrics used to evaluate the quality of summarization.

---

## Abstractive Summarization Results

The following results were generated using the models (mBART, MT5, M2M100) on Tamil text summarization tasks:

### Summarized Example:

Original Text:
> "இ� �ற��� அவ� ப�ப�ச� தமிழிட� ��ைகய��, "இ����ைப மிக� ச�ற�த ��ேபா�கான ���பாக பா��க�ேற�. அ��பைட உரிைம எ�ன எ�பைத மிக�� �வ�ரமாக இ����� வ�ள�க���ள�" எ�றா�."

### Model Summarization Output:

1. **mBART**:
   - "இ�த�ய அரச�யலைம�ப�� 21-ஆவ� வ�த�ைய மிக�� ஆழமாக �த�ம�ற� வ�ள�க���ள� எ���, ஏ�கனேவ இர�� ேவ� வழ��களி� தனி நப� அ�தர�க�ைத அ��பைட உரிைம பா�கா�கா�."

2. **MT5**:
   - "இ�த�ய அரச�யலைம�ப�� 21-ஆவ� வ�த�ைய மிக�� ஆழமாக �த�ம�ற� வ�ள�க���ள� எ���, ஏ�கனேவ �ந��க� கால�த�� �த�பத� எ�.ஆ�."

3. **M2M100**:
   - "அ��பைட உரிைம எ�ன எ�பைத மிக�� �வ�ரமாக இ����� வ�ள�க���ள�" எ�றா�."

---

## Advantages of the Approach

- Structured sentence selection based on relevance.
- Customizable scoring criteria.
- Balanced between document structure and content.
- Flexibility in weighting schemes.
- Efficient sentence clustering to capture key themes.

