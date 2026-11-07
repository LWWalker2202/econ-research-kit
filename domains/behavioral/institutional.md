# Behavioral and Experimental Economics: Institutional and Ethical Background

## Institutional background

In this field the relevant "institution" is not a policy but the research infrastructure that produces the data: who the participants are, how they are recruited, where the session takes place, and what the ethics regime allows. That infrastructure is what determines which designs are credible, and it differs from the infrastructure assumed by the standard methods literature.

Participants in Chinese economics experiments are recruited mainly from three pools. University subject pools supply undergraduate and graduate students, typically recruited by announcement or by a standing registry, and are the default for laboratory work. Domestic online research panels supply larger and demographically broader samples at lower cost per observation, and have become the main alternative to the lab for survey experiments and for preference elicitation. International platforms supply cross-country samples and are used mainly when the design requires a comparison across populations. The three pools differ in attention, in the cost of a session, in the composition of the sample, and in what can be measured at all: reaction times and group interaction are natural in the lab and awkward online.

The standard paradigms also constrain what the institution of the experiment looks like. Public goods games need groups and repeated interaction, so they are usually run in the lab with a fixed matching protocol. Auctions, including the Becker-DeGroot-Marschak procedure and the Vickrey auction, need incentive-compatible payment and therefore a real good to allocate. Time preference is elicited with multiple price lists or convex time budgets, risk preference with the Holt-Laubach or Binswanger measures, and labor supply with a real-effort task whose output is verifiable. Each of these has a conventional implementation, and referees compare the implementation to the convention rather than reading the design from scratch.

Ethics review and informed consent are now a formal part of the process rather than an afterthought. Chinese universities increasingly require approval from an institutional review board or ethics committee before any human-subjects data collection, and journals ask for the approval reference at submission. Consent has to cover the purpose of the study, the payment scheme, data storage, and the right to withdraw. The Personal Information Protection Law (个人信息保护法), in force since 2021, adds requirements for handling personal data, which matters because experiments collect identifiers, demographics, and sometimes payment records. Deception is usually prohibited or heavily restricted, so designs that rely on false feedback need either a debriefing protocol or a different implementation.

Why this generates useful variation: random assignment is under the researcher's control, so the identification problem is different from observational work. The threat is not confounding by unobservables but the validity of the manipulation and of the outcome measure, and the external validity of the sample.

## Timeline

| Year | Event | Why it matters for research |
|---|---|---|
| 2013 | AEA RCT Registry launched | Pre-registration of experiments becomes a norm that journals and referees expect |
| 2015 | Open Science Collaboration replication report published | Raises the bar for statistical power and for reporting all pre-specified outcomes |
| 2019 | Nobel Memorial Prize awarded to Banerjee, Duflo, and Kremer | Increases the weight given to randomized designs in development and behavioral economics |
| 2020 | COVID-19 disrupts in-person laboratory sessions | Accelerates the shift to online panels and changes the composition of subject pools |
| 2021 | Personal Information Protection Law (个人信息保护法) in force | Consent, storage, and data-sharing rules for participant data become binding |

## Ready-to-cite paragraphs

The following paragraph is written to be pasted into a Design or Experimental Procedures section. Fill in the placeholders with the values used in the study and delete the ones that do not apply.

Participants were recruited from {{subject_pool}} and were told that the study was about economic decision making. Sessions took place in {{lab_or_platform}}, and the experiment was programmed in {{software}}. Each session lasted about {{duration}} minutes and included {{n_sessions}} sessions with {{n_per_session}} participants each. Participants gave written informed consent, were told that participation was voluntary and that they could leave at any time, and were paid a show-up fee of {{show_up_fee}} plus a performance-based payment that depended on their own decisions in {{paid_tasks}}. No participant was deceived. The study received ethics approval from {{ethics_committee}}, and the approval reference is reported in the paper. All decisions were anonymous to other participants and to the experimenter, and the data were stored on a server accessible only to the research team.

Two notes for the writer. First, the ethics paragraph is now expected in the paper itself rather than only in the appendix, so do not bury it. Second, if the sample comes from an online panel, state the platform, the recruitment filter, and the attention-check policy, because referees treat these as part of the design rather than as data-cleaning detail.

## Sources

- Institutional review board and ethics committee rules of the authors' universities (to confirm against the official codebook).
- Personal Information Protection Law of the People's Republic of China (中华人民共和国个人信息保护法).
- AEA RCT Registry and Open Science Framework, for pre-registration and materials deposit.
- Platform documentation and terms of service for the subject pools used (Credamo 见数, Prolific, MTurk) (to confirm against the official codebook).
- Journal data and code availability policies of the target outlet (to confirm against the official codebook).
