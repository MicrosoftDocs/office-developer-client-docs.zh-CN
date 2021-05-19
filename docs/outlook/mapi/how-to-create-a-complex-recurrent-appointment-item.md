---
title: 创建复杂定期约会项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: da9626da-5ba5-4f18-954c-4e23971d23e8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d44bf5cccd7e846530eae0c03b8d3ff525f3c012
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344532"
---
# <a name="create-a-complex-recurrent-appointment-item"></a><span data-ttu-id="b5b6f-103">创建复杂定期约会项</span><span class="sxs-lookup"><span data-stu-id="b5b6f-103">Create a complex recurrent appointment item</span></span>
  
<span data-ttu-id="b5b6f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b5b6f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b5b6f-105">MAPI 可用于创建定期约会项目。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-105">MAPI can be used to create recurring appointment items.</span></span>
  
<span data-ttu-id="b5b6f-106">若要了解如何从本主题中引用的 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目下载、查看和运行代码，请参阅安装本节中使用的示例[。](how-to-install-the-samples-used-in-this-section.md)</span><span class="sxs-lookup"><span data-stu-id="b5b6f-106">For information about how to download, view, and run the code from the MFCMAPI application and CreateOutlookItemsAddin project referenced in this topic, see [Install the Samples Used in This Section](how-to-install-the-samples-used-in-this-section.md).</span></span>

### <a name="to-create-an-appointment-item"></a><span data-ttu-id="b5b6f-107">创建约会项目</span><span class="sxs-lookup"><span data-stu-id="b5b6f-107">To create an appointment item</span></span>

1. <span data-ttu-id="b5b6f-108">打开邮件存储。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-108">Open a message store.</span></span> <span data-ttu-id="b5b6f-109">若要了解如何打开邮件存储，请参阅打开 [邮件存储](opening-a-message-store.md)。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-109">For information on how to open a message store, see [Opening a Message Store](opening-a-message-store.md).</span></span>
    
2. <span data-ttu-id="b5b6f-110">打开邮件存储中的"日历"文件夹。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-110">Open a Calendar folder in the message store.</span></span> <span data-ttu-id="b5b6f-111">请参阅 **PR_IPM_APPOINTMENT_ENTRYID** ([PidTagIpmAppointmentEntryId](pidtagipmappointmententryid-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-111">See **PR_IPM_APPOINTMENT_ENTRYID** ([PidTagIpmAppointmentEntryId](pidtagipmappointmententryid-canonical-property.md)).</span></span>
    
3. <span data-ttu-id="b5b6f-112">对 ["日历"文件夹调用 IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法以创建新的约会项目。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-112">Call the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method on the Calendar folder to create the new appointment item.</span></span> 
    
4. <span data-ttu-id="b5b6f-113">设置 **dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) 创建定期约会所需的属性和其他属性。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-113">Set the **dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) property and other properties required to create a recurrent appointment.</span></span>
    
5. <span data-ttu-id="b5b6f-114">保存新的约会项目。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-114">Save the new appointment item.</span></span>
    
