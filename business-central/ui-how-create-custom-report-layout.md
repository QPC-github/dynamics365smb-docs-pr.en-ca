---
title: Create and Modify Custom Layouts for Reports and Documents
description: 'Learn how to create customized layouts to personalize the appearance of a report when viewed, printed, or saved.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'customized report, document layout, logo, personalize'
ms.search.form: '9650, 9652'
ms.date: 03/06/2022
ms.author: edupont
---
# <a name="legacy-create-and-modify-custom-report-layouts" />(Legacy) Create and Modify Custom Report Layouts

[!INCLUDE[legacy-custom-layouts](includes/legacy-custom-layouts.md)]

By default, reports have a built-in layout. The report layout can be either an RDLC (report definition language client side) report layout, a Microsoft Word report layout, or both. And while you can't modify built-in layouts, you can create custom layouts. A report can have multiple custom report layouts.

> [!NOTE]  
> In [!INCLUDE[prod_short](includes/prod_short.md)], the term "report" also covers externally-facing documents, such as sales invoices and order confirmations you send to customers as PDF files.

To create a custom layout, either copy an existing custom layout or add a new custom layout. Custom layouts are often based on a built-in layout. When you add a new custom layout, you can choose to add either an RDLC or a Word report layout type, or both. The new custom layout will be based on the built-in layout for the report, if one is available. If there's no built-in layout for the report type, a new blank layout is created. You'll have to modify and design this blank layout from scratch. Learn more about RDLC and Word report layouts, built-in and custom layouts, and more at [Manage Report Layouts](ui-manage-report-layouts.md).  

> [!TIP]
> Use financial reports to get insight into the financial data stored in your chart of accounts. Learn more at [Prepare Financial Reporting with Financial Data and Account Categories](bi-how-work-account-schedule.md).

After you define your custom report layouts, you can select them on the customer card and vendor card pages. The layouts are then used when you create documents for the customer or vendor. Learn more at [Define Document Layouts for Customers and Vendors](ui-define-customer-vendor-document-layouts.md).

You can also use custom report layouts to add content to email messages. Report layouts can save time and help ensure consistency by reusing the same content when you communicate with your customers. To use custom report layouts with email, the file type for the layout must be Word; you cannot use the RDLC file type. Learn more at [Set Up Reusable Email Text and Layouts](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts).

## <a name="create-a-custom-layout" />Create a custom layout

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Layout Selection**, and then choose the related link.

    The **Report Layout Selection** page lists all the reports available in the company specified in the **Company Name** field at the top of the page.
2. In the **Company Name** field, choose the company you want to create the report layout for.
3. Select the row for the report you want to create the layout for, and then choose the **Custom Layouts** action.  

   The **Custom Report Layouts** page appears and lists all the custom layouts available for the selected report.
4. If you want to create a copy of an existing custom layout, select the existing custom layout in the list, then choose the **Copy** action.  

   The copy of the custom layout appears on the **Custom Report Layouts** page and has the words *Copy of* in the **Description** field.
5. If you want to add a new custom layout based on a built-in layout, follow these steps:  
   1. Choose the **New** action. The **Insert Built-in Layout for a Report** page appears with the **ID** and **Name** fields automatically filled in.
   2. Turn on the **Insert Word Layout** toggle to add a custom Word report layout type OR turn on the **Insert RDLC Layout** toggle to add a custom RDLC report layout type.
   4. Choose the **OK** button.  

    The new custom layout now appears on the **Custom Report Layouts** page. If a new layout is based on a built-in layout, then the words **Copy of a Built-in Layout** appear in the **Description** field. If there was no built-in layout for the report, then the new layout has the words **New Layout** in the **Description** field, which means that custom layout is blank.
6. By default, the **Company Name** field is blank and the custom layout is available for reports by all companies. To make the custom layout available to a specific company only, choose **Edit**, then set the **Company Name** field to the company you want.

The custom layout has been created and you can modify it as you like.

> [!TIP]
> You can export the report results to a Microsoft Excel file to view the full dataset, including all columns, but without the layout. The Excel file can help you validate the report returns the expected data or diagnose problems. Learn more at [Analysing Report Data with Excel](report-analyze-excel.md).

## <a name="a-namemodifycustomlayoutamodifying-a-custom-layout" /><a name="ModifyCustomLayout"></a>Modifying a custom layout

