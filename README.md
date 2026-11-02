# Storybook-Entra-Identity-Foundation
## Skills Practiced

![Microsoft Entra ID](https://img.shields.io/badge/Microsoft_Entra_ID-0078D4?style=flat)
![User Administration](https://img.shields.io/badge/User_Administration-2563EB?style=flat)
![Security Groups](https://img.shields.io/badge/Security_Groups-2563EB?style=flat)
![Dynamic Membership](https://img.shields.io/badge/Dynamic_Membership-7C3AED?style=flat)
![Identity Attributes](https://img.shields.io/badge/Identity_Attributes-7C3AED?style=flat)
![Administrative Units](https://img.shields.io/badge/Administrative_Units-0891B2?style=flat)
![Scoped RBAC](https://img.shields.io/badge/Scoped_RBAC-0891B2?style=flat)
![Least Privilege](https://img.shields.io/badge/Least_Privilege-15803D?style=flat)
![Permission Testing](https://img.shields.io/badge/Permission_Testing-15803D?style=flat)
![Evidence Documentation](https://img.shields.io/badge/Evidence_Documentation-475569?style=flat)

Microsoft Entra ID lab covering users, groups, dynamic membership, and scoped administration
Storybook Studios Identity Foundation Lab

Overview

I built an employee directory for Storybook Studios, a fictional animation company, using Microsoft Entra ID. The goal was to organize employees, automate department group membership, and delegate a limited administrative task.

What I configured

I created four fictional employees: Tiana Palace in Finance, Shuri Udaku in Technology, Velma Dinkley in Security, and Peter Parker in Creative.

I created assigned security groups for each department and a dynamic Finance group using the Department attribute.

I created a Finance Administrative Unit containing Tiana and assigned Shuri the Password Administrator role within that scope.

What I tested

Changing Peter’s department to Finance automatically added him to the dynamic Finance group. Returning his department to Creative automatically removed him. His manually assigned Creative membership remained unchanged.

Shuri successfully reset Tiana’s password inside the Finance Administrative Unit. Her attempt to reset Peter’s password outside that unit was blocked.

After testing, I removed Shuri’s temporary administrative assignment.

What I learned

Dynamic membership depends on accurate identity attributes. Assigned membership requires separate maintenance when responsibilities change.

Administrative roles define what someone can do. Administrative Unit scope limits which accounts that role applies to.

Testing both permitted and blocked actions helped me verify the configuration. Removing temporary privileges completed the exercise.

Career relevance

This lab developed practical IAM skills in identity administration, membership automation, scoped role assignments, and permission testing.

It also strengthened governance skills in documenting permissions, collecting evidence, and removing privileges when the need ends. These are foundations I can apply when learning AI access governance.

Scope

This was a practice tenant with fictional employees. I tested directory membership and administrative permissions. Application access and AI specific controls were outside this lab.

## Lab Evidence

### Finance membership rule
The group uses the Department attribute to identify Finance employees.

![Finance dynamic membership rule](05_finance_dynamic_rule.png)

### Automatic membership addition
Peter joined the dynamic Finance group after his department changed to Finance.

![Peter added to Finance](07_peter_finance_membership.png)

### Automatic membership removal
Peter left the dynamic Finance group after his department returned to Creative.

![Peter removed from Finance](08_peter_removed_from_finance.png)

### Permitted administrative action
Shuri successfully reset Tiana’s password within the Finance Administrative Unit.

![Tiana password reset succeeded](11_shuri_tiana_reset_success.png)

### Blocked administrative action
Shuri was prevented from resetting Peter’s password outside the Finance Administrative Unit.

![Peter password reset blocked](12_shuri_peter_reset_blocked.png)
