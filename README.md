# ScoreMatrix: Research Pipeline and Dataset Repository

**A Parameter-Guided Framework for Automated Evaluation of Answer Sheets**

This repository contains the complete research implementation, dataset, and evaluation materials for ScoreMatrix - a transparent and configurable framework for automated scoring of diverse academic answer sheets including objective MCQ, short-form, descriptive, and opinion-based responses.

## Overview

ScoreMatrix integrates interpretable single-metric evaluators (semantic alignment, keyword coverage, coherence assessment, and grammar checking) within a weighted ensemble configurable by educators. The framework achieves a **Pearson correlation of 0.537** and **Mean Absolute Error of 3.37** on a normalized scoring scale while providing detailed criterion-level feedback.

## Repository Structure

### Core Implementation
- **`scorematrix-pipeline.ipynb`** - Complete implementation of the ScoreMatrix framework including all five interpretable metrics, weighted ensemble system, and evaluation pipeline
- **`scorematrix-demo-use.py`** - Standalone Python script demonstrating practical usage of the ScoreMatrix system for automated grading

### Research Paper
- **`scorematrix-2.pdf`** - Complete research paper detailing methodology, experimental setup, results, and comprehensive analysis

### Dataset and Results
- **`dataset/`** - Complete dataset of 847 student responses across 15 academic questions from multiple disciplines
- **`sample_with_predictions/`** - Final evaluation results containing automated scores, human ratings, and detailed metric breakdowns
- **`results_table.csv`** - Performance comparison table showing ScoreMatrix against baseline methods

### Visual Analysis
- **`evaluation_results.jpg`** - Comprehensive visualization dashboard showing correlation analysis, method comparisons, error distributions, metric importance weights, ablation study results, and score distribution comparisons

## Key Features

### Multi-Metric Evaluation System
- **Semantic Similarity**: Sentence-BERT embeddings with max-similarity matching at sentence level
- **Keyword Coverage**: Automated extraction and synonym recognition using spaCy and WordNet
- **Coherence Assessment**: Entity-grid modeling and sentence-similarity based flow scoring
- **Grammar Analysis**: LanguageTool integration with Flesch-Kincaid readability metrics
- **Factual Consistency**: Optional NLI-based contradiction detection

### Adaptive Configuration
- **Question Type Optimization**: Dynamic weight assignment based on descriptive, opinion, or objective question types
- **Educator Customization**: Configurable weighting system allowing instructors to emphasize specific criteria
- **Interpretable Feedback**: Detailed criterion-level explanations and improvement suggestions

## Performance Metrics

| Metric | ScoreMatrix | Unweighted Average | Semantic Similarity | Grammatical Accuracy |
|--------|-------------|-------------------|--------------------|--------------------|
| **Pearson Correlation** | **0.537** | 0.503 | NaN | 0.460 |
| **Mean Absolute Error** | **3.37** | 3.576 | 6.850 | 2.644 |
| **Root Mean Square Error** | **4.055** | - | - | - |

## Dataset Specifications

### Composition
- **Total Responses**: 847 student answers
- **Questions Coverage**: 15 distinct academic questions
- **Disciplines**: Science, social studies, literature, and technical subjects
- **Question Types**: 
  - Descriptive answers (45%)
  - Opinion-based responses (30%) 
  - Objective questions (25%)

### Quality Assurance
- **Dual Human Rating**: Each response independently scored by two expert evaluators
- **Gold Standard**: Final scores averaged post-adjudication to ensure reliability
- **Stratified Splits**: 60% training/calibration, 20% validation, 20% testing

## Implementation Resources

### Primary Notebook
**ScoreMatrix Comparison**: [https://www.kaggle.com/code/prakhar1803/scorematrix-comparison](https://www.kaggle.com/code/prakhar1803/scorematrix-comparison)

This notebook contains the complete evaluation framework used to generate the research results, including:
- Baseline method implementations and comparisons
- Comprehensive metric calculations across all evaluation criteria
- Statistical significance testing and confidence interval analysis
- Visual diagnostic generation and error analysis

### Technical Dependencies
- **Python 3.9+** with standard scientific computing stack
- **spaCy** for linguistic preprocessing and NLP operations
- **sentence-transformers** for semantic similarity computations
- **LanguageTool** for grammar analysis and error detection
- **NLTK + WordNet** for synonym detection and lexical matching
- **scikit-learn** for evaluation metrics and statistical analysis

## Experimental Validation

### Ablation Study Results
The framework's robustness is demonstrated through systematic ablation analysis:

- **Full System**: Pearson r = 0.537
- **Without Grammar**: Pearson r = 0.49 (-8.8% degradation)
- **Without Coherence**: Pearson r = 0.50 (-6.9% degradation)  
- **Without Keyword Coverage**: Pearson r = 0.47 (-12.5% degradation)
- **Without Semantic Similarity**: Pearson r = 0.45 (-16.2% degradation)

### Efficiency Analysis
- **Processing Time**: 0.8 seconds average per response
- **Scalability**: 95%+ reduction in grading time versus manual evaluation
- **Consistency**: Perfect reproducibility compared to 0.76 inter-rater reliability among human evaluators

## Use Cases and Applications

### Educational Settings
- **Large-scale standardized testing** with consistent evaluation criteria
- **Formative assessment** providing detailed feedback for student improvement
- **Multi-disciplinary grading** across science, humanities, and technical subjects
- **Bias reduction** through transparent and configurable evaluation parameters

### Research Applications
- **Automated grading benchmark** for comparative evaluation studies
- **Interpretability research** in educational AI and natural language processing
- **Pedagogical effectiveness** studies requiring scalable assessment methods

## Limitations and Considerations

### Technical Constraints
- **Reference Dependence**: Requires high-quality reference answers for optimal performance
- **Text-Centric Pipeline**: Current implementation limited to textual responses only
- **Novel Response Handling**: May undervalue creative answers using uncommon phrasing

### Deployment Requirements
- **Educator Calibration**: Weight selection may reflect instructor bias without proper training
- **Domain Adaptation**: Performance may vary across different academic disciplines
- **Ethical Considerations**: Potential bias against diverse linguistic or cultural backgrounds

## Citation

If you use this work in your research, please cite:

```bibtex
@article{kapur2025scorematrix,
  title={ScoreMatrix: A Parameter-Guided Framework for Automated Evaluation of Answer Sheets},
  author={Kapur, Pulkit and Chandra, Prakhar and Kohli, Jaspreet Singh},
  journal={Submitted for Publication},
  year={2025},
  institution={Maharaja Surajmal Institute of Technology, New Delhi, India}
}
```

## Future Development

### Planned Enhancements
- **Multimodal Evaluation**: Integration of diagram and equation analysis capabilities
- **LLM Hybridization**: Combination with large language models for enhanced reasoning
- **Adaptive Weighting**: Machine learning-based parameter optimization
- **Cross-institutional Validation**: Large-scale deployment and testing across multiple educational institutions


## License

This project is released under the MIT License. All code, datasets, and research materials are provided for academic and research purposes with appropriate attribution requirements.

---

