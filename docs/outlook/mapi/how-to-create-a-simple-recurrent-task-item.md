---
title: 创建简单的重复性任务项目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e9ee8865-0983-439e-8405-7946c5ec8762
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: be765915b729824b8c8b4209f125f354b02bad2b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394338"
---
# <a name="create-a-simple-recurrent-task-item"></a><span data-ttu-id="d6937-103">创建简单的重复性任务项目</span><span class="sxs-lookup"><span data-stu-id="d6937-103">Create a simple recurrent task item</span></span>

<span data-ttu-id="d6937-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d6937-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d6937-105">可以使用 MAPI 创建创建任务项目。</span><span class="sxs-lookup"><span data-stu-id="d6937-105">MAPI can be used to create to create task items.</span></span> <span data-ttu-id="d6937-106">本主题介绍如何创建简单的重复性任务项。</span><span class="sxs-lookup"><span data-stu-id="d6937-106">This topic describes how to create a simple recurrent task item.</span></span>
  
<span data-ttu-id="d6937-107">有关如何下载、 查看和 MFCMAPI 应用程序和此主题中所述的 CreateOutlookItemsAddin 项目从运行代码的信息，请参阅[安装使用本节中的示例](how-to-install-the-samples-used-in-this-section.md)。</span><span class="sxs-lookup"><span data-stu-id="d6937-107">For information about how to download, view, and run the code from the MFCMAPI application and CreateOutlookItemsAddin project referenced in this topic, see [Install the Samples Used in This Section](how-to-install-the-samples-used-in-this-section.md).</span></span>

### <a name="to-create-a-task-item"></a><span data-ttu-id="d6937-108">若要创建任务项目</span><span class="sxs-lookup"><span data-stu-id="d6937-108">To create a task item</span></span>

1. <span data-ttu-id="d6937-109">打开的消息存储。</span><span class="sxs-lookup"><span data-stu-id="d6937-109">Open a message store.</span></span> <span data-ttu-id="d6937-110">如何打开的消息存储的信息，请参阅[打开邮件存储区](opening-a-message-store.md)。</span><span class="sxs-lookup"><span data-stu-id="d6937-110">For information on how to open a message store, see [Opening a Message Store](opening-a-message-store.md).</span></span>
    
2. <span data-ttu-id="d6937-111">消息存储库中打开任务文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6937-111">Open the Tasks folder in the message store.</span></span> <span data-ttu-id="d6937-112">有关详细信息，请参阅**PR_IPM_TASK_ENTRYID** ([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="d6937-112">For more information, see **PR_IPM_TASK_ENTRYID** ([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md)).</span></span>
    
3. <span data-ttu-id="d6937-113">在任务文件夹，创建新任务项上调用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d6937-113">Call the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method on the Tasks folder to create the new task item.</span></span> 
    
4. <span data-ttu-id="d6937-114">**DispidTaskRecur** ([PidLidTaskRecurrence](pidlidtaskrecurrence-canonical-property.md)) 和创建重复性任务所需的其他与任务相关属性设置。</span><span class="sxs-lookup"><span data-stu-id="d6937-114">Set the **dispidTaskRecur** ([PidLidTaskRecurrence](pidlidtaskrecurrence-canonical-property.md)) property and other task-related properties required to create a recurrent task.</span></span>
    
5. <span data-ttu-id="d6937-115">保存新任务项。</span><span class="sxs-lookup"><span data-stu-id="d6937-115">Save the new task item.</span></span>
    
