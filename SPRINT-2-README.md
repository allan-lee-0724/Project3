# Week 1 Sprint
## Epics:
1. Prometheus should be configured to alert using a multi-window multi-burn rate strategy for relevant SLIs 
2. Epic 2: Planetarium Cluster should be configured so monitoring tools and planetarium pods are hosted on separate nodes, ensuring that any cascading failures on the planetarium nodes do not hinder the monitoring tools, and vice versa 
    - researching taints and tolerations would be a good starting point for this epic 

## User stories:
1. Multi-Window Multi-Burn Rate 
- As a user, I want alerting with high precision and recall percentages while keeping detection time and alert reset times down. 
- Number of story point: 3 
    - Prometheus rules file is reconfigured to use both short and long range on the same data for alerts 
    - Alert expressions are re-written to use burn rate 
    - Grafana configured to display Multi-Window Multi-Burn Rate panels 
- Intended velocity: 1-2 days
- Problem Tracking: 
    - Check Grafana and see if alerts show up as active or silent 
    - Create test cases  

2. Separate Monitoring Tool Nodes 
- As a user, I do not want my monitoring tools to fail if the application happens to fail.  
- Number of story point: 5
    - Planetarium Cluster is configured with separate nodes for monitoring tools and planetarium pods. 
    - Monitoring tools are hosted on a node separate from the planetarium pods. 
    - Planetarium pods are hosted on a node separate from the monitoring tools. 
    - Any cascading failures on planetarium nodes do not affect the functioning of monitoring tools. 
    - Any cascading failures on monitoring tool nodes do not affect the functioning of planetarium pods. 
- Intended velocity: 3-4 days
- Problem Tracking: 
    - Prometheus can collect metrics on node performance and health, including CPU and memory utilization, and detect cascading failures as a result of these metrics. 
    - Grafana can be used in conjunction with Prometheus to visualize the metrics collected and provide a visual representation of the health of the cluster, including any cascading failures. 