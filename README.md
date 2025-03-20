# BiasBackfiresXAI2025
This repository contains the user data and analysis code accompanying the paper: 
> When Bias Backfires: The Modulatory Role of Counterfactual Explanations on the Adoption of Algorithmic Bias in XAI-Supported Human Decision-Making. Submitted to XAI 2025.

## Abstract
Although the integration of artificial intelligence (AI) into everyday tasks improves efficiency and objectivity, it also risks transmitting bias to human decision-making. In this study, we conducted a controlled experiment that simulated hiring decisions to examine how biased AI recommendations - augmented with or without counterfactual explanations - influence human judgment over time. Participants, acting as hiring managers, completed 60 decision trials divided into a baseline phase without AI, followed by a phase with biased (X)AI recommendations (favoring either male or female candidates), and a final post-interaction phase without AI. Our results indicate that the participants followed the AI recommendations 70% of the time when the qualifications of the given candidates were comparable. Yet, only a fraction of participants detected the gender bias (8 out of 294). Crucially, exposure to biased AI altered participants’ inherent preferences: in the post-interaction phase, participants’ independent decisions aligned with the bias when no counterfactual explanations were provided before, but reversed the bias when explanations were given. Reported trust did not differ significantly across conditions. Confidence varied throughout the study phases after exposure to male-biased AI, indicating nuanced effects of AI bias on decision certainty. Our findings point to the importance of calibrating XAI to avoid unintended behavioral shifts in order to safeguard equitable decision-making and prevent the adoption of algorithmic bias.

## Overview of files

### Directory UserData

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

### Directory ExperimentalData

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
