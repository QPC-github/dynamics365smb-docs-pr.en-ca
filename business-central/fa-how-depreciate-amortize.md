---
title: Depreciate or Amortize FA
description: 'You must define how you will write-down, depreciate, or amortize each of your fixed assets, such as machinery and equipment, over their depreciable life.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: write down
ms.search.form: '5610, 5611, 5629, 5633, 5659, 5660, 5663, 5619, 5666'
ms.date: 06/15/2021
ms.author: edupont
---
# <a name="depreciate-or-amortize-fixed-assets" />Depreciate or Amortize Fixed Assets

Depreciation is used to allocate the cost of fixed assets, such as machinery and equipment, over their depreciable life. For each fixed asset, you must define how it will be depreciated.  

 There are two ways to post depreciation:  

* Automatically, by running the **Calculate Depreciation** batch job.  
* Manually, by using the fixed asset G/L journal.  

[!INCLUDE[prod_short](includes/prod_short.md)] can calculate daily depreciation, which allows you to calculate depreciation for any period. You can therefore analyse current operating results on, for example, a monthly, quarterly, or annual basis. The calculation uses a standard year of 360 days and a standard month of 30 days. For more information, see [Depreciation Methods](fa-depreciation-methods.md).  

If several departments use a fixed asset, periodic depreciation can be automatically allocated to these departments according to a user-defined allocation table.  

You can cancel incorrect depreciation entries by using the **Cancel FA Ledger Entries** batch job. Afterward, you can post the correct amount by running the **Calculate Depreciation** batch job again. The errors you correct are posted as fixed asset error ledger entries.  

Indexation is used to adjust values for general price-level changes. You can use the **Index Fixed Assets** batch job to recalculate the depreciation amounts.  

## <a name="to-calculate-depreciation-automatically" />To calculate depreciation automatically

Once a month, or whenever you choose, you can run the **Calculate Depreciation** batch job. The batch job ignores fixed assets that have been sold, are blocked or inactive, or use the manual depreciation method.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Calculate Depreciation**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Choose the **OK** button.  

    The batch job calculates the depreciation and creates lines in the fixed asset G/L journal.

4. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA G/L Journals**, and then choose the related link.  

    On the **Fixed Asset G/L Journal** page, in the **No. of Depreciation Days** field, you can see how many days of depreciation have been calculated.  
5. Choose the **Post** action.  