<span data-ttu-id="d6937-116">`AddTask` CreateOutlookItemsAddin 项目的 Tasks.cpp 源文件中的函数演示了这些步骤。</span><span class="sxs-lookup"><span data-stu-id="d6937-116">The  `AddTask` function in the Tasks.cpp source file of the CreateOutlookItemsAddin project demonstrates these steps.</span></span> <span data-ttu-id="d6937-117">`AddTask`函数采用参数从 MFCMAPI 示例应用程序中的**加载项**菜单上单击**添加任务**时显示**添加任务**对话框。</span><span class="sxs-lookup"><span data-stu-id="d6937-117">The  `AddTask` function takes parameters from the **Add Task** dialog box that is displayed when you click **Add Task** on the **Addins** menu in the MFCMAPI sample application.</span></span> <span data-ttu-id="d6937-118">`DisplayAddTaskDialog`中 Tasks.cpp 函数显示对话框，并将值传递从对话框到`AddTask`函数。</span><span class="sxs-lookup"><span data-stu-id="d6937-118">The  `DisplayAddTaskDialog` function in Tasks.cpp displays the dialog box and passes values from the dialog box to the  `AddTask` function.</span></span> <span data-ttu-id="d6937-119">`DisplayAddTaskDialog`函数直接与创建任务项目使用 MAPI，因此它不在此处列出是无关。</span><span class="sxs-lookup"><span data-stu-id="d6937-119">The  `DisplayAddTaskDialog` function does not relate directly to creating a task item using MAPI, so it is not listed here.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d6937-120">MFCMAPI 应用程序中的代码不能确保具有已选中**任务**文件夹，当您单击**加载项**菜单上的**添加任务**命令。</span><span class="sxs-lookup"><span data-stu-id="d6937-120">The code in the MFCMAPI application does not ensure that the **Tasks** folder has been selected when you click the **Add Task** command on the **Addins** menu.</span></span> <span data-ttu-id="d6937-121">在**任务**文件夹之外的文件夹中创建任务项目可能会导致未定义的行为。</span><span class="sxs-lookup"><span data-stu-id="d6937-121">Creating task items in a folder other than the **Tasks** folder can cause undefined behavior.</span></span> <span data-ttu-id="d6937-122">请确保您已使用 MFCMAPI 应用程序中**添加任务**命令之前选择**任务**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6937-122">Make sure that you have selected the **Tasks** folder before using the **Add Task** command in the MFCMAPI application.</span></span> 
  
