# Server Side Segment Selection for Streaming (S4Streaming)
In ABR (Adaptive Bit-Rate) streaming, the player controls the quality(bit-rate) selection function of its maximum available bandwidth estimation (most of the time based on the HTTP protocol) and possibly based on its buffer level. The player has one objective that is to maximize the quality of experience perceived by the user while avoiding rebuffering.  However it does not and cannot indeed consider other players that may share the medium and therefore the bandwidth. In addition, bandwidth estimation performed by the player is most of the time based on HTTP (application layer) which does not work properly in some situations like with CMAF low latency.  

Server Side Segment Selection for Streaming (S4S) is a technology that gives the control of the bandwidth/quality(bit-rate) tradeoff to the ISP. The  S4S server selects the quality/bit-rate of the segment to be returned to the player relying on its own available bandwidth estimation  (based on the underlaying transport’s congestion control) and a bit-rate selection strategy possibly driven by a e.g. [business] rules engine though an API.  

S4S provides also means for increasing the cooperation between the player and the cache server for a better user experience. 

S4S has been primarily designed for low latency but can also be used in non-low latency deployment when the maximum video bit-rate must be controlled/imposed for a subset or the entire set of active media sessions. 

This document specifies two modes of operation: one being [almost] totally transparent for the player and the other one being non transparent, requiring the support of a particular (lightweight) protocol . S4S applies to any ABR streaming protocols. However depending on terminal restrictions (i.e. IOS) it may not always possible to implement/deploy the S4S protocol. 
