---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-01"

keywords: Connect, finalize, questionnaire, Special Network Services, billing, fees, VRF, BGP, ticket, ASN

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link Connect Questionnaire
{: #ibm-cloud-direct-link-connect-questionnaire}

Thank you for opening a request for {{site.data.keyword.cloud}} Direct Link Connect.  To finalize your request, we’d like to gather some additional information from you.  You can speak with an engineer at any time during the questionnaire process.  Once you've completed the questionnaire, it will be reviewed by our Cloud Design Engineering team and escalated to Special Network Services for implementation.

## Do you acknowledge and agree to the following?
{: #connect-do-you-agree}

1. Each Direct Link connection requires a unique order.  If you require multiple connections, please open separate Direct Link orders for each connection.

2. The fees for your Direct Link Connect service cover the cost of service termination on the IBM Cloud infrastructure.

 * Infrastructure Services are billed in advance and begin upon acceptance of your order; however due to the nature of IBM Cloud Direct Link, the Direct Link service billing will begin upon the initiation of a Border Gateway Protocol (BGP) session with IBM Cloud, or 30 days after the service key is provided to the client.

 * Billing stops after:
   * A customer requests a circuit to be deleted, **and**
   * The Connect Provider or Network Service Provider has de-provisioned the circuit.
  * For more information see **Section 5 - Charges** in Cloud Services Agreement at the following link: [https://www.ibm.com/support/customer/zz/en/selectcountrylang.html](https://www.ibm.com/support/customer/zz/en/selectcountrylang.html). For example, customers in the United States would view [this Cloud Services contract document](https://www.ibm.com/support/customer/csol/contractexplorer/cloud/csa/us-en).
  * Alternatively, billing can stop for a customer if a customer is notified that their Direct Link service will be turned off and no longer work.

3. By ordering the Direct Link service, you will be responsible for any fees associated with reaching the Point of Presence (PoP) from your remote network and any cross-connects needed within the PoP facility to reach your exchange provider. You (or your provider) will also be responsible for buying the virtual circuit to IBM Cloud. If your provider requires that a router or other device physically sit in the PoP, you will be responsible for the costs associated with collocating that equipment as well.  Please confirm that your Network or PoP provider can reach the Direct Link Connect and can price out the associated costs.

4. IBM Cloud will not collocate any customer equipment in our network POPs.  You will need to work with your provider to determine whether or not you need to collocate any equipment into the same facility where the IBM Cloud PoP exists.

5. The Direct Link Connect service is provided in such a way where your link and the IBM Cloud router it can terminate into are both single points of failure (SPOF). If you want to achieve redundancy through the Direct Link Connect service, you will need to terminate links into two separate IBM Cloud network PoPs or order two connections into a Direct Link Connect location with a secondary router.

6. The IBM Cloud services network will not be accessible from your remote networks directly. If this changes in the future, you will be notified.

7. IBM Cloud will not allow customers to back haul traffic between their remote sites across the IBM Cloud backbone. The Direct Link Connect product is meant for your remote networks to be able to privately communicate with your IBM Cloud infrastructure.

8. After you’ve confirmed your circuit has reached the Direct Link Connect PoP, you will need to place an order with your Connect provider and supply all relevant information to the cloud exchange provider and IBM Cloud. For Equinix providers, typical deployment time can take hours. The typical deployment time for the IBM Cloud Direct Link Connect offering takes 5-10 days to complete.

9. IBM Cloud Direct Link Connect requires utilizing a VRF (Virtual Routing and Forwarding) instance on the IBM Cloud Network side.  This allows the customer to define their own remote IP addresses for use in their remote network; however, you must be aware that if you’re able to utilize the 10.x.x.x network, you still cannot overlap with your hosts within IBM Cloud nor with the IBM Cloud services network (10.0.0.0/14, 10.198.0.0/15, and 10.200.0.0/14). Transition of your account to a VRF requires a brief private network outage as each VLAN is migrated into the new configuration. The Special Network Services team will work with you to define a window for this activity. The Special Network Services team is normally available Monday through Friday, 8-5 CST ( US Central Standard time). Any activation activity outside this window will need to be requested via ticket and approved in advance if engineers are available.

10. VRF is not compatible with IBM Cloud SSL, PPTP, and IPSEC VPN services.  An alternative is to use the direct link itself for management of your servers or run your own VPN solution (such as a Vyatta) that can be configured with different types of VPN.  After migrating to a VRF, SSL VPN typically works when a VPN connection is made to the same DC location as the compute that is being accessed, but does not allow access globally.

11. IBM Cloud Direct Link Connect requires BGP in order to implement routes to a customer's remote network. When your Direct Link service has been deployed, IBM Cloud will advertise all of the private subnets assigned to your account. IBM Cloud, and will not implement custom filters, AS-Path prepend and custom local-preference to advertisements to the Customer's remote BGP peer. IBM Cloud will not implement filters on the advertisements received to IBM Cloud. Customers will need to properly manage the advertisements to/from IBM Cloud from the customer's edge router. 

## Other questions
{: #connect-other-questions}

* **Do you acknowledge and accept the pricing of _YOUR LOCATION_ for the IBM Cloud Direct Link Connect connection?**

* **IBM Cloud will assign a private ASN to you for purposes of configuring BGP to advertise your remote networks to your IBM Cloud private network.  Is this acceptable or would you prefer to utilize your own public ASN?**

* **Do you require BGP MultiPath with ECMP to be configured for setting up a redundant connection to IBM Cloud?** 

    _If yes, please include the ticket ID for the other connection. Ticket Number ____________  (note that ECMP can only be provisioned on two sessions on the same IBM Cloud XCR.  If ECMP is your desire, know that both Direct Links must land on the same router.)_

* **Do you require Local or Global Routing Access?**

    _Customers selecting local routing will only be able to pass traffic between the data centers being serviced from the PoP where the Direct Link was ordered.  Customers wishing to pass traffic outside of the PoP where the Direct Link was ordered will need to add on the global routing option._

* **Do you agree to the fee for Global Routing including the _YOUR LOCATION_ monthly fee ?**

    _Local routing includes access to all of the Data Centers connected directly to the PoP and provides unlimited ingress/egress traffic.  Global routing expands access to include all IBM Cloud’s data centers globally.  
