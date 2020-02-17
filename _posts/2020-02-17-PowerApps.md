---
title: "PowerApps"
---
## Creating one-to-many relationships in Sharepoint

Example used: Receipt

Receipt information will include:
- Receipt number
- Company/person being issued to
- Other details common in every receipt

Receipt details will include:
- Item name
- Item cost
- Item quantity

The number of receipt details differ with each new receipt.

### Steps:

1. Create 2 tables: Receipts, ReceiptDetails.
2. Create fields needed for each.
3. Create a field in ReceiptDetails called ReceiptID. This will act as your "foreign key".
4. Create a screen for receipt information.
5. Create a new form and link to the Receipts data source.

// Steps to include:
Create collection, set values to blank.

6. Create a screen for receipt details.
7. Create a new form and link to the ReceiptDetails data source.

// Steps to include:
Collect datacard text values into previous collection

8. Under "Item" enter Defaults(ReceiptDetails).

When you call ResetForm, it will give you an empty record to enter data, instead of "No items to display" 
9. On the Save button for this screen, submit the first form.

When patching the ReceiptDetails record, set ReceiptID as Form1.LastSubmit.ID.
   

The idea for this followed Shane Young's video series: https://www.youtube.com/watch?v=xgznk4XlPCo
