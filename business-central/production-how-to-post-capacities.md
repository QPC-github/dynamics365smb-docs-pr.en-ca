---
title: Post Capacities
description: Post consumed capacities that are not assigned to the production order in the capacity journal and view posted capacities on the capacity ledger entries page.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '5832, 99000802, 99000820'
ms.date: 03/08/2023
ms.author: edupont
---
# <a name="post-capacities" />Post Capacities

In the capacity journal, you post consumed capacities that are not assigned to the production order. For example, maintenance work must be assigned to capacity, but not to a production order.  

## <a name="to-post-capacities" />To post capacities

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Capacity Journals**, and then choose the related link.  
2. Fill in the **Posting Date** and **Document No.** fields.  
3. In the **Type** field, enter the type of the capacity, either **Machine centre** or **Work centre**, that you are posting.  
4. In the **No.** field, enter the number of the machine centre or work centre.  
5. Enter the relevant data in the other fields, such as **Starting Time**, **Ending Time**, **Quantity**, and **Scrap**.  
6. Choose the **Post** action to post the capacities.  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## <a name="to-view-work-center-ledger-entries" />To view work centre ledger entries

In the **Work Centre Card** and **Machine Centre Card** pages, you can view the posted capacities as a result of finished production orders.    
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Work Centres**, and then choose the related link.  
2. Open the relevant **Work Centre** card from the list, and then choose the **Capacity Ledger Entries** action.  

    The **Capacity Ledger Entries** page displays the posted entries from the work centre in the order they were posted.   

## <a name="see-also" />See Also

[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
