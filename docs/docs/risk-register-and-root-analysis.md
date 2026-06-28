# Risk Register: AI-Assisted Magnetic Vine Robot for Minimally Invasive Surgery

## Overview

This risk register identifies potential AI-technical, operational, ethical, and equity risks associated with the development and deployment of an AI-assisted magnetic vine robot for minimally invasive surgical applications. Risks were evaluated based on their likelihood and potential impact on patient safety, clinical effectiveness, and healthcare accessibility.

| Risk Name                                              | Category     | Likelihood | Impact | Mitigation                                                                                                               | Signal of Success                                                          |
| ------------------------------------------------------ | ------------ | ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------- |
| Navigation Error in Complex Anatomy                    | AI-Technical | M          | H      | Validate navigation algorithms using diverse anatomical models and maintain surgeon oversight for critical decisions.    | >95% navigation accuracy during simulation and preclinical testing.        |
| Distribution Shift Between Training and Clinical Cases | AI-Technical | M          | H      | Train and validate using anatomies from different ages, sexes, and disease conditions. Continuously monitor performance. | Less than 5% performance variation across patient groups.                  |
| Failure to Detect Anatomical Obstacles                 | AI-Technical | M          | H      | Integrate multimodal sensing and obstacle-detection algorithms with surgeon verification.                                | Detection accuracy exceeds predefined safety threshold.                    |
| Over-Reliance on Simulated Training Data               | AI-Technical | H          | H      | Validate models using physical phantoms, cadaver studies, and progressively realistic testing environments.              | Consistent performance across simulation and experimental environments.    |
| Loss of Magnetic Control                               | Operational  | M          | H      | Implement redundant localization systems and emergency manual control mechanisms.                                        | Successful recovery from control failures during testing.                  |
| Excessive Force Applied to Tissue                      | Operational  | M          | H      | Incorporate force estimation, force limits, and emergency stop protocols.                                                | No tissue damage observed during validation testing.                       |
| Magnetic Interference with Medical Equipment           | Operational  | L          | H      | Conduct electromagnetic compatibility testing before deployment.                                                         | No interference incidents during validation studies.                       |
| Automation Bias Among Surgeons                         | Ethical      | M          | H      | Maintain human-in-the-loop operation and require surgeon approval for critical actions.                                  | Surgeons retain override authority and actively review recommendations.    |
| Limited Explainability of AI Navigation Decisions      | Ethical      | M          | M      | Provide visual explanations and confidence metrics for AI-generated navigation suggestions.                              | Surgeons report understanding AI recommendations during usability testing. |
| Inadequate Informed Consent                            | Ethical      | M          | M      | Clearly communicate the role, benefits, and limitations of AI-assisted robotics to patients.                             | High patient comprehension scores during consent assessments.              |
| Algorithm Bias from Non-Representative Training Data   | Equity       | M          | H      | Use diverse anatomical datasets and conduct fairness audits.                                                             | Comparable performance across demographic groups.                          |
| Unequal Access to Surgical Robotics Technology         | Equity       | H          | M      | Develop scalable, cost-conscious designs suitable for resource-limited healthcare settings.                              | Demonstrated adoption across hospitals with varying resource levels.       |

# Risk Memo: Top Three Risks

## 1. Navigation Error in Complex Anatomy

The vine robot must navigate through highly variable anatomical pathways. If the AI incorrectly identifies a safe route, the robot could contact or damage surrounding tissues. This risk is particularly important because anatomical differences between patients may not be fully represented in training data. Extensive testing and surgeon oversight are necessary to minimise this risk.

## 2. Excessive Force Applied to Tissue

Although vine robots are designed to be compliant and flexible, unintended forces may still be applied during navigation. Excessive force could result in tissue injury, perforation, or bleeding. Force monitoring systems, predefined safety thresholds, and emergency stop functions should be incorporated to reduce the likelihood of harm.

## 3. Over-Reliance on Simulated Training Data

Much of the current development of magnetic vine robots occurs in simulation and laboratory settings. Real surgical environments are significantly more complex and may contain anatomical variations, physiological motion, and unforeseen obstacles that are absent from simulations. Validation in increasingly realistic environments is therefore critical before clinical deployment.

## Root Analysis

# Case Study: Bias in the Optum Healthcare Risk Prediction Algorithm

In 2019, researchers published a study in *Science* revealing significant racial bias in a widely used healthcare algorithm developed by Optum. The algorithm was used by hospitals and insurers across the United States to identify patients who would benefit from high-risk care management programmes. These programmes provide additional clinical support, monitoring and resources to patients with complex health conditions.

The harm occurred because the algorithm systematically underestimated the healthcare needs of Black patients. Researchers found that Black patients who were equally sick as White patients were much less likely to be selected for additional care. As a result, many Black patients who could have benefited from extra support were excluded from programmes intended to improve health outcomes.

The root cause of the problem was not a programming error but a flawed design decision. Instead of predicting actual health status, the algorithm was trained to predict future healthcare costs. The developers assumed that patients with greater healthcare needs would generate higher medical expenditures. However, due to longstanding disparities in healthcare access, Black patients often incur lower healthcare costs than White patients with similar levels of illness. Consequently, healthcare spending was an unreliable measure of true medical need.

Because the algorithm used healthcare costs as its target variable, it learned patterns that reflected existing inequalities within the healthcare system. Although race was not included as an input, the model indirectly reproduced racial disparities through other variables associated with healthcare utilisation and spending. The algorithm therefore appeared accurate from a technical perspective while producing biased outcomes in practice.

The system also failed to anticipate the impact of social and structural factors on healthcare expenditure. Lower spending does not necessarily indicate better health; it may reflect barriers to accessing care. By treating expenditure as a proxy for illness severity, the algorithm embedded historical inequities into its decision-making process.

Several safeguards could have identified the issue earlier. Developers should have conducted fairness audits across demographic groups before deployment and evaluated outcomes based on actual clinical need rather than cost. In addition, clinicians and public health experts should have been involved in selecting the target variable used for model training. Continuous post-deployment monitoring could also have detected disparities before the system was adopted at a large scale.

This case demonstrates that AI systems can cause harm even when they appear technically accurate. For the magnetic vine robot project, it highlights the importance of using representative datasets, evaluating performance across different populations, and ensuring that model outputs are assessed for fairness as well as accuracy.

