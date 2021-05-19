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
# <a name="create-a-simple-recurrent-task-item"></a><span data-ttu-id="b3986-103">创建简单定期任务项</span><span class="sxs-lookup"><span data-stu-id="b3986-103">Create a simple recurrent task item</span></span>

<span data-ttu-id="b3986-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b3986-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b3986-105">MAPI 可用于创建任务项。</span><span class="sxs-lookup"><span data-stu-id="b3986-105">MAPI can be used to create to create task items.</span></span> <span data-ttu-id="b3986-106">本主题介绍如何创建简单的重复性任务项。</span><span class="sxs-lookup"><span data-stu-id="b3986-106">This topic describes how to create a simple recurrent task item.</span></span>
  
<span data-ttu-id="b3986-107">若要了解如何从本主题中引用的 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目下载、查看和运行代码，请参阅安装本节中使用的示例[。](how-to-install-the-samples-used-in-this-section.md)</span><span class="sxs-lookup"><span data-stu-id="b3986-107">For information about how to download, view, and run the code from the MFCMAPI application and CreateOutlookItemsAddin project referenced in this topic, see [Install the Samples Used in This Section](how-to-install-the-samples-used-in-this-section.md).</span></span>

### <a name="to-create-a-task-item"></a><span data-ttu-id="b3986-108">创建任务项</span><span class="sxs-lookup"><span data-stu-id="b3986-108">To create a task item</span></span>

1. <span data-ttu-id="b3986-109">打开邮件存储。</span><span class="sxs-lookup"><span data-stu-id="b3986-109">Open a message store.</span></span> <span data-ttu-id="b3986-110">若要了解如何打开邮件存储，请参阅打开 [邮件存储](opening-a-message-store.md)。</span><span class="sxs-lookup"><span data-stu-id="b3986-110">For information on how to open a message store, see [Opening a Message Store](opening-a-message-store.md).</span></span>
    
