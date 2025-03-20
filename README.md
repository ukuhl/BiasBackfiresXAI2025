# BiasBackfiresXAI2025
This repository contains the user data and analysis code accompanying the paper: 
> When Bias Backfires: The Modulatory Role of Counterfactual Explanations on the Adoption of Algorithmic Bias in XAI-Supported Human Decision-Making. Submitted to XAI 2025.

## Abstract
Although the integration of artificial intelligence (AI) into everyday tasks improves efficiency and objectivity, it also risks transmitting bias to human decision-making. In this study, we conducted a controlled experiment that simulated hiring decisions to examine how biased AI recommendations - augmented with or without counterfactual explanations - influence human judgment over time. Participants, acting as hiring managers, completed 60 decision trials divided into a baseline phase without AI, followed by a phase with biased (X)AI recommendations (favoring either male or female candidates), and a final post-interaction phase without AI. Our results indicate that the participants followed the AI recommendations 70% of the time when the qualifications of the given candidates were comparable. Yet, only a fraction of participants detected the gender bias (8 out of 294). Crucially, exposure to biased AI altered participants’ inherent preferences: in the post-interaction phase, participants’ independent decisions aligned with the bias when no counterfactual explanations were provided before, but reversed the bias when explanations were given. Reported trust did not differ significantly across conditions. Confidence varied throughout the study phases after exposure to male-biased AI, indicating nuanced effects of AI bias on decision certainty. Our findings point to the importance of calibrating XAI to avoid unintended behavioral shifts in order to safeguard equitable decision-making and prevent the adoption of algorithmic bias.

## Overview of files

### Directory UserData

####  BiasBackfiresXAI25_analysis.Rmd / BiasBackfiresXAI25_analysis.pdf
Description:

This R Markdown script contains all the data cleaning, processing, and statistical analysis procedures applied to the user data. It replicates the analyses presented in the paper, generating figures, tables, and summary statistics for transparency and reproducibility. Note: running it will create a new subdirectory "Figures".

#### user_survey_questions_view.csv
Description:

This CSV file contains the survey questions as presented to participants during the study, along with their responses. In the analysis, the first 5 digits of the session_id are used as the userID.

Fields:

- session_id: (String) The unique identifier for the survey session. The first 5 digits are extracted and used as the userID in the analysis.
- question_id: (Integer) The numerical identifier for each survey question.
- question: (String) The full text of the survey question as displayed to the participant.
- response: (Integer) The participant’s answer, represented as a Likert scale response (1 - strongly disagree; 5 - strongly agree).

#### user_open_ended_questions_view.csv
Description:

This CSV file contains the open-ended survey questions along with the participants' free-text responses. As with other files, the first 5 digits of the session_id can be extracted and used as the userID in subsequent analyses.

Fields:

- session_id: (String) The unique identifier for the survey session. The first 5 digits are extracted and used as the userID in the analysis.
- question: (String) The text of the open-ended question presented to the participant.
- response: (String) The participant’s open-ended response.

#### user_response_details.csv
Description:

This file contains detailed response data for each trial in the study, including candidate information, participant choices, and AI recommendations across different study phases.

Fields:

- response_id: (String/Integer) Unique identifier for each response record.
- biased_gender: (String) Indicates the gender bias condition (e.g., 'F' or 'M').
- xAI: (Numeric) Indicates whether the XAI condition was active (e.g., 0 = no, 1 = yes).
- time_stamp: (Datetime/String) Timestamp when the response was recorded.
- session_id: (String) Unique session identifier (first 5 digits are used as the userID).
- phase_number: (Integer) Numerical identifier for the study phase.
- phase_name: (String) Descriptive label for the study phase (e.g., "Pre phase").
- p1: (Numeric) Identifier for data instance taken from the tabular candidate data for Candidate 1.
- p1_experience: (Numeric) Score for Candidate 1's prior work experience.
- p1_education: (Numeric) Score for Candidate 1's education.
- p1_references: (Numeric) Score for Candidate 1's references.
- p1_soft_skills: (Numeric) Score for Candidate 1's soft skills.
- p1_gender: (String) Gender of Candidate 1.
- p1_ethnicity: (String) Ethnicity of Candidate 1 (e.g., Eu = European descent, Af = African descent, Ea = East Asian descent).
- p1_user_image: (String) Filename for Candidate 1's headshot image.
- p2: (Numeric) Identifier for data instance taken from the tabular candidate data for Candidate 2.
- p2_experience: (Numeric) Score for Candidate 2's prior work experience.
- p2_education: (Numeric) Score for Candidate 2's education.
- p2_references: (Numeric) Score for Candidate 2's references.
- p2_soft_skills: (Numeric) Score for Candidate 2's soft skills.
- p2_gender: (String) Gender of Candidate 2.
- p2_ethnicity: (String) Ethnicity of Candidate 2.
- p2_user_image: (String) Filename for Candidate 2's headshot image.
- choice: (Numeric/String) The candidate (identifier) chosen by the participant.
- choice_gender: (String) Gender of the chosen candidate.
- choice_ethnicity: (String) Ethnicity of the chosen candidate.
- choice_image: (String) Filename for the chosen candidate's headshot image.
- ai_recommendation: (Numeric/String) The candidate recommended by the AI system.
- ai_gender: (String) Gender of the AI-recommended candidate.
- ai_ethnicity: (String) Ethnicity of the AI-recommended candidate.
- ai_image: (String) Filename for the AI-recommended candidate's headshot image.

