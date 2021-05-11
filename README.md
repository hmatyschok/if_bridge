if_bridge(4) - extension for inspecting PPPoE frames by pfil(9)
---------------------------------------------------------------

<pre><code> 
 This capability will be en- / disabled by setting
 
   net.link.bridge.pfil_pppoe
   
 OID on by sysctl(3) accessible MIB. Only IPv[46] datagramms 
 are inspected transparently by utilizing in conjunction with 
 pfil(9) KPI implemented Inspection Access Point [IAP]
 
   static int 	bridge_pfil(struct mbuf **, struct ifnet *, 
	struct ifnet *, int);

 where additionally fragmentation by
 
   static int	bridge_fragment(struct ifnet *, struct mbuf **, 
	struct ether_header *, int, struct llc *);
   
 and handoff by dummynet(4) proccessed PPPoE frames 
 
   static void	bridge_dummynet(struct mbuf *, struct ifnet *);
   
 is possible.
</code></pre>

