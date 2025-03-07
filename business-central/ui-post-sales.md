---
title: Posting Sales Documents
description: 'Learn about the different posting functions to post sales documents, and how you can update posted documents.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.search.form: '130, 142, 1350'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="posting-sales" />Posting Sales

Under the **Posting** menu in a sales document, you can choose between the following posting functions:

* **Post**
* **Post and New**
* **Post and Send**
* **Preview Posting**
* **Post Batch**
* **Test Report**

> [!NOTE]
> For sales orders, you can also see options related to the prepayments functionality. For more information, see [Invoicing Prepayments](finance-invoice-prepayments.md).

When you have completed all the lines and entered all the information on the sales order, you can post it. This creates a shipment and an invoice.

When a sales order is posted, the customer's account, the general ledger, and the item ledger entries are updated.

For each sales order, a sales entry is created in the **G/L Entry** table. An entry is also created in the customer's account in the **Cust. Ledger Entry** table and a general ledger entry is created in the relevant receivables account. In addition, posting the order may result in a GST/HST entry and a general ledger entry for the discount amount. Whether an entry for the discount is posted depends on the contents of the **Discount Posting** field on the **Sales & Receivables Setup** page.

For each sales order line, an item ledger entry will be created in the **Item Ledger Entry** table (if the sales lines contain item numbers) or a general ledger entry will be created in the **G/L Entry** table (if the sales lines contain a general ledger account). In addition to this, sales orders are always recorded in the **Sales Shipment Header** and **Sales Invoice Header** tables.

[!INCLUDE [order-ship-invoice](includes/order-ship-invoice.md)]

You can either post, or post and send. If you choose to post and send, a PDF file is generated that you can then send. You can also choose the **Post Batch** function, which lets you post several orders at the same time. For more information, see [Post Multiple Documents at the Same Time](ui-batch-posting.md).

## <a name="viewing-ledger-entries" />Viewing Ledger Entries

When the posting is completed, the posted sales lines are removed from the order. A message tells you when the posting is completed. After this, you will be able to see the posted entries in the various pages that contain posted entries, such as the **Cust. Ledger Entries**, **G/L Entries**, **Item Ledger Entries**, **Posted Sales Shipments**, and **Posted Sales Invoices** pages.  

In most cases, you can open ledger entries from the affected card or document. For example, on the **Customer Card** page, choose the **Ledger Entries** action.

## <a name="editing-ledger-entries" />Editing Ledger Entries

You can edit certain fields on posted purchase documents, such as the **Package Tracking No.** field. For more information, see [Edit Posted Documents](across-edit-posted-document.md). For more critical fields that affect the auditing trail, you must reverse or undo posting. For more information, see [Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md).

## <a name="see-related-microsoft-trainingtrainingmodulesship-invoice-items-dynamics-365-business-centralindex" />See related [Microsoft training](/training/modules/ship-invoice-items-dynamics-365-business-central/index)

## <a name="see-also" />See Also

[Sales](sales-manage-sales.md)  
[Post Multiple Documents at the Same Time](ui-batch-posting.md)  
[Edit Posted Documents](across-edit-posted-document.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Correct or Cancel Unpaid Sales Invoices](sales-how-correct-cancel-sales-invoice.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]  