<span data-ttu-id="b5b6f-115">`AddAppointment`CreateOutlookItemsAddin 项目的 Appointments.cpp 源文件中的 函数演示了这些步骤。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-115">The  `AddAppointment` function in the Appointments.cpp source file of the CreateOutlookItemsAddin project demonstrates these steps.</span></span> <span data-ttu-id="b5b6f-116">该 `AddAppointment` 函数从 MFCMAPI 示例应用程序中的 **Addins** 菜单上单击"添加约会"时显示的"添加约会"对话框中获得参数。 </span><span class="sxs-lookup"><span data-stu-id="b5b6f-116">The  `AddAppointment` function takes parameters from the **Add Appointment** dialog box that is displayed when you click **Add Appointment** on the **Addins** menu in the MFCMAPI sample application.</span></span> <span data-ttu-id="b5b6f-117">`DisplayAddAppointmentDialog`Appointments.cpp 中的 函数显示对话框，将值从对话框传递给 `AddAppointment` 函数。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-117">The  `DisplayAddAppointmentDialog` function in Appointments.cpp displays the dialog box and passes values from the dialog box to the  `AddAppointment` function.</span></span> <span data-ttu-id="b5b6f-118">`DisplayAddAppointmentDialog`该函数与使用 MAPI 创建约会项目没有直接关系，因此未在此处列出。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-118">The  `DisplayAddAppointmentDialog` function does not relate directly to creating an appointment item using MAPI, so it is not listed here.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b5b6f-119">当您单击"Addins"菜单上的"添加约会"命令时，MFCMAPI 应用程序中的代码并不确保已选择 **"日历**"文件夹。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-119">The code in the MFCMAPI application does not ensure that the **Calendar** folder has been selected when you click the **Add Appointment** command on the **Addins** menu.</span></span> <span data-ttu-id="b5b6f-120">在"日历"文件夹外的文件夹创建约会项目可能会导致未定义的行为。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-120">Creating an appointment item in a folder other than the **Calendar** folder can cause undefined behavior.</span></span> <span data-ttu-id="b5b6f-121">在 MFCMAPI应用程序中使用"添加约会"命令之前，请确保已选择"日历"文件夹。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-121">Make sure that you have selected the **Calendar** folder before using the **Add Appointment** command in the MFCMAPI application.</span></span> 
  
