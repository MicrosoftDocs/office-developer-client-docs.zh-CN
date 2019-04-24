---
title: 创建简单定期任务项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e9ee8865-0983-439e-8405-7946c5ec8762
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: be765915b729824b8c8b4209f125f354b02bad2b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345470"
---
# <a name="create-a-simple-recurrent-task-item"></a><span data-ttu-id="702f4-103">创建简单定期任务项</span><span class="sxs-lookup"><span data-stu-id="702f4-103">Create a simple recurrent task item</span></span>

<span data-ttu-id="702f4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="702f4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="702f4-105">MAPI 可用于创建任务项。</span><span class="sxs-lookup"><span data-stu-id="702f4-105">MAPI can be used to create to create task items.</span></span> <span data-ttu-id="702f4-106">本主题介绍如何创建简单的重复性任务项。</span><span class="sxs-lookup"><span data-stu-id="702f4-106">This topic describes how to create a simple recurrent task item.</span></span>
  
<span data-ttu-id="702f4-107">有关如何从本主题所引用的 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目中下载、查看和运行代码的信息, 请参阅[Install the 本节中使用的示例](how-to-install-the-samples-used-in-this-section.md)。</span><span class="sxs-lookup"><span data-stu-id="702f4-107">For information about how to download, view, and run the code from the MFCMAPI application and CreateOutlookItemsAddin project referenced in this topic, see [Install the Samples Used in This Section](how-to-install-the-samples-used-in-this-section.md).</span></span>

### <a name="to-create-a-task-item"></a><span data-ttu-id="702f4-108">创建任务项</span><span class="sxs-lookup"><span data-stu-id="702f4-108">To create a task item</span></span>

1. <span data-ttu-id="702f4-109">打开邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="702f4-109">Open a message store.</span></span> <span data-ttu-id="702f4-110">有关如何打开邮件存储区的信息, 请参阅[打开邮件存储](opening-a-message-store.md)。</span><span class="sxs-lookup"><span data-stu-id="702f4-110">For information on how to open a message store, see [Opening a Message Store](opening-a-message-store.md).</span></span>
    
