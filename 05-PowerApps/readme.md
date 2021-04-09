Mango Inc warehouse employees should able to identify available materials along with base unit of measurement in real time for available materials in their base plant from their existing mobile device. 

1. Design a power application that 
2. 

Documentation URL: https://powerapps.microsoft.com/en-us/blog/introducing-the-sap-erp-connector/

Exercise  1:  
Verify access to SAP S/4 appliance and Deploy on-prem data gateway. 
Deploy On-premises data gateway VM and SAP .Net Connector closer to SAP Application servers for low latency data traffic. Ensure that NSG allows flow such as SAP Gateway, Dispatcher and Message server ports
 
Exercise  2:  
In this exercise,  you are going to bring SAP Material Information and material details to the PowerApps by using Flow. 
Part 1: Get Material List
Verify access to PowerApps application layer ( https://make.preview.powerapps.com/ ). You do need  right set of licenses such as “Microsoft 365 E5 Developer, Power Apps Plan 2 Trial and Power Automate Free”
Create SAP Material List flow by calling SAP function module BAPI_MATERIAL_GETLIST by leveraging "Call SAP Function”. 
Use following parameter values such as



 


Next Step to build “Response”
 
In the response, select MATNRLIST" Using the connector in an App" at https://powerapps.microsoft.com/en-us/blog/introducing-the-sap-erp-connector/.  
 
Go to outputs section in step 2, go to MATNRLIST section and copy all the data in that section. Now click on advanced options in step 3(Response) -> Click on use sample payload to generate schema -> Paste the copied data.  
 
 
Part 2:  Get Material Details
 
Create Flow “ Get_SAP_Material  “
    
This flow has 3 steps and uses SAP BAPI named "BAPI_MTERIAL_GET_DETAIL".  
 

 

 

 
 
Follow similar steps from previous exercise. 

Exercise 3:  
 
In this exercise, you are going to create Power Application with Layout feature. 
 
Create Power Application with tablet layout. 
	• Create a screen with appropriate header. 
	
	• 
	
 
 
Select onvisible property in the form and connect to powerautomate flow "Get_SAP_MaterialList" .  For this go to Action -> click on power automate select the flow. 

 
 
Adjust the onvisible property of screen as shown in below screen. Below Screen shot  has different flow name, please ignore it and use correct flow name. Screenshot is given to show the property "OnVisible" and collection object "QueryResults". 
 

 
	• Insert vertical gallery.  
Connect the vertical gallery to collection object "QueryResults" which was pre-loaded while form is being loaded.  
	• 
	• 
	• 
	• Create second collection object to store individual material details upon selection in the gallery. 
Click on select icon on gallery and adjust onselect property to call second flow and store in collection object for example material. User power automate button under menu Action to connect to the flow. Select the flow that get material details from SAP. Below screen shot has flow named powerappsbutton that should be replaced with the one that you created.  
	• Create few labels to show material information. Material has several attributes, insert labels based on number of fields you want to display. 


Select the label and connect it with the corresponding attribute on the collection object as shown in below screen shot.  
	• 
	• 
	• 



Reference documents:
• SAP ERP Connector in power Apps https://powerapps.microsoft.com/en-us/blog/introducing-the-sap-erp-connector/
• Power Apps Canvas Apps: https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/
• Create collection: https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/create-update-collection
• Using Flows in PowerApps: https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/using-logic-flows
![image](https://user-images.githubusercontent.com/45843990/114212701-fa252280-9916-11eb-9713-27cea1f86f8e.png)