<span data-ttu-id="d6937-123">`AddTask`下面列出了函数。</span><span class="sxs-lookup"><span data-stu-id="d6937-123">The  `AddTask` function is listed below.</span></span> <span data-ttu-id="d6937-124">请注意， _lpFolder_参数传递给`AddTask`函数是代表在其中创建新任务的文件夹的[IMAPIFolder](imapifolderimapicontainer.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="d6937-124">Note that the  _lpFolder_ parameter passed to the  `AddTask` function is a pointer to an [IMAPIFolder](imapifolderimapicontainer.md) interface that represents the folder where the new task is created.</span></span> <span data-ttu-id="d6937-125">给定_lpFolder_值，该值代表**IMAPIFolder**接口，代码调用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d6937-125">Given the  _lpFolder_ that represents an **IMAPIFolder** interface, the code calls the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method.</span></span> <span data-ttu-id="d6937-126">**CreateMessage**方法返回到指向**IMessage**接口的指针成功代码和一个指针。</span><span class="sxs-lookup"><span data-stu-id="d6937-126">The **CreateMessage** method returns a success code and a pointer to a pointer to an **IMessage** interface.</span></span> <span data-ttu-id="d6937-127">大多数的`AddTask`的函数代码处理的指定属性中调用[IMAPIProp::SetProps](imapiprop-setprops.md)方法的准备工作。</span><span class="sxs-lookup"><span data-stu-id="d6937-127">Most of the  `AddTask` function code handles the work of specifying properties in preparation for calling the [IMAPIProp::SetProps](imapiprop-setprops.md) method.</span></span> <span data-ttu-id="d6937-128">如果对**SetProps**方法的调用成功，调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法将更改提交到存储并创建新的任务项。</span><span class="sxs-lookup"><span data-stu-id="d6937-128">If the call to the **SetProps** method succeeds, the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method is called to commit the changes to the store and create a new task item.</span></span> 
  
<span data-ttu-id="d6937-129">`AddTask`函数设置大量的命名属性。</span><span class="sxs-lookup"><span data-stu-id="d6937-129">The  `AddTask` function sets a number of named properties.</span></span> <span data-ttu-id="d6937-130">命名的属性和如何创建这些信息，请参阅[创建 Outlook 2007 项使用 MAPI](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d6937-130">For information about named properties and how they are created, see [Using MAPI to Create Outlook 2007 Items](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx).</span></span> <span data-ttu-id="d6937-131">使用任务项目的命名的属性占用多个属性集，因为必须小心构建参数时要传递给[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d6937-131">Because the named properties used for task items occupy multiple property sets, care must be taken when building parameters to pass to the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method.</span></span> 
  
<span data-ttu-id="d6937-132">`AddTask`函数使用`BuildWeeklyTaskRecurrencePattern`helper 函数来构建表示**dispidTaskRecur**属性设置为任务周期的结构。</span><span class="sxs-lookup"><span data-stu-id="d6937-132">The  `AddTask` function uses the  `BuildWeeklyTaskRecurrencePattern` helper function to build a structure representing a task recurrence for setting the **dispidTaskRecur** property.</span></span> <span data-ttu-id="d6937-133">有关任务定期结构信息`BuildWeeklyTaskRecurrencePattern`函数生成，请参阅[PidLidTaskRecurrence 规范属性](pidlidtaskrecurrence-canonical-property.md)和[PidLidRecurrencePattern 规范属性](pidlidrecurrencepattern-canonical-property.md)。</span><span class="sxs-lookup"><span data-stu-id="d6937-133">For information on the task recurrence structure the  `BuildWeeklyTaskRecurrencePattern` function builds, see [PidLidTaskRecurrence Canonical Property](pidlidtaskrecurrence-canonical-property.md) and [PidLidRecurrencePattern Canonical Property](pidlidrecurrencepattern-canonical-property.md).</span></span> 

<span data-ttu-id="d6937-134">请注意，尽管大量不同的定期模式是可能的`BuildWeeklyTaskRecurrencePattern`函数仅生成每周定期模式。</span><span class="sxs-lookup"><span data-stu-id="d6937-134">Note that while a large variety of recurrence patterns are possible, the  `BuildWeeklyTaskRecurrencePattern` function only builds a weekly recurrence pattern.</span></span> <span data-ttu-id="d6937-135">还有硬编码假设，例如日历类型 （公历） （星期日） 的一周的第一天许多和修改或删除实例 （无） 数。</span><span class="sxs-lookup"><span data-stu-id="d6937-135">It is also hard coded for a number of assumptions, such as the calendar type (Gregorian), the first day of the week (Sunday), and the number of modified or deleted instances (none).</span></span> <span data-ttu-id="d6937-136">更多通用定期模式创建功能需要接受这些各种作为参数的变量。</span><span class="sxs-lookup"><span data-stu-id="d6937-136">A more general purpose recurrence pattern creation function would need to accept these sorts of variables as parameters.</span></span> 
  
<span data-ttu-id="d6937-137">下面是的完整列表`AddTask`函数。</span><span class="sxs-lookup"><span data-stu-id="d6937-137">The following is the complete listing of the  `AddTask` function.</span></span> 
  
```cpp
HRESULT AddTask(LPMAPIFOLDER lpFolder,
            SYSTEMTIME* lpstStart, // PidLidCommonEnd, PidLidTaskDueDate, PidLidTaskRecurrence
            SYSTEMTIME* lpstEnd, // PidLidTaskRecurrence
            SYSTEMTIME* lpstFirstDOW, // PidLidTaskRecurrence
            DWORD dwPeriod, // PidLidTaskRecurrence
            DWORD dwOccurrenceCount, // PidLidTaskRecurrence
            DWORD dwPatternTypeSpecific, // PidLidTaskRecurrence
            LPWSTR szSubject, // PR_SUBJECT_W
            LPWSTR szBody) // PR_BODY_W
{
   if (!lpFolder) return MAPI_E_INVALID_PARAMETER;
   HRESULT hRes = S_OK;
   LPMESSAGE lpMessage = 0;
   // create a message and set its properties
   hRes = lpFolder->CreateMessage(0,
      0,
      &lpMessage);
   if (SUCCEEDED(hRes))
   {
      MAPINAMEID  rgnmid[ulTaskProps];
      LPMAPINAMEID rgpnmid[ulTaskProps];
      LPSPropTagArray lpNamedPropTags = NULL;
      ULONG i = 0;
      for (i = 0 ; i < ulTaskProps ; i++)
      {
         if (i < ulFirstTaskProp)
            rgnmid[i].lpguid = (LPGUID)&PSETID_Common;
         else
            rgnmid[i].lpguid = (LPGUID)&PSETID_Task;
         rgnmid[i].ulKind = MNID_ID;
         rgnmid[i].Kind.lID = aulTaskProps[i];
         rgpnmid[i] = &rgnmid[i];
      }
      hRes = lpFolder->GetIDsFromNames(
         ulTaskProps,
         (LPMAPINAMEID*) &rgpnmid,
         NULL,
         &lpNamedPropTags);
      if (SUCCEEDED(hRes) && lpNamedPropTags)
      {
      // Because the properties to be set are known in advance, 
      // most of the structures involved can be statically declared 
      // to minimize expensive MAPIAllocateBuffer calls.
         SPropValue spvProps[NUM_PROPS] = {0};
         spvProps[p_PidLidTaskMode].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTaskMode],PT_LONG);
         spvProps[p_PidLidCommonEnd].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidCommonEnd],PT_SYSTIME);
         spvProps[p_PidLidTaskStatus].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTaskStatus],PT_LONG);
         spvProps[p_PidLidPercentComplete].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidPercentComplete],PT_DOUBLE);
         spvProps[p_PidLidTaskState].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTaskState],PT_LONG);
         spvProps[p_PidLidTaskRecurrence].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTaskRecurrence],PT_BINARY);
         spvProps[p_PidLidTaskDeadOccurrence].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTaskDeadOccurrence],PT_BOOLEAN);
         spvProps[p_PidLidTaskOwner].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTaskOwner],PT_UNICODE);
         spvProps[p_PidLidTaskFRecurring].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTaskFRecurring],PT_BOOLEAN);
         spvProps[p_PidLidTaskOwnership].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTaskOwnership],PT_LONG);
         spvProps[p_PidLidTaskAcceptanceState].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTaskAcceptanceState],PT_LONG);
         spvProps[p_PidLidTaskFFixOffline].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTaskFFixOffline],PT_BOOLEAN);
         spvProps[p_PidLidTaskDueDate].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTaskDueDate],PT_SYSTIME);
         spvProps[p_PidLidTaskComplete].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTaskComplete],PT_SYSTIME);
         spvProps[p_PR_MESSAGE_CLASS_W].ulPropTag   = PR_MESSAGE_CLASS_W;
         spvProps[p_PR_ICON_INDEX].ulPropTag        = PR_ICON_INDEX;
         spvProps[p_PR_SUBJECT_W].ulPropTag         = PR_SUBJECT_W;
         spvProps[p_PR_MESSAGE_FLAGS].ulPropTag     = PR_MESSAGE_FLAGS;
         spvProps[p_PR_BODY_W].ulPropTag            = PR_BODY_W;
         spvProps[p_PidLidTaskMode].Value.l = tdmtNothing;
         SYSTEMTIME stStartUTC = {0};
         TzSpecificLocalTimeToSystemTime(NULL,lpstStart,&stStartUTC);
         SystemTimeToFileTime(&stStartUTC,&spvProps[p_PidLidCommonEnd].Value.ft);
         spvProps[p_PidLidTaskStatus].Value.l = tsvNotStarted;
         spvProps[p_PidLidPercentComplete].Value.dbl = 0.0;
         spvProps[p_PidLidTaskState].Value.l = tdsOWNNEW;
         spvProps[p_PidLidTaskDeadOccurrence].Value.b = false;
         spvProps[p_PidLidTaskOwner].Value.lpszW = L"Unknown";
         spvProps[p_PidLidTaskFRecurring].Value.b = true;
         spvProps[p_PidLidTaskOwnership].Value.l = tovNew;
         spvProps[p_PidLidTaskAcceptanceState].Value.l = tdvNone;
         spvProps[p_PidLidTaskFFixOffline].Value.b = true;
         SystemTimeToFileTime(lpstStart,&spvProps[p_PidLidTaskDueDate].Value.ft);
         spvProps[p_PidLidTaskComplete].Value.b = false;
         spvProps[p_PR_MESSAGE_CLASS_W].Value.lpszW = L"IPM.Task";
         spvProps[p_PR_ICON_INDEX].Value.l = 0x501; // Unassigned Recurring Task
         spvProps[p_PR_SUBJECT_W].Value.lpszW = szSubject;
         spvProps[p_PR_MESSAGE_FLAGS].Value.l = MSGFLAG_READ;
         spvProps[p_PR_BODY_W].Value.lpszW = szBody;
         hRes = BuildWeeklyTaskRecurrencePattern(
            lpstStart,
            lpstEnd,
            lpstFirstDOW,
            dwPeriod,
            dwOccurrenceCount,
            dwPatternTypeSpecific,
            &spvProps[p_PidLidTaskRecurrence].Value.bin.cb,
            &spvProps[p_PidLidTaskRecurrence].Value.bin.lpb);
         if (SUCCEEDED(hRes))
         {
            hRes = lpMessage->SetProps(NUM_PROPS, spvProps, NULL);
            if (SUCCEEDED(hRes))
            {
               hRes = lpMessage->SaveChanges(FORCE_SAVE);
            }
         }
         if (spvProps[p_PidLidTaskRecurrence].Value.bin.lpb)
            delete[] spvProps[p_PidLidTaskRecurrence].Value.bin.lpb;
      }
      MAPIFreeBuffer(lpNamedPropTags);
   }
   if (lpMessage) lpMessage->Release();
   return hRes;
}

```

## <a name="see-also"></a><span data-ttu-id="d6937-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6937-138">See also</span></span>

- [<span data-ttu-id="d6937-139">使用 MAPI 创建 Outlook 2007 项</span><span class="sxs-lookup"><span data-stu-id="d6937-139">Using MAPI to Create Outlook 2007 Items</span></span>](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)