2. <span data-ttu-id="702f4-111">打开邮件存储区中的 "任务" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="702f4-111">Open the Tasks folder in the message store.</span></span> <span data-ttu-id="702f4-112">有关详细信息, 请参阅**PR_IPM_TASK_ENTRYID** ([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="702f4-112">For more information, see **PR_IPM_TASK_ENTRYID** ([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md)).</span></span>
    
3. <span data-ttu-id="702f4-113">在 "任务" 文件夹中调用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法, 以创建新的任务项。</span><span class="sxs-lookup"><span data-stu-id="702f4-113">Call the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method on the Tasks folder to create the new task item.</span></span> 
    
4. <span data-ttu-id="702f4-114">设置**dispidTaskRecur** ([PidLidTaskRecurrence](pidlidtaskrecurrence-canonical-property.md)) 属性以及创建重复性任务所需的其他与任务相关的属性。</span><span class="sxs-lookup"><span data-stu-id="702f4-114">Set the **dispidTaskRecur** ([PidLidTaskRecurrence](pidlidtaskrecurrence-canonical-property.md)) property and other task-related properties required to create a recurrent task.</span></span>
    
5. <span data-ttu-id="702f4-115">保存新的任务项。</span><span class="sxs-lookup"><span data-stu-id="702f4-115">Save the new task item.</span></span>
    
<span data-ttu-id="702f4-116">CreateOutlookItemsAddin `AddTask`项目的任务 .cpp 源文件中的函数演示这些步骤。</span><span class="sxs-lookup"><span data-stu-id="702f4-116">The  `AddTask` function in the Tasks.cpp source file of the CreateOutlookItemsAddin project demonstrates these steps.</span></span> <span data-ttu-id="702f4-117">`AddTask`函数采用 "**添加任务**" 对话框中的参数, 当您在 MFCMAPI 示例应用程序中的 " **Addins** " 菜单上单击 "**添加任务**" 时, 将显示此对话框。</span><span class="sxs-lookup"><span data-stu-id="702f4-117">The  `AddTask` function takes parameters from the **Add Task** dialog box that is displayed when you click **Add Task** on the **Addins** menu in the MFCMAPI sample application.</span></span> <span data-ttu-id="702f4-118">Tasks `DisplayAddTaskDialog`中的函数显示对话框, 并将对话框中的值传递给`AddTask`函数。</span><span class="sxs-lookup"><span data-stu-id="702f4-118">The  `DisplayAddTaskDialog` function in Tasks.cpp displays the dialog box and passes values from the dialog box to the  `AddTask` function.</span></span> <span data-ttu-id="702f4-119">该`DisplayAddTaskDialog`函数与使用 MAPI 创建任务项不直接相关, 因此此处未列出它。</span><span class="sxs-lookup"><span data-stu-id="702f4-119">The  `DisplayAddTaskDialog` function does not relate directly to creating a task item using MAPI, so it is not listed here.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="702f4-120">当您单击**Addins**菜单上的 "**添加任务**" 命令时, MFCMAPI 应用程序中的代码不会确保已选择 "**任务**" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="702f4-120">The code in the MFCMAPI application does not ensure that the **Tasks** folder has been selected when you click the **Add Task** command on the **Addins** menu.</span></span> <span data-ttu-id="702f4-121">在除 "**任务**" 文件夹之外的文件夹中创建任务项可能会导致未定义的行为。</span><span class="sxs-lookup"><span data-stu-id="702f4-121">Creating task items in a folder other than the **Tasks** folder can cause undefined behavior.</span></span> <span data-ttu-id="702f4-122">在 MFCMAPI 应用程序中使用 "**添加任务**" 命令之前, 请确保已选择 "**任务**" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="702f4-122">Make sure that you have selected the **Tasks** folder before using the **Add Task** command in the MFCMAPI application.</span></span> 
  
<span data-ttu-id="702f4-123">`AddTask`函数如下所示。</span><span class="sxs-lookup"><span data-stu-id="702f4-123">The  `AddTask` function is listed below.</span></span> <span data-ttu-id="702f4-124">请注意, __ 传递给`AddTask`函数的 lpFolder 参数是指向[IMAPIFolder](imapifolderimapicontainer.md)接口的指针, 该接口表示创建新任务的文件夹。</span><span class="sxs-lookup"><span data-stu-id="702f4-124">Note that the  _lpFolder_ parameter passed to the  `AddTask` function is a pointer to an [IMAPIFolder](imapifolderimapicontainer.md) interface that represents the folder where the new task is created.</span></span> <span data-ttu-id="702f4-125">给定表示**IMAPIFolder**接口的_lpFolder_ , 该代码调用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="702f4-125">Given the  _lpFolder_ that represents an **IMAPIFolder** interface, the code calls the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method.</span></span> <span data-ttu-id="702f4-126">**CreateMessage**方法返回一个成功代码和一个指向**IMessage**接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="702f4-126">The **CreateMessage** method returns a success code and a pointer to a pointer to an **IMessage** interface.</span></span> <span data-ttu-id="702f4-127">大部分`AddTask`函数代码处理指定属性的工作, 以准备调用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="702f4-127">Most of the  `AddTask` function code handles the work of specifying properties in preparation for calling the [IMAPIProp::SetProps](imapiprop-setprops.md) method.</span></span> <span data-ttu-id="702f4-128">如果对**SetProps**方法的调用成功, 则调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以提交对存储的更改, 并创建新的任务项。</span><span class="sxs-lookup"><span data-stu-id="702f4-128">If the call to the **SetProps** method succeeds, the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method is called to commit the changes to the store and create a new task item.</span></span> 
  
<span data-ttu-id="702f4-129">`AddTask`函数设置许多命名属性。</span><span class="sxs-lookup"><span data-stu-id="702f4-129">The  `AddTask` function sets a number of named properties.</span></span> <span data-ttu-id="702f4-130">有关命名属性及其创建方式的信息, 请参阅[使用 MAPI 创建 Outlook 2007 项目](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="702f4-130">For information about named properties and how they are created, see [Using MAPI to Create Outlook 2007 Items](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx).</span></span> <span data-ttu-id="702f4-131">由于用于任务项的命名属性占用了多个属性集, 因此在生成参数以传递给[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法时必须小心谨慎。</span><span class="sxs-lookup"><span data-stu-id="702f4-131">Because the named properties used for task items occupy multiple property sets, care must be taken when building parameters to pass to the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method.</span></span> 
  
<span data-ttu-id="702f4-132">`AddTask`函数使用`BuildWeeklyTaskRecurrencePattern` helper 函数生成一个结构, 该结构表示设置**dispidTaskRecur**属性的任务周期。</span><span class="sxs-lookup"><span data-stu-id="702f4-132">The  `AddTask` function uses the  `BuildWeeklyTaskRecurrencePattern` helper function to build a structure representing a task recurrence for setting the **dispidTaskRecur** property.</span></span> <span data-ttu-id="702f4-133">有关`BuildWeeklyTaskRecurrencePattern`函数生成的任务定期结构的信息, 请参阅[PidLidTaskRecurrence 规范属性](pidlidtaskrecurrence-canonical-property.md)和[PidLidRecurrencePattern 规范属性](pidlidrecurrencepattern-canonical-property.md)。</span><span class="sxs-lookup"><span data-stu-id="702f4-133">For information on the task recurrence structure the  `BuildWeeklyTaskRecurrencePattern` function builds, see [PidLidTaskRecurrence Canonical Property](pidlidtaskrecurrence-canonical-property.md) and [PidLidRecurrencePattern Canonical Property](pidlidrecurrencepattern-canonical-property.md).</span></span> 

<span data-ttu-id="702f4-134">请注意, 尽管可以使用大量的定期模式, 但该`BuildWeeklyTaskRecurrencePattern`函数只生成每周定期模式。</span><span class="sxs-lookup"><span data-stu-id="702f4-134">Note that while a large variety of recurrence patterns are possible, the  `BuildWeeklyTaskRecurrencePattern` function only builds a weekly recurrence pattern.</span></span> <span data-ttu-id="702f4-135">它也是硬编码的一些假设, 例如日历类型 (公历)、一周的第一天 (星期日) 以及已修改或已删除的实例数 (无)。</span><span class="sxs-lookup"><span data-stu-id="702f4-135">It is also hard coded for a number of assumptions, such as the calendar type (Gregorian), the first day of the week (Sunday), and the number of modified or deleted instances (none).</span></span> <span data-ttu-id="702f4-136">更常规用途的定期模式创建函数需要接受这些种类的变量作为参数。</span><span class="sxs-lookup"><span data-stu-id="702f4-136">A more general purpose recurrence pattern creation function would need to accept these sorts of variables as parameters.</span></span> 
  
<span data-ttu-id="702f4-137">下面是该`AddTask`函数的完整列表。</span><span class="sxs-lookup"><span data-stu-id="702f4-137">The following is the complete listing of the  `AddTask` function.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="702f4-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="702f4-138">See also</span></span>

- [<span data-ttu-id="702f4-139">使用 MAPI 创建 Outlook 2007 项目</span><span class="sxs-lookup"><span data-stu-id="702f4-139">Using MAPI to Create Outlook 2007 Items</span></span>](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)

