# Backend Module structure

### Audit module files structure

![](../.gitbook/assets/screenshot-from-2018-09-19-18-00-34.png)

`management` - specific management commands. in our case there is only one command for updating permissions.  
`migrations` - database migrations  
`notifications` - templates for email notifications  
`purchase_order` - nested global application to keep shared across the countries information about auditor firm  
`serializers`- rest framework serializers  
    - `auditor.py` - serializers for auditor firm, staff members, purchase orders  
    - `engagement.py` - engagement related serializers \(Audits, SpotChecks, Attachments, etc\)  
    - `export` - everything that is related to csv & pdf exports  
    - `mixins.py` - specific serializers mixins  
    - `risks.py` - Risks serializers \(mainly used in MicroAssessment Questionnaire\)  
- `templates` - templates to be used in various exports. visit letter & activities pdf export  
- `tests` - tests for models, views, serializers, transitions flow  
- `transitions` - everything that is related to fsm transitions  
    - `conditions.py` - custom checks for transitions. for example in case of submitting report we need to be assured that report attachments are exists.  
    - `serializers.py` - transitions serializers to validate their input arguments \(see more in [permissions framework section]()\)  
- `admin.py` - admin site definitions for models  
- `apps.py` - python app configuration  
- `conditions.py` - conditions to perform FSM transitions. [see more details here]()  
- `exports.py` - csv renderers  
- `filters.py` - rest framework views filters  
- `metadata.py` - base metadata class to be used in viewsets. more in [API Metadata section]()  
- `models.py` -  country-related audit models  
- `signals.py` - app signals. custom logic for user deletion; sending notifications in case of assigning action points  
- `urls.py` - app urls  
- `views.py` - just set of views to work with models

### audit.purchase\_order app

![](../.gitbook/assets/screenshot-from-2018-09-19-18-02-08.png)

To store global data that is related to Auditor Portal, was implemented nested application named `purchase_order`.   
Views and serializers are still placed in parent application to keep consistant place for all module logic.

App consists of:  
- `migrations` - database migrations  
- `tests` - unit tests  
- `admin.py` - admin site config  
- `apps.py` - python app config  
- `models.py` - partner with their staff members  
- `synchronizer.py` - VISION partner synchronizer  
- `tasks.py` - periodic tasks, which are responsible to keep partners synced with VISION  