> [!NOTE]
> Known limitation: If you set the **Use Force No. of Days** field to Yes, and the **Force No. of Days** field is set to a value where **Posting Date** minus **Number of Days** results in a date in the previous calendar year, the system will not let you post the depreciation.
> You can avoid it by reducing the **Force No. of Days** field to no more than than the calculated days until posting date using 30days/month OR set the flag **Fiscal Year 365 Days** in the Depreciation Book.
> We recommend the first option as you may not want to change the use of 30days/months for depreciation. For more information, see [Fiscal Year 365 Days Field Depreciation](fa-how-setup-depreciation.md#fiscal-year-365-days-field-depreciation).


## <a name="to-post-depreciation-manually-from-the-fixed-asset-gl-journal" />To post depreciation manually from the fixed asset G/L journal

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Asset G/L Journal**, and then choose the related link.  
2. Create an initial journal line and fill in the fields as necessary.  
3. In the **FA Posting Type** field, select **Depreciation**.  
4. Choose the **Insert FA Bal. Account** action. A second journal line is created for the balancing account that is set up for depreciation posting. For more information, see [To set up fixed asset posting groups](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).
5. Choose the **Post** action to post the journal.  

The **Book Value** field on the **Fixed Asset Card** page is updated accordingly.

If you have set up fixed asset allocation keys to allocate amounts to different departments or projects, the amounts are allocated during posting. For more information, see [Set Up General Fixed Assets Information](fa-how-setup-general.md).  

## <a name="to-manage-the-ending-book-value" />To manage the ending book value

In the **Ending Book Value** field on the **FA Depreciation Books** page, you can specify the book value that you want your fixed asset to have in the current depreciation book after it has been fully depreciated. You can do this manually or you can fill in the **Default Ending Book Value** field on the related **Depreciation Book** page, which will then be used to automatically fill the field.

> [!NOTE]
> If the last depreciation means that the **Book Value** field on the **Fixed Asset Card** page is zero, the last depreciation is automatically reduced by this amount.<br /><br />
> If the value in the **Book Value** field is greater than zero after the last depreciation,  for example because of a rounding problem or because a salvage value exists, the value in the **Ending Book Value** field on the **FA Depreciation Books** page is ignored. For more information, see [To post the salvage value together with the acquisition cost](fa-how-acquire.md#to-post-the-salvage-value-together-with-the-acquisition-cost).

## <a name="to-calculate-allocations-in-the-fixed-asset-gl-journal" />To calculate allocations in the fixed asset G/L journal

If a fixed asset is used by several departments, periodic depreciation can be automatically allocated to these departments according to a user-defined allocation table.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Asset G/L Journal**, and then choose the related link.  
2. Create an initial line and fill in the fields as necessary.
3. In the **FA Posting Type** field, select **Allocation**.  
4. Choose the **Insert FA Bal. Account** action. A second journal line is created for the balancing account that is set up for allocation posting.  
5. Choose the **Post** action to post the journal.  

## <a name="use-duplication-lists-to-prepare-to-post-to-multiple-depreciation-books" />Use duplication lists to prepare to post to multiple depreciation books

When you fill in journal lines to post to a depreciation book, you can duplicate the lines in a separate journal so you can post to a different depreciation book. For more information, see To [post entries to different depreciation books](fa-how-depreciate-amortize.md#to-post-entries-to-different-depreciation-books).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Depreciation Books**, and then choose the related link.  
2. Open the depreciation book, and then select the **Part of Duplication List** check box.  

> [!IMPORTANT]  
>   If you have selected the **Use Duplication List** field, do not use number series on the journal. The reason is that the number series for the fixed asset G/L journal does not the number series for the fixed asset journal.  

## <a name="to-post-entries-to-different-depreciation-books" />To post entries to different depreciation books

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Asset G/L Journal**, and then choose the related link.  
2. In the journal that you want to post depreciation with, select the **Use Duplication List** check box.  
3. Fill in the remaining fields as necessary.  
4. Choose the **Post** action.  
5. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Journals**, and then choose the related link.  

    > [!NOTE]  
    >   The **Fixed Asset Journal** page contains new lines for different depreciation books according to the duplication list.  
6. Review or edit the lines, and then choose the **Post** action.  

    > [!NOTE]  
    >   Another way to duplicate an entry in a separate book is to enter a depreciation book code in the **Duplicate in Depreciation Book** field when you fill in a journal line.  

You can copy entries from one depreciation book to another by using the **Copy Depreciation Book** batch job. The batch job creates journal lines in the journal batch that you have specified on the **FA Journal Setup** page for the depreciation book that you want to copy to. For more information, see the following procedure.  

## <a name="to-copy-fixed-asset-ledger-entries-between-depreciation-books" />To copy fixed asset ledger entries between depreciation books

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Depreciation Books**, and then choose the related link.  
2. Open the relevant depreciation book card, and then choose the **Copy Depreciation Book** action.  
3. On the **Copy Depreciation Book** page, fill in the fields as necessary.  
4. Choose the **OK** button.  

The copied lines are created in either the fixed asset G/L journal or the fixed asset journal, depending on whether the depreciation book that you are copying has integration to the general ledger.  

## <a name="see-related-microsoft-trainingtrainingmodulescalculate-post-depreciations" />See related [Microsoft training](/training/modules/calculate-post-depreciations/)

## <a name="see-also" />See also

[Fixed Assets](fa-manage.md)  
[Setting Up Fixed Assets](fa-setup.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
