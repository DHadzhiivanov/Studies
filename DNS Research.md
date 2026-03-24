
# The Fundamentals

The DNS naming system is organized as a tree structure comprised of multiple levels.

Each node in the *tree* is given a label which defines its **Domain** of **Authority**. The topmost node is the **Root Domain**; it delegates to **Domains** at the next level which are known as **Top-Level Domains (TLDs)**. They in turn delegate to **Second-Level Domains(SLDs)**, and so on. The TLDs include a special group of TLDs called the **Country Code Top-Level Domains (ccTLDs)**, in which every country is assigned a unique two-character country code from ISO 3166 as its domain.

DNS simply is a recursive query system that goes from top-down through each authoritative domain to answer a QUESTION query from the client returning a complete ANSWER (the fully qualified domain name FQDN). The cache resolver can skip the root node if its already cached but this is done only for performance purposes.

![[DNSQueries.svg]]

