# AWS Automated Threat Detection & Response

> Event-driven cloud security project using GuardDuty, EventBridge, Lambda, and SNS to automatically detect and contain threats.

---

## Overview

This project demonstrates a **real-time automated incident response pipeline** in AWS.

When a critical threat is detected:

1. GuardDuty generates a finding  
2. EventBridge filters critical events  
3. Lambda isolates the EC2 instance  
4. SNS sends an alert notification  

---

## Architecture
GuardDuty → EventBridge → Lambda → EC2 Isolation
↓
SNS → Email Alert

---

## Technologies Used

- Amazon GuardDuty  
- Amazon EventBridge  
- AWS Lambda (Python)  
- Amazon SNS  
- Amazon EC2  
- AWS IAM  

---

## ⚙️ Implementation Steps (With Screenshots)

### 1. Enable EventBridge

![EventBridge](./screenshots/01-eventbridge.png)

---

### 2. Enable GuardDuty

![GuardDuty](./screenshots/02-guardduty.png)

---

### 3. Launch EC2 Instance

![EC2 Launch](./screenshots/03-ec2-launch.png)

---

### 4. Verify EC2 Running

![EC2 Running](./screenshots/04-ec2-running.png)

---

### 5. Create Containment Security Group

![Security Group](./screenshots/05-security-group.png)

---

### 6. Create Lambda Execution Role

![Lambda Role](./screenshots/06-lambda-role.png)

---

### 7. Create EventBridge Trust Policy

![EventBridge Trust](./screenshots/07-eventbridge-trust.png)

---

### 8. Create EventBridge Role

![EventBridge Role](./screenshots/08-eventbridge-role.png)

---

### 9. Attach Permissions

![Permissions](./screenshots/09-role-permissions.png)

---

### 10. Create SNS Subscription

![SNS Subscription](./screenshots/10-sns-subscription.png)

---

### 11. Confirm SNS Email

![SNS Confirmation](./screenshots/11-sns-confirmation.png)

---

### 12. SNS Subscription Active

![SNS Confirmed](./screenshots/12-sns-confirmed.png)

---

### 13. Create Lambda Function

![Lambda Role Select](./screenshots/13-lambda-role-select.png)

---

### 14. Add Lambda Code

![Lambda Code](./screenshots/14-lambda-code.png)

---

### 15. Configure Instance + Security Group IDs

![Lambda Config](./screenshots/15-lambda-config.png)

---

### 16. Create EventBridge Rule (JSON Pattern)

![Event Pattern](./screenshots/16-event-pattern.png)

---

### 17. Add Lambda Target

![Target Lambda](./screenshots/17-target-lambda.png)

---

### 18. Add SNS Target

![Target SNS](./screenshots/18-target-sns.png)

---

### 19. Generate GuardDuty Findings

![Findings](./screenshots/19-findings.png)

---

### 20. Verify Containment

![Containment Result](./screenshots/20-containment-result.png)

---

## ✅ Results

- EC2 instance automatically isolated  
- Security group replaced with containment group  
- Email alerts successfully triggered  
- Fully automated response pipeline  

---

## Key Insights

- Event-driven architecture enables real-time security automation  
- GuardDuty provides built-in threat intelligence  
- Lambda allows immediate remediation without manual action  
- SNS ensures visibility during incidents  

---

## 📚 Lessons Learned

- IAM permissions are critical for automation to work  
- EventBridge rules must match exact event patterns  
- There is slight delay in AWS event propagation  
- Security groups are effective for quick containment  

---

## Challenges

- Debugging IAM role permissions  
- Correctly configuring Lambda environment variables  
- EventBridge JSON filtering syntax  
- Delay in GuardDuty sample findings  

---

## Recommendations

### Security
- Apply **least privilege IAM policies**
- Restrict SSH to trusted IPs only  

### Monitoring
- Integrate **CloudWatch logs**
- Enable **AWS Security Hub**

### Automation
- Extend Lambda to:
  - Stop instances  
  - Snapshot volumes  
  - Tag compromised resources  

### Notifications
- Add Slack / Teams / PagerDuty integration  

---

## Conclusion

This project showcases how to build a **fully automated cloud security response system** using AWS-native services.

It highlights:
- Real-time detection  
- Automated containment  
- Scalable event-driven design  

---

## Project Structure
├── README.md
├── Lambda.py
├── Event_Pattern_Critical.json
├── EventBridge_Role_Trust.json
└── screenshots/

---

## Reference
- Pluralsight Lab  
- Lambda Code:  
https://github.com/pluralsight-cloud/LAB---AWS-Live-Threat-Detection-and-Response-Simulation/blob/main/Lambda.py
