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
# <a name="create-a-simple-recurrent-task-item"></a>创建简单定期任务项

**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 可用于创建任务项。 本主题介绍如何创建简单的重复性任务项。
  
有关如何从本主题所引用的 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目中下载、查看和运行代码的信息, 请参阅[Install the 本节中使用的示例](how-to-install-the-samples-used-in-this-section.md)。

### <a name="to-create-a-task-item"></a>创建任务项

1. 打开邮件存储区。 有关如何打开邮件存储区的信息, 请参阅[打开邮件存储](opening-a-message-store.md)。
    
2. 打开邮件存储区中的 "任务" 文件夹。 有关详细信息, 请参阅**PR_IPM_TASK_ENTRYID** ([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md))。
    
3. 在 "任务" 文件夹中调用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法, 以创建新的任务项。 
    
4. 设置**dispidTaskRecur** ([PidLidTaskRecurrence](pidlidtaskrecurrence-canonical-property.md)) 属性以及创建重复性任务所需的其他与任务相关的属性。
    
5. 保存新的任务项。
    
CreateOutlookItemsAddin `AddTask`项目的任务 .cpp 源文件中的函数演示这些步骤。 `AddTask`函数采用 "**添加任务**" 对话框中的参数, 当您在 MFCMAPI 示例应用程序中的 " **Addins** " 菜单上单击 "**添加任务**" 时, 将显示此对话框。 Tasks `DisplayAddTaskDialog`中的函数显示对话框, 并将对话框中的值传递给`AddTask`函数。 该`DisplayAddTaskDialog`函数与使用 MAPI 创建任务项不直接相关, 因此此处未列出它。 
  
> [!IMPORTANT]
> 当您单击**Addins**菜单上的 "**添加任务**" 命令时, MFCMAPI 应用程序中的代码不会确保已选择 "**任务**" 文件夹。 在除 "**任务**" 文件夹之外的文件夹中创建任务项可能会导致未定义的行为。 在 MFCMAPI 应用程序中使用 "**添加任务**" 命令之前, 请确保已选择 "**任务**" 文件夹。 
  
`AddTask`函数如下所示。 请注意, __ 传递给`AddTask`函数的 lpFolder 参数是指向[IMAPIFolder](imapifolderimapicontainer.md)接口的指针, 该接口表示创建新任务的文件夹。 给定表示**IMAPIFolder**接口的_lpFolder_ , 该代码调用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法。 **CreateMessage**方法返回一个成功代码和一个指向**IMessage**接口的指针的指针。 大部分`AddTask`函数代码处理指定属性的工作, 以准备调用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法。 如果对**SetProps**方法的调用成功, 则调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以提交对存储的更改, 并创建新的任务项。 
  
`AddTask`函数设置许多命名属性。 有关命名属性及其创建方式的信息, 请参阅[使用 MAPI 创建 Outlook 2007 项目](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)。 由于用于任务项的命名属性占用了多个属性集, 因此在生成参数以传递给[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法时必须小心谨慎。 
  
`AddTask`函数使用`BuildWeeklyTaskRecurrencePattern` helper 函数生成一个结构, 该结构表示设置**dispidTaskRecur**属性的任务周期。 有关`BuildWeeklyTaskRecurrencePattern`函数生成的任务定期结构的信息, 请参阅[PidLidTaskRecurrence 规范属性](pidlidtaskrecurrence-canonical-property.md)和[PidLidRecurrencePattern 规范属性](pidlidrecurrencepattern-canonical-property.md)。 

请注意, 尽管可以使用大量的定期模式, 但该`BuildWeeklyTaskRecurrencePattern`函数只生成每周定期模式。 它也是硬编码的一些假设, 例如日历类型 (公历)、一周的第一天 (星期日) 以及已修改或已删除的实例数 (无)。 更常规用途的定期模式创建函数需要接受这些种类的变量作为参数。 
  
下面是该`AddTask`函数的完整列表。 
  
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

- [使用 MAPI 创建 Outlook 2007 项目](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)

