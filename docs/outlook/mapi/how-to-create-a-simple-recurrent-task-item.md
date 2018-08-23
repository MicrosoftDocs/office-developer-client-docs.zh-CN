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
ms.openlocfilehash: 68d7472f993bcc35abbd4b733bae9f137b948608
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576839"
---
# <a name="create-a-simple-recurrent-task-item"></a>创建简单的重复性任务项目

**适用于**： Outlook 2013 |Outlook 2016 
  
可以使用 MAPI 创建创建任务项目。 本主题介绍如何创建简单的重复性任务项。
  
有关如何下载、 查看和 MFCMAPI 应用程序和此主题中所述的 CreateOutlookItemsAddin 项目从运行代码的信息，请参阅[安装使用本节中的示例](how-to-install-the-samples-used-in-this-section.md)。

### <a name="to-create-a-task-item"></a>若要创建任务项目

1. 打开的消息存储。 如何打开的消息存储的信息，请参阅[打开邮件存储区](opening-a-message-store.md)。
    
2. 消息存储库中打开任务文件夹。 有关详细信息，请参阅**PR_IPM_TASK_ENTRYID** ([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md))。
    
3. 在任务文件夹，创建新任务项上调用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法。 
    
4. **DispidTaskRecur** ([PidLidTaskRecurrence](pidlidtaskrecurrence-canonical-property.md)) 和创建重复性任务所需的其他与任务相关属性设置。
    
5. 保存新任务项。
    
`AddTask` CreateOutlookItemsAddin 项目的 Tasks.cpp 源文件中的函数演示了这些步骤。 `AddTask`函数采用参数从 MFCMAPI 示例应用程序中的**加载项**菜单上单击**添加任务**时显示**添加任务**对话框。 `DisplayAddTaskDialog`中 Tasks.cpp 函数显示对话框，并将值传递从对话框到`AddTask`函数。 `DisplayAddTaskDialog`函数直接与创建任务项目使用 MAPI，因此它不在此处列出是无关。 
  
> [!IMPORTANT]
> MFCMAPI 应用程序中的代码不能确保具有已选中**任务**文件夹，当您单击**加载项**菜单上的**添加任务**命令。 在**任务**文件夹之外的文件夹中创建任务项目可能会导致未定义的行为。 请确保您已使用 MFCMAPI 应用程序中**添加任务**命令之前选择**任务**文件夹。 
  
`AddTask`下面列出了函数。 请注意， _lpFolder_参数传递给`AddTask`函数是代表在其中创建新任务的文件夹的[IMAPIFolder](imapifolderimapicontainer.md)接口的指针。 给定_lpFolder_值，该值代表**IMAPIFolder**接口，代码调用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法。 **CreateMessage**方法返回到指向**IMessage**接口的指针成功代码和一个指针。 大多数的`AddTask`的函数代码处理的指定属性中调用[IMAPIProp::SetProps](imapiprop-setprops.md)方法的准备工作。 如果对**SetProps**方法的调用成功，调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法将更改提交到存储并创建新的任务项。 
  
`AddTask`函数设置大量的命名属性。 命名的属性和如何创建这些信息，请参阅[创建 Outlook 2007 项使用 MAPI](http://msdn.microsoft.com/en-us/library/cc678348%28office.12%29.aspx)。 使用任务项目的命名的属性占用多个属性集，因为必须小心构建参数时要传递给[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法。 
  
`AddTask`函数使用`BuildWeeklyTaskRecurrencePattern`helper 函数来构建表示**dispidTaskRecur**属性设置为任务周期的结构。 有关任务定期结构信息`BuildWeeklyTaskRecurrencePattern`函数生成，请参阅[PidLidTaskRecurrence 规范属性](pidlidtaskrecurrence-canonical-property.md)和[PidLidRecurrencePattern 规范属性](pidlidrecurrencepattern-canonical-property.md)。 

请注意，尽管大量不同的定期模式是可能的`BuildWeeklyTaskRecurrencePattern`函数仅生成每周定期模式。 还有硬编码假设，例如日历类型 （公历） （星期日） 的一周的第一天许多和修改或删除实例 （无） 数。 更多通用定期模式创建功能需要接受这些各种作为参数的变量。 
  
下面是的完整列表`AddTask`函数。 
  
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

## <a name="see-also"></a>另请参阅

- [使用 MAPI 创建 Outlook 2007 项](http://msdn.microsoft.com/en-us/library/cc678348%28office.12%29.aspx)

