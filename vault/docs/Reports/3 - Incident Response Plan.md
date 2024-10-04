# Incident Response Plan

## Purpose

The purpose of this document is to outline the incident response plan for RandomCompany (“the client”) which is prepared by OD Company. The client has requested the services of OD Company to create an incident response plan to prepare the client for the eventual incident that will hit the company with its newfound growth. In the past, the client has focused on growing the company and incident management has been a low priority and as part of the remediation, the creation of an incident response plan. This document will describe the overall plan for responding to an incident and include details of roles and responsibilities, common incidents, mitigation and containment measures. The goal is to have a detailed plan that lays out a comprehensive plan for reducing damages because of incidents and ensuring all involved can effectively assist in the process.
## Scope

The scope of this document is to the entirety of the infrastructure that the client uses, including the systems and the stakeholders that rely on those systems. It will cover the key systems that the response team will be responsible and will cover the common incidents that may impact them. The response plan is not intended to describe procedures for every possible incident that may arise but provide guidelines on common incidents and help provide a foundation to use for incidents that were considered out of scope for the response plan. The following systems are within the scope of the response plan:
- Windows 11
- Windows Server 2022
- CentOS
- Wazuh
- Bee-box
- Metasploitable
- Kali
- Ubuntu 22.04 with BWapp
- Android

## Incident Response Team (IRT)

The response team’s formation will be the responsibility of the client to create and organize a team from their employees. This section will be a guide to the types of roles that are typically found in an IRT to assist in the creation of the team. The team will need a leader who is typically a manager who will be responsible for overseeing the team’s objectives. They will also act as a liaison between the IRT and upper management or key stakeholders.

The team will also need an IT specialist along with other IT members whose responsibilities are reacting to an incident and executing the response plan. They will work on verification of an incident, isolation or containment and eradication. The goal of these members is to respond quickly to mitigate damages to the organization and return the organization to regular operations. The IT members on the team should specialize in something related to incidents. For example, malware, forensics, rootkits, and network recovery. This is to ensure the team has the appropriate knowledge to act efficiently to an incident without having a gap in knowledge.

In addition, the team will need a public relations (PR) specialist whose responsibility is to craft a message when required to share with the public. It is important to keep the public informed on any incidents that may impact the service provided or the safety of their data. The goal of the PR is to craft a message that will not only get the message across but reduce the backlash the company may receive for the incident, ensuring that the client is doing everything they can to fix the situation and will continue to be dedicated to the safety of their customers.

## Communication Protocols

Communication between the members of the IRT will be done using the preferred method for communication for the client. This should be a mix of formal and informal communication. For example, official communication between the team and upper management should be done through meetings or emails so that there is a record. Between team members a use of instant messaging should be used to ensure the free flow of information between key members during an incident. All reports should be formally written and communicated to key stakeholders through email. Finally, the PR team’s communication should be done through official channels such as the company website and the use of social media for spreading the official message. If there is a strategic business partner, they should be kept in the loop and ensure correspondence are formal and have a trail. All employees are responsible for identifying potential incidents are reporting them through a formal process to the IRT for verification and further action. The client should setup a formal process, such as, a shared inbox or incident tracking tool that is monitored by all members of the IRT.

### Detection and Analysis

Detection of an incident will be a company wide effort. All employees will need to be alert and report anything that may be suspicious. It is then the responsibility of the IRT to verify the reports and react accordingly. That may be initiating the response plan, or carefully finetuning the intrusion detection system to reduce false positives.

The incident detection system that will be used on the client’s network will the Wazuh. Wazuh is an open-source security information and event management (SIEM) and extended detection and response (XDR) platform that can be deployed on various systems to help with the aggregation of logs and the detection of events. Wazuh will be deployed on all systems in the infrastructure, excluding the bee-box system as it not compatible with the version of Linux. The scope of this plan is the reaction to an incident and not the proactive measures to avoiding an incident and therefore will not comment on the state of the bee-box system.

It is the responsibility of the IRT to respond to alerts from Wazuh and from other employees on suspected incidents and utilize Wazuh’s aggregation of events and logs to conclude whether an incident has occurred. By utilizing Wazuh, IRT members will be able to continue to conduct their primary responsibilities while being alerted of potential incidents that may require their attention. Alerts should be thoroughly analyzed for indicators of an incident or false positive. When an incident is confirmed, a root cause analysis should be conducted to determine the cause and ultimately to determine a solution.

### Containment and Eradication

Once an incident has been confirmed the next step is to contain the incident so that it cannot spread beyond the initial system or to minimize the impacted systems. This should be done quickly so that the incident’s impact can be reduced. The first step of the containment process should be to isolate the network or system. This should be done physically by disconnecting it from the network. This method is the most ideal because its isolation but also enable a long-term solution for keeping it contained until recovery is complete. If this is not possible, the next solution should be to isolate the affected area through router and firewall rules. All traffic incoming from the affected area should be dropped to prevent lateral movement across the network. All outgoing traffic from the affected area should also be dropped to prevent the system from being used for malicious purposes outside the environment, such as a botnet.

Once the containment step is completed, the next step is eradication. With a root cause analysis already done on the incident, steps can be taken to ensure the eradication of the incident.  The steps for eradication will depend on the incident and here are some examples of the eradication process based on the type of incident:
- Unauthorized access – The access point is closed, and any persistence left behind is removed.
- Malware – The malware is removed from all systems infected. Vulnerabilities that allowed the malware incident to occur are mitigated.
- Phishing – assessment of the data loss/data provided, removal of any malicious software installed and changing over credentials.

## Recovery

After the incident is contained and eradicated, recovery back to regular business operations is the next step. Backs ups should be maintained for if it is necessary to restore to a previous backup in order to resume regular business operations. One thing to consider is that backups may be from a time when persistence was added to the network undetected. Care should be taken to ensure that backups are not also infected and will cause the incident to continue beyond what was expected. Once the incident has been eradicated and any backups restored, the system should be reintroduced into the network with the root cause fixed. Monitoring should continue to verify that the problem has been completely resolved and nothing was missed. The length of time to continue monitoring the incident can be a variable length of time and can be linked to the risk of it reoccurring and the confidence that the permanent solution will adequately mitigate the likelihood of reoccurrence. Once continuous monitoring of the incident can be wrapped up, the IRT team has finished their responsibilities and can return to their regular responsibilities and the company has fully returned to regular operations.

## Continuous Improvement

This document should be a living document and should be regularly reviewed and updated to reflect the security goals of the client. With the changing security landscape along with the changing company objectives, the roles and responsibilities of the IRT will continue to change or grow to adapt to the current environment. Additionally, after every incident, the IRT should meet and discuss the incident. They should discuss what went well, what went poorly and what can be improved for next time. Based on the feedback of the incident response, the process can be updated to incorporate the improvements that can be made to ensure the process continues to be effective, efficient and works for the entire response team. This is also the time to discuss effective proactive measures to ensure that the company is better prepared to prevent incidents from occurring. These measures can be discussed and brought forward to leadership to get buy in for implementing the proactive measures.