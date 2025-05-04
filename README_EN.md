<div align="center">
<!-- <img src = "https://github.com/GoThereGit/Chinese-AMR/blob/main/img/camrp2024.png" width=200> -->
</div>

[<p align="right"><font size=50><ins>English Version</ins></font>](https://github.com/UM-FAH-Yuan/FIE2025/blob/main/README_EN.md)</p> 

# <p align="center"><font size=50><strong>第一届中文叙实性推理评测任务</strong></font></p> 
<p align="center"><font size=50><strong>Factivity Inference Evaluation 2025</strong></font></p> 

# Recent Updates

![Static Badge](https://img.shields.io/badge/20250503-Q%20%26%20A-blue?style=plastic)

- **Q1:** I just tested the submission method on the Tianchi platform, but it keeps failing, possibly due to incorrect formatting. I suggest the organizers consider providing an answer template corresponding exactly to your evaluation set. I tried again and still couldn’t submit—maybe the order is wrong or another issue.

```json
{
  "d_id": "nat_acc_001",
  "answer": "U"
}
```

May we have a submission template? This would avoid such issues; the template’s order should match the evaluation set, at minimum specifying whether to list artificial items before natural ones.

- **A1:** Thank you for your feedback. We have received it! We will first coordinate with the Tianchi platform, and the example submission code has now been updated on our site (see [Submission Example](#daimashili)). Note: on the Tianchi platform results page, “art_acc” and “nat_acc” indicate accuracy on the artificial and natural subsets respectively, and are unrelated to data IDs. ![Static Badge](https://img.shields.io/badge/20250504__updated-blue?style=plastic)

- **Q2:** We still have questions about the annotations for ArtS_085 and ArtS_087.
- **A2:** Regarding the dispute over the word “披露”(disclose), we currently prefer to maintain the existing annotation results. To ensure data stability, we will not adjust the sample or evaluation sets before the official competition begins. However, we welcome further discussion on such controversies after the evaluation concludes. Such verbs indeed warrant deeper study. We believe the differences between your team’s understanding and our annotations stem mainly from judgments of certainty and the scope of the options. 

  Considering that our initial annotation scheme used a three-way classification (True / False / Uncertain), individual items may spark debate. However, we believe this does not hinder teams’ effective evaluation of the task itself. As emphasized in the task announcement, our primary goal is to promote research on factivity inference in Chinese. We sincerely appreciate your in-depth reflection and invaluable feedback. In the second edition of this evaluation, we will carefully incorporate all opinions to refine our annotation scheme and more precisely measure models’ performance in factivity inference.

- **Q3:** Is it still possible to submit the participation agreement now?
- **A3:** Yes. You may submit the signed participation agreement at any time before the rankings are finalized. We recommend all teams submit their signed agreement as early as possible to avoid disqualification due to incomplete information.

![Static Badge](https://img.shields.io/badge/20250501-Q%20%26%20A-blue?style=plastic)

- **Q1:** Can two models be used in tandem? Does this count as the fine-tuning track or the non-fine-tuning track?
- **A1:** If by “tandem use” you mean testing with multiple models and then combining the best results, that is not allowed and is considered cheating. Our main purpose is to survey current large models’ performance on Chinese factivity inference; patching results together undermines this goal. If multiple models are combined, complete results must be provided for each model to compare performance fairly. Moreover, as stated in the briefing, evaluation results are not the sole criterion for recommending technical reports—innovation in methodology and design also matters. Thus, there is no need to combine outputs for higher accuracy.

- **Q2:** Some members raised issues about “披露”(disclose) vs. “揭露”(reveal) in ArtS indices 84–87 and 236–238.
- **A2:** After discussion, we have decided no changes are needed for these annotations.

- **Q3:** For the non-fine-tuning track, what are the restrictions on model usage? Are LLMs invoking tools (or RAG) allowed? Should we define clear boundaries on model use to ensure fairness?
- **A3:** Factivity inference is not purely syntactic but spans lexicon, syntax, semantics, and pragmatics. Introducing a single external tool may not significantly improve inference effect. However, the teams are encouraged to explore external resources (e.g., analysis results, other datasets) as part of your prompts. Teams must document their algorithms and resources in their technical reports, so fairness concerns are mitigated. As with any evaluation, cheating is possible; please preserve your code for verification.

- **Q4:** Regarding non-fine-tuning, does a training-free method comply? These techniques don’t update parameters but merge them. Does fine-tuning only mean gradient descent, excluding parameter merging?
- **A4:** Modifying decoding strategies without weight updates is allowed. Our definition of non-fine-tuning requires no gradient descent and no weight modifications.

![Static Badge](https://img.shields.io/badge/20250430-Q%20%26%20A-blue?style=plastic)

- **Q1:** Who should receive the signed PDF of the participation agreement? Via email? How do we confirm team registration? Does the signatory need an supervisor’s signature? Should the supervisor also join the Tianchi team or add them after rankings are finalized? This question is about how names appear on certificates.
- **A1:** The agreement includes fields for your team to complete. Please have the team leader fill them, save as PDF, and email to the organizer at guanliang.cong@connect.um.edu.mo. The leader is responsible for communication with the organizers. Upon receipt, we will issue a team number, confirming your registration.

  Since a technical report is required, you may include supervisors’ names there. Certificate details will be finalized with awardees before issuance. ![Static Badge](https://img.shields.io/badge/20250501__updated-blue?style=plastic)

- **Q2:** Where can we find the QQ group link?
- **A2:** After sending the signed agreement by email, we will reply with a team number and the QQ group QR code. You may scan to join. The DingTalk group QR code has been posted on the Tianchi competition page ([link](https://tianchi.aliyun.com/competition/entrance/532342)).

- **Q3:** For the non-fine-tuning track, is multi-agent collaboration allowed?
- **A3:** Absolutely! We encourage diverse approaches, including multi-agent methods.

![Static Badge](https://img.shields.io/badge/20250428-Q%20%26%20A-blue?style=plastic)

- **Q1:** Can you preview which questions were modified in the artificial subset?
- **A1:** The modifications to the artificial subset have been uploaded. See [ArtS-20250427updated.csv](https://github.com/UM-FAH-Yuan/FIE2025/blob/main/Sample_Set/ArtS-20250427updated.csv).

- **Q2:** Regarding differing evaluation sets for fine-tuning vs. non-fine-tuning, we agree and have a suggestion: exclude “假装”(pretend) verbs from scoring in both sets initially, then use them as a distinguishing feature. Fine-tuning teams learn from the provided “U” labels, while non-fine-tuning teams interpret “假装”(pretend) items independently, and their accuracy on these is not counted. If teams submit identical answers on “假装”(pretend), we can review code and advance research on “假装”(pretend) verbs.
- **A2:** We find distinguishing tracks by data ID suffix simpler. Currently, fine-tuning data IDs end with `_FT` and non-fine-tuning with `_prompt`. Teams’ backgrounds and interests vary; requiring everyone to address “假装”(pretend) verbs may be challenging.

- **Q3:** How do we know whether our approach is fine-tuning or non-fine-tuning? For example, is adjusting the temperature parameter fine-tuning?
- **A3:** The distinction was explained at last night’s briefing; see the video. Temperature adjustment is not fine-tuning. It only affects response consistency, not model parameters.

- **Q4:** Could you share the papers mentioned by Prof. Li at the end of the briefing in the QQ group? The forum recording is unavailable.
- **A4:** Recommended Chinese papers:
  - https://aclanthology.org/events/ccl-2024/#2024ccl-3
  - https://aclanthology.org/events/ccl-2023/#2023ccl-3
  - https://aclanthology.org/2023.ccl-3.12.pdf
  - https://aclanthology.org/2023.ccl-3.9.pdf

  English papers: proceedings of CoNLL and SemEval.

![Static Badge](https://img.shields.io/badge/20250427-UPDATE-brightgreen?style=plastic)

We held the second briefing tonight. Recording:
- **Title:** FIE2025 Task Briefing 20250427
- **Date:** 2025-04-27 20:05:07
- **Link:** [Tencent Meeting](https://meeting.tencent.com/crm/2BLk3pQk47) (no password)
- **Slides:** [Download PDF](https://github.com/UM-FAH-Yuan/FIE2025/blob/main/meeting_record_20250427.pdf)

![Static Badge](https://img.shields.io/badge/20250426-Q%20%26%20A-blue?style=plastic)

- **Q1:** After registering on Alibaba Cloud Tianchi, do we need to register on GitHub as well?
- **A1:** After registering on Tianchi, you must sign the participation agreement. We are updating the Tianchi page to include it. Please review both documents and return the signed agreement by email.
- **Q2:** Is the Tianchi leaderboard just a reference? Will final rankings be announced after May 15 (technical reports) and on June 1 by organizers?
- **A2:** Yes, the Tianchi leaderboard is real-time reference only. Final results are confirmed after technical report submission. The submission page won’t close immediately on May 12, but results are due by then. Final rankings will be announced on June 1.

![Static Badge](https://img.shields.io/badge/20250425-Q%20%26%20A-blue?style=plastic)

- **Q1:** Our team questioned answers for artificial samples 67, 80, 89, 90, 225, 233. We noticed samples 381, 382, 665, 666 were revised but 533, 534 were not. We think these three pairs could be combined as “U.” What is the organizer’s view?
- **A1:** After careful discussion, we believe the revised natural subset answers are correct and will not be changed. A few adjustments were made to the artificial subset; the updated full version will be uploaded this weekend. ![Static Badge](https://img.shields.io/badge/20250504__updated-blue?style=plastic) See [ArtS-20250427updated.csv](https://github.com/UM-FAH-Yuan/FIE2025/blob/main/Sample_Set/ArtS-20250427updated.csv).
- **Q2:** We suggest each team participate in only one track to avoid submitting fine-tuning results in the non-fine-tuning track. Since fine-tuning accuracy is higher, dual participation could skew rankings.
- **A2:** We consider the current setup appropriate. Restricting teams to one track may limit multifaceted research. We require code submission for verification and will remind teams to select the correct result file. We are also considering differentiated evaluation sets (e.g., extra item for fine-tuning) to reduce submission errors.
- **Q3:** Team members find five days too short. We suggest seven days for fine-tuning track and seven to ten days for non-fine-tuning, since manual prompt engineering takes longer.
- **A3:** After review, we extended both tracks to seven days and slightly advanced the evaluation set release. Details were discussed at the April 27 briefing. ![Static Badge](https://img.shields.io/badge/20250504__updated-blue?style=plastic) See schedule on our site.

![Static Badge](https://img.shields.io/badge/20250423-Q%20%26%20A-blue?style=plastic)

- **Q1:** Must evaluation papers be submitted via OpenReview separately from technical reports?
- **A1:** Yes. From May 20 to June 1, we will review technical reports and recommend top teams to submit full papers to the workshop via OpenReview (group: cips-cl.org/CCL/2025/Workshop/Eval). DO NOT use the main conference link.
- **Q2:** The technical report deadline is May 15, but OpenReview shows May 11. Which is correct?
- **A2:** OpenReview now shows: Submission Start: May 20 2025 12:00AM UTC-0, Deadline: Jun 01 2025 12:00AM UTC-0. Please refer to this arrangement.

![Static Badge](https://img.shields.io/badge/20250421-Q%20%26%20A-blue?style=plastic)

- **Q1:** May models output content beyond T/F/U/R? For example, include chain-of-thought, then manually extract the answer.
- **A1:** Yes. As long as the answer portion is explicit (“True”, “False”, “Uncertain”) and consistent, it is allowed. If manually extracting answers, include reproducible rules and save code for auditing.
- **Q2:** Are multi-turn dialogues allowed?
- **A2:** In theory, yes, including multi-turn. However, we prohibit artificially correcting model answers within the dialogue (e.g., “You’re wrong; I think…”) as it undermines true reasoning assessment.

![Static Badge](https://img.shields.io/badge/20250417-Q%20%26%20A-blue?style=plastic)

- **Q1:** Must team members register on Tianchi to participate? Does this affect result submission?
- **A1:** Our evaluation relies on the Tianchi platform. Please register at https://tianchi.aliyun.com/competition/entrance/532342 and sign up for the competition. ![Static Badge](https://img.shields.io/badge/20250504__updated-blue?style=plastic)
- **Q2:** Will verbs in the sample set (e.g., “pretend”) appear again in the evaluation set? Do sample-set verbs cover evaluation-set verbs?
- **A2:** Sample-set verbs reappear in the evaluation set but cover only half. We intentionally limit overlap to test models’ generalization.
- **Q3:** We want to know if answers for “pretend” items 25, 26 in the old natural sample (natural_sample_202412311817.json) were correct, as we based our prompts on them.
- **A3:** For “pretend,” we decided to retain all such items in the evaluation set but exclude them from scoring. Rationale: “pretend” is special, akin to biological camouflage. When the subject pretends to be in a state, the embedded proposition is true; when pretending to perform an action, scholars disagree on completion. To avoid disagreement, we keep all “pretend” items but do not count them. We will select replacement items from other verbs to maintain the total count before final release.

# Registration

Please carefully read the [FIE2025 Participation Agreement](https://github.com/UM-FAH-Yuan/FIE2025/blob/main/Agreement%20%26%20License/%E7%AC%AC%E4%B8%80%E5%B1%8A%E4%B8%AD%E6%96%87%E5%8F%8...
