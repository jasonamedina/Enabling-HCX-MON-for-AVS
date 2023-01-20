# Enabling HCX MON for AVS

**IMPORTANT: Make sure to collect ping and traceroute results before enabling MON**

1.	Enable HCX MON on the Network Extension.  
 ![image](https://user-images.githubusercontent.com/97964083/213808925-d9172181-2f69-407b-bbd9-146d6e7f2c42.png)


2.	Enable MON on the VM’s that will use the AVS “NSX” default-gateway. Make sure you choose the correct VMs and choose the correct "Target Router Location". This is your NSX T1 router that you are using in AVS. This step will also inject a host route for the VM for ingress AVS traffic destined to the VM.  
 ![image](https://user-images.githubusercontent.com/97964083/213809013-d9b06a66-b2f9-4acc-a84a-ac77515b1d63.png)


3.	Modify the HCX Policy Route. You can find the Policy Route where it says “Advanced”  
    ![image](https://user-images.githubusercontent.com/97964083/213809043-40468070-0cd8-462b-9136-b9a8a47832ef.png)


4.	Remove all IP Policy Redirection rules as shown below and make sure “Redirect to Peer” is set to “Allow”. This will force all your MON-enabled VM’s to use your AVS NSX T1 default-gateway.  
![image](https://user-images.githubusercontent.com/97964083/213809122-7bd3390e-d737-4e4e-9e1d-fab85bf29512.png)

5 . Once all the steps are complete, be sure to test it with Ping and Traceroute. You can compare the ping and traceroute results with the results you collected before enabling MON. You should also be able to test to see if you are now accessing the Internet from within Azure.   

I've attached two links below if you'd like to go into more detail about MON.  
https://docs.vmware.com/en/VMware-HCX/4.3/hcx-user-guide/GUID-73125E78-3428-4B7B-BACD-6332444A5D6B.html  
https://docs.vmware.com/en/VMware-HCX/4.3/hcx-user-guide/GUID-F45B1DB5-C640-4A75-AEC5-45C58B1C9D63.html  
