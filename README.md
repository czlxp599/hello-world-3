### Feature:           Decommission VMs

When a VM is
no longer needed the customer will initiate decommissioning of the VM.

Rules:  The customer must be authorized to decommission VMs

### Scenario:         Customer has selected a VM for
decommissioning

When   the customer submits
request to decommission a VM and the waiting period has elapsed

            Then    a
change record is created

            And      the
VM is removed from Active Directory

            And      the
Chef Client and Chef Node are removed

            And      the
IP address is deleted

            And      the
related tools are updated (monitoring, AD,APIC,QIP, WFA Storage, Chef)

            And      CMDB
is updated

            And      related
processes are updated ((Finance, Event, SACM, Capacity)


### Scenario:         Customer cancels decommissioning request

When waiting period has not elapsed and the customer cancels
a decommissioning request

Then    terminate the decommission request

### Are any of the following items required in the decommissioning process? 

Communication sent to application owner(s) pre-decommission and or post decommission?

Related processes must be updated (Finance, Event, SACM, Capacity)Delete
or deactivate application service accountDelete

NetApp file shareDelete, deactivate, terminate access to file share

Are any pre-requisite activities required such
as changing root passwords, moving users, removing NFS mounts, backing up
recovery information, scrubbing data etc must be performed
