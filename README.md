graph LR
A[Admin Login (Verify Role)] --> B{Yes (Admin)}
B --> C{Open Add Equipment Form}
C --> D{Enter Equipment Details (Name, Description, Model, Serial, etc.)}
D --> E{Submit Details}
E --> F{Validate Details}
F -- Yes --> G{Equipment Added}
F -- No --> D{Fix Errors}
G --> H{Equipment List Updated}
H --> I[End]

B --> J{No (Not Admin)}
J --> K{Display Access Denied Message}
K --> I
 
G --> L{Equipment Status: Available}
L --> M{Status Change Option}
M --> N{Change Status (In Use, Maintenance, Retired)} [Triggered by Admin]
N --> O{Update Status & Equipment List}
O --> P{Send Notification (if Maintenance or Retired)} [Triggered by System]
P -- Yes --> Q{Send email notification to Admins}
P -- No --> I
Q --> I
