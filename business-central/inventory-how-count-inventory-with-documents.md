---
title: Count and Adjust Inventory
description: Describes how to count physical inventory and use inventory documents to adjust on-hand inventory.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'adjustment, status, negative, positive, increase, decrease, inventory'
ms.search.forms: '5895, 6561, 6562, 6563, 6564, 6565, 6566, 5892, 5891, 5879, 5880, 5893, 5897, 5882, 5881, 5899, 5875, 5878, 5877, 5876, 5896, 6567, 6568, 6569, 6570, 6571, 6572, 5883, 5886, 884, 5898, 5885, 5890, 5888, 5889, 5887, 5894, 6774, 6775, 6776, 6780, 6781, 6782, 6783'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="count-and-adjust-inventory-using-documents" />Count and Adjust Inventory Using Documents

You can take a physical inventory of your items by using physical inventory order and physical inventory recording documents. The **Physical Inventory Order** page is used to organize the complete inventory counting project, for example one per location. The **Physical Inventory Recording** page is used to communicate and capture the actual count of items. You can create multiple recordings for one order, for example to distribute groups of items to different employees.

The **Physical Inventory Recording** report can be printed from each recording and contains empty quantity fields for entering the counted inventory. When a user is done counting, and the quantities are entered on the **Physical Inventory Recording** page, you choose the **Finish** action. This transfers the quantities to the related lines on the **Physical Inventory Order** page. Functionality ensures that no item count can be recorded twice.  

> [!NOTE]
> Using documents to perform a physical inventory provides more control and supports distributing the counting to multiple employees. You can also perform the task by using journals, such as the **Phys. Inventory Journals** and **Whse. Phys. Inventory Journals** pages. For more information, see [Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md). This article describes how to perform a physical inventory using documents.
>
> If you are using zones, then you cannot use physical inventory orders. Instead, use the **Whse. Phys. Inventory Journal** page to count your warehouse entries before synchronizing them with item ledger entries.

Counting inventory by using documents consist of the following overall steps:

1. Create a physical inventory order with expected item quantities prefilled.
2. Generate one or more physical inventory recordings from the order.
3. Enter the counted item quantities on the recordings, as captured on print-outs, for example, and set it to **Finished**.
4. Complete and post the physical inventory order.

## <a name="to-create-a-physical-inventory-order" />To create a physical inventory order

A physical inventory order is a complete document that consists of a physical inventory order header and some physical inventory order lines. The information on a physical inventory header describes how to take the physical inventory. The physical inventory order lines contain the information about the items and their locations.

