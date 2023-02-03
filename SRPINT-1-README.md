# Week 1 Sprint
## Epics:
1. Prometheus should be configured to trigger alerts designed to warn that SLOs are in danger due to cluster conditions 
    - memory usage high 
    - cpu usage high 
    - file space low 
    - pods are consistently resetting 
    - etc 
2. Alertmanager should be integrated into the monitoring deployment in order to better facilitate alerts 
    - can silence alerts 
    - can integrate third party resources to receive alert information 
    - email 
    - pagers 
    - communication app (teams channel) 
    - etc 

## User stories:
1. Alert Triggering
- As a user, I want to have various alerts set up to monitor and track different service metrics and alert me when those metrics are doing bad 
- Number of story point: 3 
    - SLO should be reasonable 
    - Prometheus needs configuring 
        - Prometheus-rules yaml file needs updating for service monitoring 
    - More custom alerts must be made 
        - Account for CPU/memory usage, file space size, and pod state, for example 
- Intended velocity: 1-2 days
- Problem Tracking: 
    - Check Grafana and see if alerts show up 
    - Create test cases 
    - Create threshold 

2. Alert Notifications
- As a user, I want to receive a notification via email or teams if my application’s metrics start to fail, as well as whenever an alert in the application is raised. 
- Number of story point: 4
    - Kubernetes configMap object could be created to set up alert manager 
    - Manual Grafana alert set up for new individual alerts or silence 
    - The AlertManager window should be accessible through  
    - The AlertManager should successfully send email updates to the specified recipients
- Intended velocity: 1-2 days
- Problem Tracking: 
    - Check Grafana and see if alerts show up as active or silent 
    - Create test cases 

### update Jan 31, 2023
- DONE:
    - Created user stories
    - Performed research
- CURRENT SPRINT:
    - Create a service monitor
    - Create an alert manager
- IN PROGRESS:
    - Create a service monitor
    - Create an alert manager
- ON HOLD:
    - Multi-window multi-burn rate prometheus alert
    - Monitoring tools and planetarium pods are hosted on separate nodes
    - Sensitive information and monitoring tools sould be stored and referenced as secrets
    - Data saved by Prometheus and Loki should be stored outside of the cluster in a persistent volume
- NEXT UP:
    - Create customized metrics to monitor services
- QUESTIONS
    - Service monitor alerts: are the measurements provided or do we need to import/add anything?

### update Feb 1, 2023
- DONE: (+1)
    - Created user stories
    - Performed research
    - (+) Create a service monitor
- CURRENT SPRINT:
    - Create a service monitor
    - Create an alert manager
- IN PROGRESS: (-1)
    - Create an alert manager
- ON HOLD:
    - Multi-window multi-burn rate prometheus alert
    - Monitoring tools and planetarium pods are hosted on separate nodes
    - Sensitive information and monitoring tools sould be stored and referenced as secrets
    - Data saved by Prometheus and Loki should be stored outside of the cluster in a persistent volume
- NEXT UP:
    - Research and test out alert manager
- QUESTIONS
    - Alert manager configuration: SMTP?

### update Feb 2, 2023
- DONE: (-1)
    - Created user stories
    - Performed research
- CURRENT SPRINT: 
    - Create a service monitor
    - Create an alert manager
- IN PROGRESS: (+1)
    - Create an alert manager
    - (+) Service monitor DOWN
- ON HOLD:
    - Multi-window multi-burn rate prometheus alert
    - Monitoring tools and planetarium pods are hosted on separate nodes
    - Sensitive information and monitoring tools sould be stored and referenced as secrets
    - Data saved by Prometheus and Loki should be stored outside of the cluster in a persistent volume
- NEXT UP:
    - Research and test out alert manager
    - Fix service monitor
- QUESTIONS
    - Service monitor targeting app=planetarium-clusterip?
    - Lag in Prometheus server? Time zone difference?

### update Feb 3, 2023
- DONE: (+2)
    - Created user stories
    - Performed research
    - Create a stable service monitor
    - Create an alert manager
- CURRENT SPRINT: 
    - Create a service monitor
    - Create an alert manager
- IN PROGRESS: (-2) ALL DONE :-)
- ON HOLD:
    - Multi-window multi-burn rate prometheus alert
    - Monitoring tools and planetarium pods are hosted on separate nodes
    - Sensitive information and monitoring tools sould be stored and referenced as secrets
    - Data saved by Prometheus and Loki should be stored outside of the cluster in a persistent volume
- NEXT UP:
    - Maintain and improve alert manager
        - add silence
        - add other means other than email
    - Planned sprint epics for next week:
        - Multi-window multi-burn rate prometheus alert
        - Monitoring tools and planetarium pods are hosted on separate nodes
    - QUESTIONS
        - Setting up AWS SNS?

## Retrospective
- What went well? 
    - Alert setup was completed rapidly 
    - Well-maintained overall communication flow  
        - We knew what to do for the day and what to expect for the next day 
        - Constant exchange of ideas  
        - Structured workflow: P3 -> IM -> P3 -> Interview Prep 
- What could have been better? 
    - We underestimated the time it would take to complete our second user story 
- What will we do differently? 
    - Take more time at the beginning to plan out steps. Then, delegate tasks based on those steps.  
- Action items 
    - Constantly monitor application and services 
    - Start planning for next week

