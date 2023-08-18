An Elastic Fabric Adapter (EFA) is a network device that you can attach to your Amazon EC  
instance to accelerate High Performance Computing (HPC) and machine learning applications.  
It enhances the performance of inter-instance communication that is critical for scaling HPC and  
machine learning applications. EFA devices provide all Elastic Network Adapter (ENA) devices

functionalities plus a new OS bypass hardware interface that allows user-space applications to  
communicate directly with the hardware-provided reliable transport functionality.

The OS-bypass capabilities of EFAs are not supported on Windows instances. If you attach an  
EFA to a Windows instance, the instance functions as an Elastic Network Adapter, without the  
added EFA capabilities.