<span data-ttu-id="b5b6f-122">下面  `AddAppointment` 列出了 方法。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-122">The  `AddAppointment` method is listed below.</span></span> <span data-ttu-id="b5b6f-123">请注意，传递给该方法的  _lpFolder_ 参数是指向  `AddAppointment` [IMAPIFolder](imapifolderimapicontainer.md) 接口的指针，该接口表示创建定期约会的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-123">Note that the  _lpFolder_ parameter passed to the  `AddAppointment` method is a pointer to an [IMAPIFolder](imapifolderimapicontainer.md) interface that represents the folder where the recurrent appointment is created.</span></span> <span data-ttu-id="b5b6f-124">在给定表示 **IMAPIFolder** 接口的 _lpFolder_ 参数后，代码将调用 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-124">Given the  _lpFolder_ parameter that represents an **IMAPIFolder** interface, the code calls the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method.</span></span> <span data-ttu-id="b5b6f-125">**CreateMessage** 方法返回成功代码和指向 **指向 IMessage** 接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-125">The **CreateMessage** method returns a success code and a pointer to a pointer to an **IMessage** interface.</span></span> <span data-ttu-id="b5b6f-126">大多数函数代码处理指定属性的工作，以准备调用  `AddAppointment` [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-126">Most of the  `AddAppointment` function code handles the work of specifying properties in preparation for calling the [IMAPIProp::SetProps](imapiprop-setprops.md) method.</span></span> <span data-ttu-id="b5b6f-127">如果 **调用 SetProps** 方法成功，将调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法以将更改提交到存储区并创建新的日历项目。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-127">If the call to the **SetProps** method succeeds, the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method is called to commit the changes to the store and create a new calendar item.</span></span> 
  
<span data-ttu-id="b5b6f-128">该  `AddAppointment` 函数设置许多命名属性。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-128">The  `AddAppointment` function sets a number of named properties.</span></span> <span data-ttu-id="b5b6f-129">有关命名属性及其创建方式的信息，请参阅 Using [MAPI to Create Outlook 2007 Items](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-129">For information about named properties and how they are created, see [Using MAPI to Create Outlook 2007 Items](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx).</span></span> <span data-ttu-id="b5b6f-130">由于约会项目使用的命名属性占用多个属性集，因此在构建参数以传递到 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 方法时必须小心。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-130">Because the named properties used for appointment items occupy multiple property sets, care must be taken when building parameters to pass to the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method.</span></span> 
  
<span data-ttu-id="b5b6f-131">该  `AddAppointment` 函数使用多个帮助程序函数为各种约会相关的属性构建结构。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-131">The  `AddAppointment` function uses several helper functions to build a structure for various appointment-related properties.</span></span> <span data-ttu-id="b5b6f-132">`BuildTimeZoneStruct`和 `BuildTimeZoneDefinition` 帮助程序函数用于构建一个指定与时区相关的属性的结构。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-132">The  `BuildTimeZoneStruct` and  `BuildTimeZoneDefinition` helper functions are used to build a structure that specifies the time-zone-related properties.</span></span> <span data-ttu-id="b5b6f-133">与时区相关的属性为 **dispidTimeZoneStruct** ([PidLidTimeZoneStruct](pidlidtimezonestruct-canonical-property.md)) 、dispidTimeZoneDesc ( [PidLidTimeZoneDescription](pidlidtimezonedescription-canonical-property.md) **) 、dispidApptTZDefRecur** ([PidLidAppointmentTimeZoneDefinitionRecur](pidlidappointmenttimezonedefinitionrecur-canonical-property.md)) ， **dispidApptTZDefStartDisplay** ([PidLidAppointmentTimeZoneDefinitionStartDisplay](pidlidappointmenttimezonedefinitionstartdisplay-canonical-property.md)) 和 **dispidApptTZDefEndDisplay** ([PidLidAppointmentTimeZoneDefinitionEndDisplay](pidlidappointmenttimezonedefinitionenddisplay-canonical-property.md)) ，它们将在 [[MS-OXOCAL] 的相应部分中进行讨论](https://msdn.microsoft.com/library/cc425490%28v=EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-133">The time-zone-related properties are **dispidTimeZoneStruct** ([PidLidTimeZoneStruct](pidlidtimezonestruct-canonical-property.md)), **dispidTimeZoneDesc** ([PidLidTimeZoneDescription](pidlidtimezonedescription-canonical-property.md)), **dispidApptTZDefRecur** ([PidLidAppointmentTimeZoneDefinitionRecur](pidlidappointmenttimezonedefinitionrecur-canonical-property.md)), **dispidApptTZDefStartDisplay** ([PidLidAppointmentTimeZoneDefinitionStartDisplay](pidlidappointmenttimezonedefinitionstartdisplay-canonical-property.md)), and **dispidApptTZDefEndDisplay** ([PidLidAppointmentTimeZoneDefinitionEndDisplay](pidlidappointmenttimezonedefinitionenddisplay-canonical-property.md)), and they are discussed in the corresponding sections of [[MS-OXOCAL]](https://msdn.microsoft.com/library/cc425490%28v=EXCHG.80%29.aspx).</span></span> 

<span data-ttu-id="b5b6f-134">该函数用于构建一个指定  `BuildGlobalObjectID` **LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)) 和 **dispidCleanGlobalObjId** ([PidLidCleanGlobalObjectId](pidlidcleanglobalobjectid-canonical-property.md)) 属性的结构，将在 [[MS-OXOCAL]](https://msdn.microsoft.com/library/cc425490%28v=EXCHG.80%29.aspx)的相应部分中讨论这些属性。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-134">The  `BuildGlobalObjectID` function is used to build a structure that specifies the **LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)) and **dispidCleanGlobalObjId** ([PidLidCleanGlobalObjectId](pidlidcleanglobalobjectid-canonical-property.md)) properties, which are discussed in the corresponding sections of [[MS-OXOCAL]](https://msdn.microsoft.com/library/cc425490%28v=EXCHG.80%29.aspx).</span></span> <span data-ttu-id="b5b6f-135">指定 **dispidApptRecur** 属性的结构是使用  `BuildWeeklyAppointmentRecurrencePattern` 函数构建的。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-135">The structure that specifies the **dispidApptRecur** property is built using the  `BuildWeeklyAppointmentRecurrencePattern` function.</span></span> 

<span data-ttu-id="b5b6f-136">有关函数构建的结构的信息，请参阅  `BuildWeeklyAppointmentRecurrencePattern` [PidLidAppointmentRecur 规范属性](pidlidappointmentrecur-canonical-property.md)。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-136">For information about the structure built by the  `BuildWeeklyAppointmentRecurrencePattern` function, see [PidLidAppointmentRecur Canonical Property](pidlidappointmentrecur-canonical-property.md).</span></span> <span data-ttu-id="b5b6f-137">请注意，虽然有各种约会定期模式，但函数仅生成每周约会  `BuildWeeklyAppointmentRecurrencePattern` 定期模式。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-137">Note that while a large variety of appointment recurrence patterns are possible, the  `BuildWeeklyAppointmentRecurrencePattern` function only builds a weekly appointment recurrence pattern.</span></span> <span data-ttu-id="b5b6f-138">它还使用若干硬编码值，如日历类型 (公历) 、星期 (星期日) 的第一天以及经过修改或删除的实例数 (无) 。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-138">It also uses several hard-coded values, such as the calendar type (Gregorian), the first day of the week (Sunday), and number of modified or deleted instances (none).</span></span> <span data-ttu-id="b5b6f-139">创建函数的更定期模式约会需要接受这些类型的变量作为参数。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-139">A more general purpose appointment recurrence pattern creation function would need to accept these sorts of variables as parameters.</span></span> 
  
<span data-ttu-id="b5b6f-140">以下是 函数的完整  `AddAppointment` 列表。</span><span class="sxs-lookup"><span data-stu-id="b5b6f-140">The following is the complete listing of the  `AddAppointment` function.</span></span> 
  
```cpp
HRESULT AddAppointment(LPMAPIFOLDER lpFolder,
               SYSTEMTIME* lpstStartDateLocal, // PidLidAppointmentRecur
               SYSTEMTIME* lpstEndDateLocal, // PidLidAppointmentRecur
               SYSTEMTIME* lpstStartFirstUST, // PidLidAppointmentStartWhole, PidLidCommonStart, PR_START_DATE
               SYSTEMTIME* lpstEndFirstUST, // PidLidAppointmentEndWhole, PidLidCommonEnd, PR_END_DATE
               SYSTEMTIME* lpszClipStartUST, // PidLidClipStart
               SYSTEMTIME* lpstClipEndUST, // PidLidClipEnd
               SYSTEMTIME* lpstFirstDOW, // PidLidAppointmentRecur
               DWORD dwStartOffsetLocal, // PidLidAppointmentRecur
               DWORD dwEndOffsetLocal, // PidLidAppointmentRecur
               DWORD dwPeriod, // PidLidAppointmentRecur
               DWORD dwOccurrenceCount, // PidLidAppointmentRecur
               DWORD dwPatternTypeSpecific, // PidLidAppointmentRecur
               ULONG ulDuration, // PidLidAppointmentDuration
               LPWSTR szSubject, // PR_SUBJECT_W
               LPWSTR szLocation, // PidLidLocation
               LPWSTR szPattern) // PidLidRecurrencePattern
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
      MAPINAMEID  rgnmid[ulAppointmentProps];
      LPMAPINAMEID rgpnmid[ulAppointmentProps];
      LPSPropTagArray lpNamedPropTags = NULL;
      ULONG i = 0;
      for (i = 0 ; i < ulAppointmentProps ; i++)
      {
         if (i < ulFirstMeetingProp)
            rgnmid[i].lpguid = (LPGUID)&PSETID_Appointment;
         else if (i < ulFirstCommonProp)
            rgnmid[i].lpguid = (LPGUID)&PSETID_Meeting;
         else
            rgnmid[i].lpguid = (LPGUID)&PSETID_Common;
         rgnmid[i].ulKind = MNID_ID;
         rgnmid[i].Kind.lID = aulAppointmentProps[i];
         rgpnmid[i] = &rgnmid[i];
      }
      hRes = lpFolder->GetIDsFromNames(
         ulAppointmentProps,
         (LPMAPINAMEID*) &rgpnmid,
         NULL,
         &lpNamedPropTags);
      if (SUCCEEDED(hRes) && lpNamedPropTags)
      {
      // Because the properties to be set are known in advance, 
      // most of the structures involved can be statically declared 
      // to minimize expensive MAPIAllocateBuffer calls.
         SPropValue spvProps[NUM_PROPS] = {0};
         spvProps[p_PidLidAppointmentSequence].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidAppointmentSequence],PT_LONG);
         spvProps[p_PidLidBusyStatus].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidBusyStatus],PT_LONG);
         spvProps[p_PidLidLocation].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidLocation],PT_UNICODE);
         spvProps[p_PidLidAppointmentStartWhole].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidAppointmentStartWhole],PT_SYSTIME);
         spvProps[p_PidLidAppointmentEndWhole].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidAppointmentEndWhole],PT_SYSTIME);
         spvProps[p_PidLidAppointmentDuration].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidAppointmentDuration],PT_LONG);
         spvProps[p_PidLidAppointmentColor].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidAppointmentColor],PT_LONG);
         spvProps[p_PidLidResponseStatus].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidResponseStatus],PT_LONG);
         spvProps[p_PidLidRecurring].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidRecurring],PT_BOOLEAN);
         spvProps[p_PidLidClipStart].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidClipStart],PT_SYSTIME);
         spvProps[p_PidLidClipEnd].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidClipEnd],PT_SYSTIME);
         spvProps[p_PidLidTimeZoneStruct].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTimeZoneStruct],PT_BINARY);
         spvProps[p_PidLidTimeZoneDescription].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidTimeZoneDescription],PT_UNICODE);
         spvProps[p_PidLidAppointmentTimeZoneDefinitionRecur].ulPropTag
           = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidAppointmentTimeZoneDefinitionRecur],
           PT_BINARY);
         spvProps[p_PidLidAppointmentTimeZoneDefinitionStartDisplay].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidAppointmentTimeZoneDefinitionStartDisplay],
            PT_BINARY);
         spvProps[p_PidLidAppointmentTimeZoneDefinitionEndDisplay].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidAppointmentTimeZoneDefinitionEndDisplay],
            PT_BINARY);
         spvProps[p_PidLidAppointmentRecur].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidAppointmentRecur],PT_BINARY);
         spvProps[p_PidLidRecurrenceType].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidRecurrenceType],PT_LONG);
         spvProps[p_PidLidRecurrencePattern].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidRecurrencePattern],PT_UNICODE);
         spvProps[p_PidLidIsRecurring].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidIsRecurring],PT_BOOLEAN);
         spvProps[p_PidLidGlobalObjectId].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidGlobalObjectId],PT_BINARY);
         spvProps[p_PidLidCleanGlobalObjectId].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidCleanGlobalObjectId],PT_BINARY);
         spvProps[p_PidLidCommonStart].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidCommonStart],PT_SYSTIME);
         spvProps[p_PidLidCommonEnd].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidCommonEnd],PT_SYSTIME);
         spvProps[p_PidLidSideEffects].ulPropTag
            = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[p_PidLidSideEffects],PT_LONG);
         spvProps[p_PR_SUBJECT_W].ulPropTag          = PR_SUBJECT_W;
         spvProps[p_PR_START_DATE].ulPropTag         = PR_START_DATE;
         spvProps[p_PR_END_DATE].ulPropTag           = PR_END_DATE;
         spvProps[p_PR_MESSAGE_CLASS_W].ulPropTag    = PR_MESSAGE_CLASS_W;
         spvProps[p_PR_ICON_INDEX].ulPropTag         = PR_ICON_INDEX;
         spvProps[p_PR_CONVERSATION_INDEX].ulPropTag   = PR_CONVERSATION_INDEX;
         spvProps[p_PR_MESSAGE_FLAGS].ulPropTag      = PR_MESSAGE_FLAGS;
         spvProps[p_PidLidAppointmentSequence].Value.l = 0;
         spvProps[p_PidLidBusyStatus].Value.l = olBusy;
         spvProps[p_PidLidLocation].Value.lpszW = szLocation;
         SystemTimeToFileTime(lpstStartFirstUST,&spvProps[p_PidLidAppointmentStartWhole].Value.ft);
         SystemTimeToFileTime(lpstEndFirstUST,&spvProps[p_PidLidAppointmentEndWhole].Value.ft);
         spvProps[p_PidLidAppointmentDuration].Value.l = ulDuration;
         spvProps[p_PidLidAppointmentColor].Value.l = 0; // No color
         spvProps[p_PidLidResponseStatus].Value.l = respNone;
         spvProps[p_PidLidRecurring].Value.b = true;
         SystemTimeToFileTime(lpszClipStartUST,&spvProps[p_PidLidClipStart].Value.ft);
         SystemTimeToFileTime(lpstClipEndUST,&spvProps[p_PidLidClipEnd].Value.ft);
         SYSTEMTIME stStandard = {0};
         stStandard.wMonth = 0xB;
         stStandard.wDay = 0x1;
         stStandard.wHour = 0x2;
         SYSTEMTIME stDaylight = {0};
         stDaylight.wMonth = 0x3;
         stDaylight.wDay = 0x2;
         stDaylight.wHour = 0x2;
         hRes = BuildTimeZoneStruct(
            300,
            0,
            (DWORD)-60,
            &stStandard,
            &stDaylight,
            &spvProps[p_PidLidTimeZoneStruct].Value.bin.cb,
            &spvProps[p_PidLidTimeZoneStruct].Value.bin.lpb);
         spvProps[p_PidLidTimeZoneDescription].Value.lpszW = L"(GMT-05:00) Eastern Time (US & Canada)";
         SYSTEMTIME stRule1Standard = {0};
         stRule1Standard.wMonth = 0xA;
         stRule1Standard.wDay = 0x5;
         stRule1Standard.wHour = 0x2;
         SYSTEMTIME stRule1Daylight = {0};
         stRule1Daylight.wMonth = 0x4;
         stRule1Daylight.wDay = 0x1;
         stRule1Daylight.wHour = 0x2;
         if (SUCCEEDED(hRes)) hRes = BuildTimeZoneDefinition(
            L"Eastern Standard Time",
            0, // TZRule Flags
            2006, // wYear
            300, // lbias
            0, // lStandardBias,
            (DWORD)-60, // lDaylightBias,
            &stRule1Standard, // stStandardDate
            &stRule1Daylight, // stDaylightDate
            TZRULE_FLAG_EFFECTIVE_TZREG, // TZRule Flags
            2007, // wYear
            300, // lbias
            0, // lStandardBias,
            (DWORD)-60, // lDaylightBias,
            &stStandard, // stStandardDate
            &stDaylight, // stDaylightDate
            &spvProps[p_PidLidAppointmentTimeZoneDefinitionRecur].Value.bin.cb,
            &spvProps[p_PidLidAppointmentTimeZoneDefinitionRecur].Value.bin.lpb);
         spvProps[p_PidLidAppointmentTimeZoneDefinitionStartDisplay].Value.bin.cb
            = spvProps[p_PidLidAppointmentTimeZoneDefinitionRecur].Value.bin.cb;
         spvProps[p_PidLidAppointmentTimeZoneDefinitionStartDisplay].Value.bin.lpb
            = spvProps[p_PidLidAppointmentTimeZoneDefinitionRecur].Value.bin.lpb;
         spvProps[p_PidLidAppointmentTimeZoneDefinitionEndDisplay].Value.bin.cb
            = spvProps[p_PidLidAppointmentTimeZoneDefinitionRecur].Value.bin.cb;
         spvProps[p_PidLidAppointmentTimeZoneDefinitionEndDisplay].Value.bin.lpb
            = spvProps[p_PidLidAppointmentTimeZoneDefinitionRecur].Value.bin.lpb;
         if (SUCCEEDED(hRes)) hRes = BuildWeeklyAppointmentRecurrencePattern(
            lpstStartDateLocal,
            lpstEndDateLocal,
            lpstFirstDOW,
            dwStartOffsetLocal,
            dwEndOffsetLocal,
            dwPeriod,
            dwOccurrenceCount,
            dwPatternTypeSpecific,
            &spvProps[p_PidLidAppointmentRecur].Value.bin.cb,
            &spvProps[p_PidLidAppointmentRecur].Value.bin.lpb);
         spvProps[p_PidLidRecurrenceType].Value.l = rectypeWeekly;
         spvProps[p_PidLidRecurrencePattern].Value.lpszW = szPattern;
         spvProps[p_PidLidIsRecurring].Value.b = true;
         if (SUCCEEDED(hRes)) hRes = BuildGlobalObjectId(
            &spvProps[p_PidLidGlobalObjectId].Value.bin.cb,
            &spvProps[p_PidLidGlobalObjectId].Value.bin.lpb);
         spvProps[p_PidLidCleanGlobalObjectId].Value.bin.cb  = spvProps[p_PidLidGlobalObjectId].Value.bin.cb;
         spvProps[p_PidLidCleanGlobalObjectId].Value.bin.lpb = spvProps[p_PidLidGlobalObjectId].Value.bin.lpb;
         SystemTimeToFileTime(lpstStartFirstUST,&spvProps[p_PidLidCommonStart].Value.ft);
         SystemTimeToFileTime(lpstEndFirstUST,&spvProps[p_PidLidCommonEnd].Value.ft);
         spvProps[p_PidLidSideEffects].Value.l
            = seOpenToDelete | seOpenToCopy | seOpenToMove | seCoerceToInbox | seOpenForCtxMenu;
         spvProps[p_PR_SUBJECT_W].Value.lpszW = szSubject;
         SystemTimeToFileTime(lpstStartFirstUST,&spvProps[p_PR_START_DATE].Value.ft);
         SystemTimeToFileTime(lpstEndFirstUST,&spvProps[p_PR_END_DATE].Value.ft);
         spvProps[p_PR_MESSAGE_CLASS_W].Value.lpszW = L"IPM.Appointment";
         spvProps[p_PR_ICON_INDEX].Value.l = 0x00000401; // Recurring Appointment
         if (SUCCEEDED(hRes)) hRes = BuildConversationIndex(
            &spvProps[p_PR_CONVERSATION_INDEX].Value.bin.cb,
            &spvProps[p_PR_CONVERSATION_INDEX].Value.bin.lpb);
         spvProps[p_PR_MESSAGE_FLAGS].Value.l = MSGFLAG_READ;
         if (SUCCEEDED(hRes)) hRes = lpMessage->SetProps(NUM_PROPS, spvProps, NULL);
         if (SUCCEEDED(hRes))
         {
            hRes = lpMessage->SaveChanges(FORCE_SAVE);
         }
         if (spvProps[p_PidLidTimeZoneStruct].Value.bin.lpb)
            delete[] spvProps[p_PidLidTimeZoneStruct].Value.bin.lpb;
         if (spvProps[p_PidLidAppointmentTimeZoneDefinitionRecur].Value.bin.lpb)
            delete[] spvProps[p_PidLidAppointmentTimeZoneDefinitionRecur].Value.bin.lpb;
         // Do not delete p_PidLidAppointmentTimeZoneDefinitionStartDisplay, 
         // it was borrowed from p_PidLidAppointmentTimeZoneDefinitionStartDisplay
         // Do not delete p_PidLidAppointmentTimeZoneDefinitionEndDisplay, 
         // it was borrowed from p_PidLidAppointmentTimeZoneDefinitionStartDisplay
         if (spvProps[p_PidLidAppointmentRecur].Value.bin.lpb)
            delete[] spvProps[p_PidLidAppointmentRecur].Value.bin.lpb;
         if (spvProps[p_PidLidGlobalObjectId].Value.bin.lpb)
            delete[] spvProps[p_PidLidGlobalObjectId].Value.bin.lpb;
         // Do not delete p_PidLidCleanGlobalObjectId, it was borrowed from p_PidLidGlobalObjectId
         if (spvProps[p_PR_CONVERSATION_INDEX].Value.bin.lpb)
            delete[] spvProps[p_PR_CONVERSATION_INDEX].Value.bin.lpb;
      }
      MAPIFreeBuffer(lpNamedPropTags);
   }
   if (lpMessage) lpMessage->Release();
   return hRes;
}

```

## <a name="see-also"></a><span data-ttu-id="b5b6f-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5b6f-141">See also</span></span>

- [<span data-ttu-id="b5b6f-142">使用 MAPI 创建Outlook 2007 项</span><span class="sxs-lookup"><span data-stu-id="b5b6f-142">Using MAPI to Create Outlook 2007 Items</span></span>](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)

