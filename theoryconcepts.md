## Security Through Obscurity:

--> Security through obscurity is the practice of concealing the details or mechanisms of a system to enhance its security. 

--> It relyies on secrecy (hiding how a system works) as the main method of protection.

--> Security through obscurity can be used as an extra layer, but never as the only layer of security.

--> It can be weak as: 

1. Once the secret is discovered, security collapses.

2. Attackers often reverse-engineer systems.

3. Not reliable as a standalone defense.

~ **Examples**: Using a secret or undocumented API endpoint as the only protection, Writing custom encryption and keeping the algorithm secret.

## Attack Surface: 

--> An attack surface refers to all the points of entry and potential vulnerabilities in a system, network, or application that an unauthorized user could exploit to gain access or disrupt operations.

--> It matters because:

1. A larger attack surface increases risk.

2. Harder to secure everything perfectly.

--> We can reduce the attack surface by:

1. Closing unused ports

2. Removing unnecessary features

3. Limiting permissions (Principle of Least Privilege)

4. Securing APIs properly

~ **Examples**: Login pages, APIs and endpoints, Open ports. 
