Contacts Manager — Human Error Simulation 

What I Built 

A web-based contact management application that simulates human error failures. Users can add, view, and delete contacts. When "Human Error Simulation" is enabled, deletions bypass safety confirmations, causing unintended data loss. 

How to Run 

Click the link attached or click this link 

https://ayesha-saeed-0.github.io/HumanError_Example/ 

How to Trigger the Failure 

Add several test contacts (name + phone number) 

Check the box: "Enable Human Error Simulation" 

Click "Delete" on any contact OR click "Delete All Contacts" 

The red error banner appears: "⚠️ Human error simulated: contacts deleted without confirmation." 

Check the logs to see the failure recorded 

Expected Log Example 

Single Contact Deletion with Error: 

{ 
 "timestamp": "2025-11-19T14:32:45.123Z", 
 "action": "delete_single_contact", 
 "removed": { 
   "name": "Alice", 
   "number": "555-1234" 
 }, 
 "totalContacts": 2, 
 "error": "HUMAN_ERROR" 
} 
 

Bulk Deletion with Error: 

{ 
 "timestamp": "2025-11-19T14:33:12.456Z", 
 "actor": "user", 
 "action": "delete_all_contacts", 
 "affectedCount": 5, 
 "totalContacts": 0, 
 "error": "HUMAN_ERROR" 
} 
 

Failure Type 

Human Error — Users accidentally delete contacts without confirmation when the safety toggle is enabled, demonstrating how missed confirmations lead to permanent data loss. 

 
