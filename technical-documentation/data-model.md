# Data Model

Main entity of Financial Assurance module is Engagement. It can be one of four types: Audit, SpecialAudit, SpotCheck, MicroAssessment. Each of them has own special fields & related models. They are stored inside tenants and doesn't share across the countries.

![Micro Assessment](../.gitbook/assets/financial_asurance_micro_assessment.png)

Main part of data contains in base Engagement model. Additionally to connected models, Risks are used to store Questionnaire, their structure is shown below. They describe answers to the questions \(RiskBluePrint\) from Questionnaire. Questions can be grouped using categories \(RiskCategory\). Category has link to self, so they are organized to tree.

![Risks structure](../.gitbook/assets/financial_asurance_risks.png)

![Audit](../.gitbook/assets/financial_asurance_audit.png)

Risks are used in audit too to store key weaknesses, they are flexible enough to store question-like structures.

![Spot Check](../.gitbook/assets/financial_asurance_spot_check.png)

![Special Audit](../.gitbook/assets/financial_asurance_special_audit.png)



Global models are base and can be shared across countries, namely partners & purchase orders.  
Tenant models are Engagement with it's subclasses and all models that relates to it.

![Risks models](../.gitbook/assets/financial_asurance_risks%20%281%29.png)

Engagements are mapped to Purchase Orders. They were placed into single application because they are global and should be available from any country.

![](../.gitbook/assets/financial_assurance_po.png)

Purchase Orders are linked to Audit Firms, with their members.

Full models structure is shown on the scheme below.

![Global structure of Financial Assurance models](../.gitbook/assets/financial_asurance.png)