To create the physical inventory order lines, you typically use the **Calculate Lines** function to reflect the current inventory as lines on the order. Alternatively, you can use the **Copy from Document** function to fill the lines with the content of another open or posted physical inventory order. The following procedure only describes how to use the **Calculate Lines** function.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Physical Inventory Orders**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the required fields on the **General** FastTab. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Choose the **Calculate Lines** action.
5. Select options as necessary.
6. Set filters, for example, to only include a subset of items to be counted with the first recording.

    > [!TIP]
    > To plan for multiple employees to count the inventory, it is advisable to set different filters each time you use the **Calculate Lines** action to only fill the order with the subset of inventory items that one user will be recording. Then as you generate multiple physical inventory recordings for multiple employees, you minimize the risk of counting items twice. For more information, see the [To create a physical inventory recording](#to-create-a-physical-inventory-recording) section.

7. Choose the **OK** button.

A line for each item that exists on the chosen location and per the set filters and options is inserted on the order. For items that are set up for item tracking, the **Use Item Tracking** check box is selected, and information about the expected quantity of serial and lot numbers is available by choosing the **Lines** action and then **Item Tracking Lines**. For more information, see the [Handling Item Tracking when Counting Inventory](#handling-item-tracking-when-counting-inventory) section.

You can now proceed to create one or more recordings, which are instructions to the employees who perform the actual counting.  

## <a name="to-create-a-physical-inventory-recording" />To create a physical inventory recording

For each physical inventory order, you can create one or more physical inventory recording documents on which employees enter the counted quantities, either manually or through an integrated scanning device.

By default, a recording is created for all the lines on the related physical inventory order. To avoid that two employees count the same items in case of distributed counting, it is advisable to gradually fill the physical inventory order by setting filters on the **Calculate Lines** batch job (see the "To create a physical inventory order" section) and then create the physical inventory recording while selecting the **Only Lines Not in Recordings** check box. This settings makes sure that each new recording that you create only contains different items than the ones on other recordings.

In case of manual counting, you can print a list, the **Phys. Invt. Recording** report, which has an empty column to write the counted quantities in. When counting is completed, you enter the recorded quantities on the related lines on the **Phys. Inventory Recording** page. Lastly, you transfer the recorded quantities to the related physical inventory order by setting the status to **Finished**.

1. On a **Physical Inventory Order** page that contains lines for the items to be counted in one recording, choose the **Make New Recording** action.
2. Select options and set filters as necessary.
3. Choose the **OK** button.

    A physical inventory recording document is created.

4. For every set of items to be counted, load them on the related physical inventory order and repeat steps 1 through 3 with the **Only Lines Not in Recordings** check box selected.

5. Choose the **Recordings** action to open the **Phys. Inventory Recording List** page.
6. Open the relevant recording.
7. On the **General** FastTab, fill in the fields as necessary.
8. For items that use item tracking, create an additional line for each lot number or serial number code by choosing the **Functions** action, and then the **Copy Line** action. For more information, see the [Handling Item Tracking when Counting Inventory](#handling-item-tracking-when-counting-inventory) section.  
9. Choose the **Print** action to prepare the physical document that employees will use to write down the counted quantities.

## <a name="to-finish-a-physical-inventory-recording" />To finish a physical inventory recording

When employees have counted the inventory quantities, you must prepare to record them in the system.

1. From the **Phys. Inventory Recording List** page, select the physical inventory recording that you want to finish, and then choose the **Edit** action.
2. On the **Lines** FastTab, fill the actual counted quantity in the **Quantity** field for each line.
3. For items with serial or lot numbers (the **Use Item Tracking** check box is selected), enter the counted quantities on the dedicated lines for the item's serial and lot numbers respectively question. For more information, see the [Handling Item Tracking when Counting Inventory](#handling-item-tracking-when-counting-inventory) section.
4. Select the **Recorded** check box on each line.
5. When you have entered all data for a physical inventory recording, choose the **Finish** action. Note that all lines must have the **Recorded** checkbox selected.

    > [!NOTE]
    > When you finish a physical inventory recording, each line is transferred to the line on the related physical inventory order that matches it exactly. To match, the values in the **Item No.**, **Variant Code**, **Location Code**, and **Bin Code** fields must be the same on the recording and the order lines.<br /><br />
    > If no matching physical inventory order line exists, and if the **Allow Recording Without Order** checkbox is selected, then a new line is inserted automatically and the **Recorded Without Order** checkbox on the related physical inventory order line is selected. Otherwise, an error message is displayed and the process is cancelled.<br /><br />
    > If more than one physical inventory recording lines match a physical inventory order line, then a message is displayed and the process is cancelled. If, for some reason, two identical physical inventory lines end up on the physical inventory order, you can use a function to resolve it. For more information, see the [To find duplicate physical inventory order lines](#to-find-duplicate-physical-inventory-order-lines) section.

## <a name="to-complete-a-physical-inventory-order" />To complete a physical inventory order

When you have finished a physical inventory recording, the **Qty. Recorder (Base)** field on the related physical inventory order is updated with the counted (recorded) values, and the **On Recording** check box is selected. If a counted value is different from the expected, then that difference is shown in the **Pos Qty. (Base)** and **Neg Qty. (Base)** field respectively.

To see expected quantities and any recorded differences for items with item tracking, choose the **Lines** action, and then choose the **Item Tracking Lines** action to select various views for serial and lot numbers involved in the physical inventory count.

You can also choose the **Phys. Inventory Order Diff.** action to view any differences between the expected quantity and the counted quantity.

### <a name="to-find-duplicate-physical-inventory-order-lines" />To find duplicate physical inventory order lines

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Physical Inventory Orders**, and then choose the related link.
2. Open the physical inventory order that you want to view duplicate lines for.
3. Choose the **Show Duplicate Lines** action.

Duplicate physical inventory order lines display so that you can delete them and keep only one line with a unique set of values in the **Item No.**, **Variant Code**, **Location Code**, and **Bin Code** fields.

### <a name="to-post-a-physical-inventory-order" />To post a physical inventory order

After completing a physical inventory order and changing its status to **Finished**, you can post it. You can only set the status of a physical inventory order to **Finished** if the following are true:

- All related physical inventory recordings have a status of **Finished**.
- Each physical inventory order line has been counted by at least one inventory recording line.
- The **In Recording Lines** and the **Qty. Exp. Calculated** check boxes have been selected for all of the physical inventory order lines.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Physical Inventory Orders**, and then choose the related link.
2. Select the physical inventory order that you want to complete, and then choose the **Edit** action.

    On the **Physical Inventory Order** page, you view the quantity recorded in the **Qty. Recorded (Base)** field.
3. Choose the **Finish** action.

    The value in the **Status** field is **Finished**, and you can now only change the order by first choosing the **Reopen** action.
4. To post the order, choose the **Post** action, and then choose the **OK** button.

    The item ledger entries are updated along with any related item tracking entries.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

### <a name="to-view-posted-physical-inventory-orders" />To view posted physical inventory orders

After posting, the physical inventory order will be deleted and you can view and evaluate the document as a posted physical inventory order including its physical inventory recordings and any comments made.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Phys. Invt. Orders**, and then choose the related link.
2. On the **Posted Phys. Invt. Orders** page, select the posted inventory order that you want to view, and then choose the **View** action.
3. To view a list of related physical inventory recordings, choose the **Recordings** action.

## <a name="handling-item-tracking-when-counting-inventory" />Handling Item Tracking when Counting Inventory

Item tracking pertains to the serial or lot numbers that are assigned to items. When counting an item that is stored in inventory as, for example, 10 different lot numbers, the employee must be able to record which and how many units of each lot number are on inventory. For more information about item tracking functionality, see [Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md).

The **Use Item Tracking** check box on physical inventory order lines is automatically selected if an item tracking code is set up for the item, but you can also select or deselect it manually.

### <a name="example---prepare-a-physical-inventory-recording-for-an-item-tracked-item" />Example - Prepare a Physical Inventory Recording for an Item-Tracked Item

Consider a physical inventory for Item A, which is stored in inventory as ten different serial numbers.
1. On the recording line for the item, select the **Use Item Tracking** check box.
2. Choose the **Serial No.** field, select the first serial number that exists in inventory for the item, and then choose the **OK** button.

    Copy the line for the first item-tracked item to insert additional lines corresponding to the number of serial numbers that are stored in inventory.

3. Choose the **Functions** action, and then the **Copy Line** action.
4. On the **Copy Phys. Invt. Rec. Line** page, enter 9 in the **No. of Copies** field, and then choose the **OK** button.
5. On the first of the copy lines, select the **Serial No.** field and select the next serial number for the item.
6. Repeat step 5 for the remaining eight serial numbers, taking care to not select the same one twice.
7. Choose the **Print** action to prepare the print-out that employees will use to write down the counted items and serial/lot numbers.

Notice that the **Phys. Invt. Recording** report contains ten lines for Item A, one for each serial number.

### <a name="example---record-and-post-counted-lot-number-differences" />Example - Record and Post Counted Lot Number Differences

A lot-tracked item is stored in inventory with the "LOT" number series.

**Expected Inventory**:

|Lot No.|Quantity|
|-|-|
|LOT1001|80|
|LOT1003|30|
|LOT1006|10|
|Total|120|

**Recorded Quantities**:

|Lot No.|Quantity|
|-|-|
|LOT1001|80|
|LOT0002|12|
|LOT1003|20|
|LOT1006|10|
|Total|112|

**Quantities to Post**:

|Lot No.|Expected Quantity|Recorded Quantity|Quantity to Post|
|-|-|-|-|
|LOT1001|80|80|0|
|LOT1002|0|12|+12|
|LOT1003|30|20|-10|
|LOT1006|10|0|-10|
|Total|120|112|-8|

On the **Physical Inventory Order** page, the **Neg. Qty. (Base)** field will contain *8*. For the order line in question, the **Phys. Invt. Item Track. List** page will contain the positive or negative quantities for the individual lot numbers.

## <a name="inventory-documents" />Inventory Documents

The following types of documents are useful for managing your warehouse:

* Use **Inventory receipts** to register positive adjustments of items based on the quality, quantity, and cost.
* Use **Inventory shipments** to write off missing or damaged goods.

You can print these documents at any stage, release and reopen them, and assign common values, including dimensions, in the header. If you want to reprint the documents after they have been posted, you can do that on the **Posted Inventory Receipt** and **Posted Inventory Shipment** pages.

> [!NOTE]
> Before you can use these documents you must specify a number series to create their identifiers. For more information, see the next section.

### <a name="to-set-up-numbering-for-inventory-documents" />To set up numbering for inventory documents

The following procedure shows how to set up numbering for inventory documents.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Setup**, and then choose the related link.
2. On the **Numbering** FastTab, specify in the following fields the series of numbers for documents:

   * **Inventory Receipt Nos.**  
   * **Posted Inventory Receipt Nos.**  
   * **Inventory Shipment Nos.**  
   * **Posted Inventory Shipment Nos.**  

### <a name="to-create-and-post-an-inventory-document" />To create and post an inventory document

The following procedure shows how to create, print, and post an inventory receipt. The steps are similar for inventory shipments.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Receipts**, and then choose the related link.  
2. In the header of the **Inventory Receipt** page, choose the location in the **Location Code** field, and then fill in the remaining fields as necessary.
3. On the **Lines** FastTab, in the **Item** field, choose the inventory item. In the **Quantity** field, enter the number of items to add. 
4. To print an **Inventory Receipt** report from the **Inventory Receipt** page, choose the **Print** action.

The following functions are available on the **Inventory Receipt** page:

* Choose the **Release** or **Reopen** actions to set the status for the next processing stage  
* Choose the **Post** action to post the inventory receipt, or choose **Post and Print** to post the receipt and print the test report  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## <a name="printing-inventory-documents" />Printing Inventory Documents

You can specify the reports that must be printed at different stages by choosing one of the following options in **Usage** field the **Report Selection - Inventory** page:

* Inventory Receipt
* Inventory Shipment
* Posted Inventory Receipt
* Posted Inventory Shipment

> [!NOTE]
> The available reports may vary based on your country's localization. The base application doesn't include any layouts.

## <a name="see-related-microsoft-trainingtrainingmodulesadjust-inventory" />See related [Microsoft training](/training/modules/adjust-inventory/)

## <a name="see-also" />See also

[Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md)  
[Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md)  
[Inventory](inventory-manage-inventory.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