#### user_response_details_incomplete.csv
Description:
This file contains the records of participants who did not complete the study, i.e., those who aborted early. It includes the partial responses captured up to the point of dropout. 

Fields: same as user_response_details.csv

#### user_phase_confidence_view.csv
Description:

This CSV file contains self-reported confidence ratings from participants, collected at various phases of the study. Each record corresponds to a specific study phase for a given session. In analysis, the first 5 digits of the session_id are used as the userID.

Fields:

- session_id: (String) Unique session identifier (first 5 digits are used as the userID).
- phase_number: (Integer) The numerical order of the study phase (e.g., 3 for Pre phase, 4 for Intervention Phase, 5 for Post Phase).
- phase_name: (String) Descriptive label for the study phase (e.g., "Pre phase", "Intervention Phase", "Post Phase").
- confidence: (Numeric) The participant's self-reported confidence score during that phase (1 - not at all, 5 - extremely)

#### user_attention_questions.csv
Description:

This file records participants' responses to attention-check questions (or rather, comprehension check) designed to ensure participants fully understood and paid attention to the study instructions.

Fields:

- session_id: (String) A unique identifier for the survey session. (Note: The first 5 digits can be used as the userID in analyses.)
- question: (String) The identifier for the attention-check question (e.g., "question1", "question2", etc.).
  - question1, correct answer: "Resource Operations Coordinator"
  - question2, correct answer: "Prior Experience, Education, References, Soft Skills"
  - question3, correct answer: "The candidate‘s „Experience“ has a lower value than the candidate‘s „Soft Skills“., The candidate‘s „References“ have received the maximal score of 10."
- response: (String) The participant’s response to the attention-check question.

#### session_info_demographics.csv
Description:

This CSV file contains session-level information and demographic data for study participants. It includes details about each session’s timing, the participant's age group and gender, and an indicator for whether the participant was blocked from the study due to failed comprehension checks.

Fields:

- session_id: (String) A unique identifier for the session.
- status: (Integer) Indicates the session status (e.g., 0 = no issues or 1 = incomplete data).
- start_time: (Datetime/String) The timestamp when the session began.
- end_time: (Datetime/String) The timestamp when the session ended.
- age_group: (String) Categorical age group of the participant (e.g., "18-24y", "25-34y", etc.).
- gender: (String) Self-identified gender of the participant (e.g., male, female, etc.).
- blocked: (Boolean) Indicator of whether the participant was blocked from the study due to failed comprehension checks (e.g., 1 for blocked, empty or 0 for not blocked).

### Directory ExperimentalData

#### xHR_CandidateData.csv
Description:

This file contains fully simulated candidate data used to present potential job seekers to participants in the study. The data simulates candidate profiles with demographic and qualification scores, supporting realistic hiring scenarios.

Fields:

- gender: (String) Candidate's gender (e.g., "F" for female, "M" for male).
- ethnicity: (String) Candidate's ethnicity (e.g., "Af" for African).
- glasses: (String/Integer) Indicator for whether the candidate is depicted wearing glasses ("1" indicates the presence of glasses).
- prior.exp: (Numeric) Score representing the candidate's prior work experience.
- education: (Numeric) Score representing the candidate's education level.
- references: (Numeric) Score representing the quality of the candidate's references.
- soft.skills: (Numeric) Score representing the candidate's soft skills.
- summed.points: (Numeric) Total score calculated by summing the scores for prior experience, education, references, and soft skills.

## License

This work is licensed under the Creative Commons Attribution 4.0 International License. To view a copy of this license, visit http://creativecommons.org/licenses/by/4.0/ or send a letter to Creative Commons, PO Box 1866, Mountain View, CA 94042, USA.

## How to cite

When Bias Backfires: The Modulatory Role of Counterfactual Explanations on the Adoption of Algorithmic Bias in XAI-Supported Human Decision-Making. Submitted to XAI 2025.

```
@inproceedings{
  title={When Bias Backfires: The Modulatory Role of Counterfactual Explanations on the Adoption of Algorithmic Bias in XAI-Supported Human Decision-Making},
  author={Kuhl, Ulrike and Bush, Annika},
  year={2025},
  pubstate={submitted}
}
```