To modify a custom report layout, you must first export the report layout as a file to a location on your computer or network. Then, open the exported document and make the changes. When you're finished making the changes, you import the report layout.

### <a name="modify-a-custom-layout" />Modify a custom layout

1. Export a custom layout from the **Custom Report Layouts** page. If that page isn't already open, search for and open the **Report Layout Selection** page, select the report that has the layout you want to modify, then choose the **Custom Layouts** action.  
2. On the **Custom Report Layouts** page, select the layout you want to modify, choose the **Export Layout** action, then choose **Save** or **Save As** to save the report layout document to a location on your computer or network.  
3. Open the report layout document you saved and make changes.

   If you're changing a Word layout, open the layout document in Word. Learn more about editing Word reports at [Work with Word Layouts](ui-how-add-fields-word-report-layout.md)<!--the next section [Making Changes to the Report Layout](ui-how-create-custom-report-layout.md#MakeChangesToLayout)-->.

   RDLC report layouts are more advanced than Word report layouts. Learn more about modifying an RDLC report layout at [Designing RDLC Report Layouts](/dynamics-nav/Designing-RDLC-Report-Layouts).

   Remember to save your changes when you're done.

4. Return to the **Custom Report Layouts** page, select the report layout you exported and modified, then choose the **Import Layout** action.  

5. In the **Import** dialogue box, select **Choose** to find and select the modified report layout document, then choose **Open**.

> [!IMPORTANT]
> Remember to import the report layout document that you modified. Otherwise, the new report layout will not be available.

<!--
## <a name="a-namemakechangestolayouta-create-and-modify-custom-report-layouts" /><a name="MakeChangesToLayout"></a> Create and modify custom report layouts

To make general formatting and layout changes, such as changing text font, adding and modifying a table, or removing a data field, just use the basic editing features of Word like you do with any Word document.

If you're designing a Word report layout from scratch or adding new data fields, then start by adding a table that includes rows and columns that will eventually hold the data fields.

> [!TIP]  
> Show the table gridlines so that you see the boundaries of table cells. Remember to hide the gridlines when you're done editing. To show or hide table gridlines, select the table, and then under **Layout** on the **Table** tab, choose **View Gridlines**.

### <a name="embedding-fonts-in-word-layouts-for-consistency" />Embedding fonts in Word layouts for consistency

To ensure that reports always display and print with the intended fonts, wherever users open or print the reports, you can embed the fonts in the Word document. However, embedding fonts can significantly increase the size of the Word files. Learn more about embedding fonts in Word at [Embed fonts in Word, PowerPoint, or Excel](https://support.office.com/article/Embed-fonts-in-Word-PowerPoint-or-Excel-cb3982aa-ea76-4323-b008-86670f222dbc).

### <a name="a-nameremovefielda-removing-label-and-data-fields-in-word-layouts" /><a name="RemoveField"></a> Removing label and data fields in Word layouts

 Label and data fields of a report are contained in content controls in Word. The following figure illustrates a content control when it's selected in the Word document.  

 ![Content control for field in Word report layout.](media/nav_wordreportlayouts_contentcontrol.png "NAV_WordReportLayouts_ContentControl")  

 The name of the label or data field name displays in the content control. In the example, the field name is CompanyAddr1.  

### <a name="to-remove-a-label-or-data-field" />To remove a label or data field

1. Right-click the field you want to delete, then choose **Remove Content Control**.  

     The content control is removed, but the field name remains as text.  

2. Delete the remaining text as needed.  

### <a name="adding-data-fields" />Adding data fields

Adding data fields from a report dataset is more advanced and requires some knowledge of the report dataset. Learn more about adding fields for data, labels, and images at [Add Fields to a Word Report Layout](ui-how-add-fields-word-report-layout.md).  -->

## <a name="see-related-microsoft-trainingtrainingmoduleschange-documents-dynamics-365-business-centralindex" />See related [Microsoft training](/training/modules/change-documents-dynamics-365-business-central/index)

## <a name="see-also" />See also

[Managing Report Layouts](ui-manage-report-layouts.md)  
[Change the Current Report Layout](ui-how-change-layout-currently-used-report.md)  
[Import and Export a Custom Report or Document Layout](ui-how-import-and-export-report-layout.md)  
[Work with Reports, Batch Jobs, and XMLports](ui-work-report.md)  
[Prepare Financial Reporting with Financial Data and Account Categories](bi-how-work-account-schedule.md)  
[Business Intelligence](bi.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
