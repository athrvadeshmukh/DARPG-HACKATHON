![zy4knlgc-Drpg_Challenges_15thmarch_banner](https://github.com/athrvadeshmukh/DARPG-HACKATHON/assets/112002659/dbc4e80c-dfa8-4be7-b578-c70b124b7e4e)

# PROBLEM STATEMENT- 3	

## Evaluate And Optimize An Existing Open-Source Speech-To-Text Transcription Tool For Accurately Converting Feedback Calls Related To Citizen Grievances Into English Text. The Goal Is To Benchmark The Tool's Performance And Implement Enhancements To Achieve Measurable Improvements In Transcription Accuracy For Calls In Hindi, English, And Hinglish. This Project Does Not Involve Creating A New System But Rather Focuses On Refining An Already Established Open-Source Solution.

# Zero AI Speech-to-Text Transcription

## Project Report

### Team ID: DARPG_1146

### Problem Statement: 3

---

### Team Members:

- ATHRVA DESHMUKH ([Athrva Deshmukh](https://github.com/athrvadeshmukh))
- GOURAV KUSHWAHA (([GOURAV KUSHWAHA](https://github.com/GOURAVKUSHWAHA-pro))
- UJJWAL GUPTA ([Ujjwal Gupta](https://github.com/masterujjval))
- SONU KUSHWAHA ([Sonu Kushwaha](https://github.com/Sonu7804))

---
### Demo and Explanation Video

https://github.com/athrvadeshmukh/DARPG-HACKATHON/assets/112002659/18f08482-c5b1-4022-ab61-4c3bcf978e08

---

### Submit To:

Online Hackathon on Data-driven Innovation for Citizen Grievance Redressal organized by the Department of Administrative Reforms & Public Grievances (DARPG) of the Ministry of Personnel, Public Grievances & Pensions.

---

### Project Link:

[Zero AI Speech-to-Text Transcription](https://github.com/athrvadeshmukh/DARPG-HACKATHON.git)

---
### Output 

![image](https://github.com/athrvadeshmukh/DARPG-HACKATHON/assets/112002659/6bf67333-463f-4812-9190-8d11416bbe64)


![image](https://github.com/athrvadeshmukh/DARPG-HACKATHON/assets/112002659/c72184c1-af91-4cef-9733-c7d274772b51)


![image](https://github.com/athrvadeshmukh/DARPG-HACKATHON/assets/112002659/bccac9b7-ade4-4b7f-b5a4-808d3fcca29f)


---
### Approach

![Approach](https://raw.githubusercontent.com/openai/whisper/main/approach.png)


## Executive Summary

The project aims to evaluate and optimize an existing open-source speech-to-text transcription tool for accurately converting feedback calls related to citizen grievances into English text. The tool under consideration is ZeroAI.py, which utilizes the Whisper library for transcription tasks. The primary objective is to benchmark the tool's performance and implement enhancements to achieve measurable improvements in transcription accuracy for calls in Hindi, English, and Hinglish. The project does not entail creating a new system but rather focuses on refining an already established open-source solution.

---

## Introduction

The objective of this project is to evaluate and optimize the open-source speech-to-text transcription tool, Whisper, for accurately converting feedback calls related to citizen grievances into English text. The project aims to benchmark the tool’s performance and implement enhancements to achieve measurable improvements in transcription accuracy for calls in Hindi, English, and Hinglish. Rather than creating a new system, the focus is on refining the already established open-source solution provided by Whisper. The proliferation of citizen feedback mechanisms necessitates efficient handling and processing of various communication channels, including voice calls. In contexts where feedback is provided in multilingual formats such as Hindi, English, and Hinglish, automated transcription tools play a crucial role in extracting actionable insights from diverse data sources. This project addresses the optimization of an existing speech-to-text transcription tool to enhance its accuracy and usability in handling feedback calls related to citizen grievances.

---

## Objectives

- Evaluate the current performance of the open-source speech-to-text transcription tool.
- Identify key areas for improvement in transcription accuracy, particularly for calls in Hindi, English, and Hinglish.
- Implement enhancements and optimizations to the existing tool to achieve measurable improvements.
- Benchmark the performance of the optimized tool against the baseline.
- Provide recommendations for future enhancements and usage scenarios.

---

## Whisper Overview

Whisper is a general-purpose speech recognition model developed by OpenAI. It is a Transformer sequence-to-sequence model trained on a large dataset of diverse audio. The model is designed to perform multilingual speech recognition, speech translation, spoken language identification, and voice activity detection.

---

## Approach

Whisper utilizes a Transformer sequence-to-sequence model trained on various speech processing tasks. These tasks are jointly represented as a sequence of tokens to be predicted by the decoder, enabling a single model to replace many stages of a traditional speech-processing pipeline. The multitask training format employs special tokens that serve as task specifiers or classification targets.

---

## Project Setup

### Software Requirements:

- Python 3.8-3.11
- PyTorch 1.10.1
- ffmpeg
- rust (if required)

### Installation:

The Whisper package can be installed via pip using the following commands:

- Bash: `pip install -U openai-whisper`
- Windows: `pip install git+https://github.com/openai/whisper.git`
- Additional dependencies such as ffmpeg and rust may need to be installed based on the system requirements.
- To install all dependencies `pip install -r requirements.txt`

---

## Available Models and Languages

Whisper provides several model sizes optimized for different applications and languages. The table below summarizes the available models along with their specifications:

| Size   | Parameters | English-only model | Multilingual model | Required VRAM | Relative speed |
|--------|------------|--------------------|--------------------|---------------|----------------|
| tiny   | 39 M       | tiny.en            | tiny               | ~1 GB         | ~32x           |
| base   | 74 M       | base.en            | base               | ~1 GB         | ~16x           |
| small  | 244 M      | small.en           | small              | ~2 GB         | ~6x            |
| medium | 769 M      | medium.en          | medium             | ~5 GB         | ~2x            |
| large  | 1550 M     | N/A                | large              | ~10 GB        | 1x             |

The performance of Whisper varies based on the language and model size. The .en models are optimized for English-only applications and tend to perform better, especially for smaller models.

![WER breakdown by language](https://github.com/openai/whisper/assets/266841/f4619d66-1058-4005-8f67-a9d811b77c62)

---

## Command-line and Python Usage

Whisper can be used both from the command line and within Python scripts for transcription tasks. The command-line usage allows for transcribing speech in audio files, while Python usage provides more flexibility for integration and customization.

### Command-line Usage:

- Bash: `whisper audio.flac audio.mp3 audio.wav --model medium`

### Python Usage:

```python
import whisper

model = whisper.load_model("base")
result = model.transcribe("audio.mp3")
print(result["text"])
```

The Python API enables users to transcribe audio files and provides access to lower-level functionalities for language detection and decoding.

---

## Project Evaluation

Before proceeding with optimization efforts, it's essential to evaluate the current performance of Whisper on feedback calls related to citizen grievances. The evaluation phase involves several key steps:

- Data Collection
- Annotation
- Evaluation Metrics
- Test Set Preparation
- Baseline Performance
- Error Analysis

---

## Experimentation and Validation

To validate the effectiveness of the optimization strategies, a series of controlled experiments should be conducted:

- Experimental Setup
- Hyperparameter Tuning
- Cross-Validation
- Statistical Significance Testing
- Qualitative Analysis

---

## Optimization Strategy

To optimize Whisper for accurately transcribing feedback calls related to citizen grievances, the following strategies can be considered:

- Fine-tuning
- Language-specific Models
- Data Augmentation
- Model Ensemble
- Language Model Integration
- Speaker Adaptation
- Domain Adaptation
- Multimodal Fusion
- Model Ensemble and Fusion

---

## Continuous Improvement and Lifelong Learning

Incorporating mechanisms for continuous improvement and lifelong learning is essential to ensure that Whisper remains relevant, reliable, and effective over time:

- Model Retraining and Update Policies
- Active Learning and Human-in-the-Loop
- Automatic Model Versioning and Rollback
- Benchmarking and Comparative Evaluation
- Experimentation and Innovation
- User Feedback Mechanisms
- Cross-Disciplinary Collaboration
- Community Engagement and Participation

---

## Responsible Use and Ethical Governance

Adopting principles of responsible use and ethical governance is paramount to ensure that Whisper's capabilities are harnessed for positive social impact and ethical outcomes:

- Ethical Use Policies and Guidelines
- Fairness and Equity Considerations
- Privacy and Data Protection
- Algorithmic Accountability and Transparency
- Ethical Review and Oversight
- Community Engagement and Stakeholder Dialogue
- Continuous Education and Awareness

---

## Program

```python


def main():
    # Evaluate current performance
    evaluate_performance()

    # Optimize the transcription tool
    optimize_transcription_tool()

    # Validate optimization strategies
    validate_strategies()

    # Ensure responsible use and ethical governance
    ensure_responsible_use()


if __name__ == "__main__":
    main()
```

---


## Conclusion

The optimization of Whisper for accurately transcribing feedback calls related to citizen grievances represents a significant opportunity to enhance the efficiency and effectiveness of public service delivery mechanisms. By leveraging state-of-the-art speech recognition technologies and adopting a data-driven approach, it is possible to achieve measurable improvements in transcription accuracy and usability. The success of this project depends on collaboration, innovation, and a shared commitment to excellence in citizen-centric governance.

---

## Acknowledgments

We would like to express our sincere gratitude to the Department of Administrative Reforms & Public Grievances (DARPG) for organizing the hackathon and providing us with this opportunity to contribute to the advancement of citizen-centric governance. We are also thankful to our mentors, colleagues, and fellow participants for their guidance, support, and inspiration throughout the course of this project.

---

## Project Report
[Project Report](DARPG_45_Hackathon_Report.pdf)

---

## References

- Whisper Documentation: [https://github.com/openai/whisper](https://github.com/openai/whisper)
- OpenAI: [https://openai.com](https://openai.com)
- Department of Administrative Reforms & Public Grievances (DARPG): [https://darpg.gov.in](https://darpg.gov.in)

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
![image](https://github.com/athrvadeshmukh/DARPG-HACKATHON/assets/112002659/ab8fd812-02a4-4eb7-af43-e4a14333e058)