2. <span data-ttu-id="b3986-111">打开邮件存储中的"任务"文件夹。</span><span class="sxs-lookup"><span data-stu-id="b3986-111">Open the Tasks folder in the message store.</span></span> <span data-ttu-id="b3986-112">有关详细信息，请参阅 **PR_IPM_TASK_ENTRYID** ([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="b3986-112">For more information, see **PR_IPM_TASK_ENTRYID** ([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md)).</span></span>
    
3. <span data-ttu-id="b3986-113">在 ["任务"文件夹上调用 IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法以创建新的任务项。</span><span class="sxs-lookup"><span data-stu-id="b3986-113">Call the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method on the Tasks folder to create the new task item.</span></span> 
    
4. <span data-ttu-id="b3986-114">将 **dispidTaskRecur** ([PidLidTaskRecurrence](pidlidtaskrecurrence-canonical-property.md)) 属性和其他与任务相关的属性设置为创建重复性任务所需的属性。</span><span class="sxs-lookup"><span data-stu-id="b3986-114">Set the **dispidTaskRecur** ([PidLidTaskRecurrence](pidlidtaskrecurrence-canonical-property.md)) property and other task-related properties required to create a recurrent task.</span></span>
    
5. <span data-ttu-id="b3986-115">保存新任务项。</span><span class="sxs-lookup"><span data-stu-id="b3986-115">Save the new task item.</span></span>
    
<span data-ttu-id="b3986-116">`AddTask`CreateOutlookItemsAddin 项目的 Tasks.cpp 源文件中的 函数演示了这些步骤。</span><span class="sxs-lookup"><span data-stu-id="b3986-116">The  `AddTask` function in the Tasks.cpp source file of the CreateOutlookItemsAddin project demonstrates these steps.</span></span> <span data-ttu-id="b3986-117">函数从"添加任务"对话框中接受参数，该对话框在 MFCMAPI 示例应用程序中的"加载项"菜单上单击"添加任务 `AddTask` "时显示。   </span><span class="sxs-lookup"><span data-stu-id="b3986-117">The  `AddTask` function takes parameters from the **Add Task** dialog box that is displayed when you click **Add Task** on the **Addins** menu in the MFCMAPI sample application.</span></span> <span data-ttu-id="b3986-118">Tasks.cpp 中的 函数显示对话框，将对话框中的值传递给  `DisplayAddTaskDialog`  `AddTask` 函数。</span><span class="sxs-lookup"><span data-stu-id="b3986-118">The  `DisplayAddTaskDialog` function in Tasks.cpp displays the dialog box and passes values from the dialog box to the  `AddTask` function.</span></span> <span data-ttu-id="b3986-119">`DisplayAddTaskDialog`该函数与使用 MAPI 创建任务项没有直接关系，因此未在此处列出。</span><span class="sxs-lookup"><span data-stu-id="b3986-119">The  `DisplayAddTaskDialog` function does not relate directly to creating a task item using MAPI, so it is not listed here.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b3986-120">当您单击"加载项"菜单上的"添加任务"命令时，MFCMAPI 应用程序中的代码并不确保已选择"任务"**文件夹。** </span><span class="sxs-lookup"><span data-stu-id="b3986-120">The code in the MFCMAPI application does not ensure that the **Tasks** folder has been selected when you click the **Add Task** command on the **Addins** menu.</span></span> <span data-ttu-id="b3986-121">在"任务"文件夹外的文件夹创建任务项可能会导致未定义行为。</span><span class="sxs-lookup"><span data-stu-id="b3986-121">Creating task items in a folder other than the **Tasks** folder can cause undefined behavior.</span></span> <span data-ttu-id="b3986-122">在 MFCMAPI应用程序中使用"添加任务"命令之前，请确保已选择"任务"文件夹。</span><span class="sxs-lookup"><span data-stu-id="b3986-122">Make sure that you have selected the **Tasks** folder before using the **Add Task** command in the MFCMAPI application.</span></span> 
  
<span data-ttu-id="b3986-123">函数  `AddTask` 如下所示。</span><span class="sxs-lookup"><span data-stu-id="b3986-123">The  `AddTask` function is listed below.</span></span> <span data-ttu-id="b3986-124">请注意，传递给函数的  _lpFolder_ 参数是指向  `AddTask` [IMAPIFolder](imapifolderimapicontainer.md) 接口的指针，该接口表示新建任务的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b3986-124">Note that the  _lpFolder_ parameter passed to the  `AddTask` function is a pointer to an [IMAPIFolder](imapifolderimapicontainer.md) interface that represents the folder where the new task is created.</span></span> <span data-ttu-id="b3986-125">在给定表示 **IMAPIFolder** 接口的 _lpFolder_ 后，代码将调用 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b3986-125">Given the  _lpFolder_ that represents an **IMAPIFolder** interface, the code calls the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method.</span></span> <span data-ttu-id="b3986-126">**CreateMessage** 方法返回成功代码和指向 **指向 IMessage** 接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b3986-126">The **CreateMessage** method returns a success code and a pointer to a pointer to an **IMessage** interface.</span></span> <span data-ttu-id="b3986-127">大多数函数代码处理指定属性的工作，以准备调用  `AddTask` [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="b3986-127">Most of the  `AddTask` function code handles the work of specifying properties in preparation for calling the [IMAPIProp::SetProps](imapiprop-setprops.md) method.</span></span> <span data-ttu-id="b3986-128">如果 **调用 SetProps** 方法成功，将调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法以将更改提交到存储并创建新的任务项。</span><span class="sxs-lookup"><span data-stu-id="b3986-128">If the call to the **SetProps** method succeeds, the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method is called to commit the changes to the store and create a new task item.</span></span> 
  
<span data-ttu-id="b3986-129">该  `AddTask` 函数设置许多命名属性。</span><span class="sxs-lookup"><span data-stu-id="b3986-129">The  `AddTask` function sets a number of named properties.</span></span> <span data-ttu-id="b3986-130">有关命名属性及其创建方式的信息，请参阅使用 [MAPI 创建 Outlook 2007 项目](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b3986-130">For information about named properties and how they are created, see [Using MAPI to Create Outlook 2007 Items](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx).</span></span> <span data-ttu-id="b3986-131">由于用于任务项的命名属性占用多个属性集，因此在构建参数以传递到 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 方法时必须小心。</span><span class="sxs-lookup"><span data-stu-id="b3986-131">Because the named properties used for task items occupy multiple property sets, care must be taken when building parameters to pass to the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method.</span></span> 
  
<span data-ttu-id="b3986-132">该函数使用 helper 函数构建一个表示任务定期的结构，用于  `AddTask`  `BuildWeeklyTaskRecurrencePattern` 设置 **dispidTaskRecur** 属性。</span><span class="sxs-lookup"><span data-stu-id="b3986-132">The  `AddTask` function uses the  `BuildWeeklyTaskRecurrencePattern` helper function to build a structure representing a task recurrence for setting the **dispidTaskRecur** property.</span></span> <span data-ttu-id="b3986-133">有关函数生成的任务定期结构的信息，请参阅  `BuildWeeklyTaskRecurrencePattern` [PidLidTaskRecurrence 规范属性](pidlidtaskrecurrence-canonical-property.md) 和 [PidLidRecurrencePattern 规范属性](pidlidrecurrencepattern-canonical-property.md)。</span><span class="sxs-lookup"><span data-stu-id="b3986-133">For information on the task recurrence structure the  `BuildWeeklyTaskRecurrencePattern` function builds, see [PidLidTaskRecurrence Canonical Property](pidlidtaskrecurrence-canonical-property.md) and [PidLidRecurrencePattern Canonical Property](pidlidrecurrencepattern-canonical-property.md).</span></span> 

<span data-ttu-id="b3986-134">请注意，虽然可能有多种定期模式，但函数仅  `BuildWeeklyTaskRecurrencePattern` 构建每周一定期模式。</span><span class="sxs-lookup"><span data-stu-id="b3986-134">Note that while a large variety of recurrence patterns are possible, the  `BuildWeeklyTaskRecurrencePattern` function only builds a weekly recurrence pattern.</span></span> <span data-ttu-id="b3986-135">它还针对许多假设进行了硬编码，例如日历类型 (公历) 、每周的第一天 (星期日) 以及修改或删除的实例数 (无) 。</span><span class="sxs-lookup"><span data-stu-id="b3986-135">It is also hard coded for a number of assumptions, such as the calendar type (Gregorian), the first day of the week (Sunday), and the number of modified or deleted instances (none).</span></span> <span data-ttu-id="b3986-136">创建函数定期模式需要接受这些类型的变量作为参数。</span><span class="sxs-lookup"><span data-stu-id="b3986-136">A more general purpose recurrence pattern creation function would need to accept these sorts of variables as parameters.</span></span> 
  
<span data-ttu-id="b3986-137">以下是 函数的完整  `AddTask` 列表。</span><span class="sxs-lookup"><span data-stu-id="b3986-137">The following is the complete listing of the  `AddTask` function.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="b3986-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3986-138">See also</span></span>

- [<span data-ttu-id="b3986-139">使用 MAPI 创建 Outlook 2007 项目</span><span class="sxs-lookup"><span data-stu-id="b3986-139">Using MAPI to Create Outlook 2007 Items</span></span>](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)

