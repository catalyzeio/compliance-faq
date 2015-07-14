# How does Catalyze handle encryption?

Catalyze encrypts all data in transit and at rest. The only form of communication Catalyze supports for customers is SSL, and Catalyze encrypts all data within its network using TLS version 1.2. For data at rest we use 4096-bit RSA key pair to protect the data. Our data integrity policy is [here][1].

# How does Catalyze you delete data?

When servers are decommissioned, we unmount the encrypted volume and wipe the underlying raw block storage volume prior to deleting the block storage resource. Part of the wiping process is writing over the existing customer data to assure no future access.

# Where are Catalyze data centers located?

All Catalyze data centers are currently located within the continental United States. We are aware of the data sovereignty rules in different geographies and have expanded data center coverage in the past to meet customer requirements. We are exploring non-US based data centers currently to expand our geographic reach. If you require data centers to be located outside the US, please [reach out][2] to explore options.

# How does Catalyze back up data for customers?

Backups for all customers are performed daily. 7 days of backups are retained. This is documented in more detail [here][3]. Backups are sent to a different site. Disaster recovery related details are outlined here - https://policy.catalyze.io/#disaster-recovery-policy. 

# Does Catalyze have a disaster recovery plan in place?

Yes, Catalyze has a disaster recovery plan outlined [here][4]. The disaster recovery plan is tested both through tabletop and technical exercises.

# What is the general process for keeping operating systems up to date?

We track and subscribe to lists (email and other notifications) published by vendors, OS, and framework developers to track vulnerabilities as discovered. Ubuntu is the base OS run in our netwworks. Updates published by Canonical (for example) are deployed as approved post application testing. Application level security patches and services packs are also deployed after testing. Other vulnerabilities / CVEs are also tracked such as pertaining to SSL/TLS, NGINX etc.

The recent POODLE, GHOST and FREAK vulnerabilities exposed were either patched immediately after testing to ensure minimal impact (where there was expected impact, that was communicated so customers could take steps to resolve). All of these follow the same Risk Assessment process described earlier.

# How are updates / patches applied to the environment?

Any patches or changes to the infrastructure must follow our Risk Assessment policy which is documented in detail [here][5].
Generally, software patches and updates will be applied to all systems in a timely manner. In the case of routine updates, they will be applied after thorough testing. In the case of updates to correct known vulnerabilities, priority will be given to testing to speed the time to production. Critical security patches are applied within 30 days from testing and all patches are applied within 90 days after testing. Mission critical patches will be deployed in less than 7 days after testing.

# Does Catalyze run intrusion detection software (IDS)?

Yes, Intrusion Detection Systems (IDS) have been installed on all hosts and logs reviewed regularly as defined [here][6]. IDS logs and alerts are sent and reviewed by the Catalyze Security Team.

Additionally, all hosts run customized version of App Armor profiles have been set up to further harden the OS and jail processes.

# Does Catalyze scan for vulnerabilities?

Yes, Catalyze scans all of its hosts and networks using [Nessus][7] from Tenable. The results of scans are reviewed by our Security Officer each week and all found issues are either 1) resolved or 2) documented as mitigated. Vulnerability scanning is outlined in detail [here][8].

# Are external penetration tests conducted against Catalyze networks?

Yes, Catalyze performs external penetration tests annually. Additionally, internal penetration testing is performed by the Catalyze Security Team quarterly. The penetration testing policy is outlined [here][9].

# Are there tools in place to detect and prevent denial of service attacks (DOS or DDOS)?

Yes, we leverage perimeter detection of DOS attacks. We automate blocking of IP addresses found to be attempting DOS attacks. Our DOS policy is outlined [here][10].

# Are perimeter firewall used? How are they configured?

To restrict access to the bare minimum required, redundant, dedicated hardware firewalls are set up to deny all requests by default. Ports have to be opened specifically to cater to specific application and database needs. These hardware firewalls are deployed in a Virginia data center. SSH connections and direct serial port access are the only way to access firewalls.


[1]:	https://policy.catalyze.io/#data-integrity-policy
[2]:	mailto:sales@catalyze.io
[3]:	https://policy.catalyze.io/#backup-policy-and-procedures
[4]:	https://policy.catalyze.io/#disaster-recovery-policy
[5]:	%20https://policy.catalyze.io/#risk-management-policy
[6]:	https://policy.catalyze.io/#intrusion-detection-policy
[7]:	http://www.tenable.com/products/nessus-vulnerability-scanner
[8]:	https://policy.catalyze.io/#vulnerability-scanning-policy97
[9]:	https://policy.catalyze.io/#vulnerability-scanning-policy97
[10]:	https://policy.catalyze.io/#intrusion-detection-policy