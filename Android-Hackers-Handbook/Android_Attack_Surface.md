## Understanding Android's Attack Surface

### Attack Terminology

**CIA**: confidentiality, integrity, accessibility

**CVSS**: Common Vulnerability Scoring System (CVSS) - a widely accepted standard for classifying and ranking vulnerability intelligence

**Attack Vector**: The means by which an attacker makes their move. 
- describes methods used to carry out attack
- classified based on authentication, accessibility and difficulty

**Attack Surface**: The characteristics of a target that makes it vulnerable to attack
- refers to the code an attacker can execute and therefore attack
- doesn't depend on attacker's actions or require a vuln
- describes where vulnerabilities may be
- studying one attack surface often reveals other possible attack surfaces
- reaching an attack surface may be possibly by an attack vector

### Classifying Attack Surfaces
- size of attack surface = how much it interferes with other systems, users, code, etc. 
- Android known to interface with anything and everything -- "Droid Does"; therefore large attack surface

**Attack Vector**: important since user interaction and authN requirements can limit the impact of a vuln
**Privileges Gained**: privileges can also limit impact
**Memory Safety**: memory-safe languages can prevent certain classes of vulns compared to those that are not memory-safe (eg. C, C++)
**Complexity**: complexity can lead to difficulty in managing a project and an increased risk of mistakes 

- by focusing on risky attack surfaces (classified with the above properties), the system can be attacked or secured more efficiently
- attackers tend to focus on risky attack surfaces because of the ratio of risk to reward



 



