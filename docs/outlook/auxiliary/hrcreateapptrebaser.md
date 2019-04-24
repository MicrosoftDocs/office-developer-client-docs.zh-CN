---
title: HrCreateApptRebaser
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 265028b7-a583-f6ba-0214-5a4322f98f35
description: 初始化 IOlkApptRebaser 对象, 以便在 Outlook 日历中的重定约会中使用。
ms.openlocfilehash: 33ad47d59ee2ca1b2461f730494f3466b9f8b54a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317610"
---
# <a name="hrcreateapptrebaser"></a><span data-ttu-id="aed40-103">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="aed40-103">HrCreateApptRebaser</span></span>

<span data-ttu-id="aed40-104">初始化[IOlkApptRebaser](iolkapptrebaser.md)对象, 以便在 Outlook 日历中的重定约会中使用。</span><span class="sxs-lookup"><span data-stu-id="aed40-104">Initializes an [IOlkApptRebaser](iolkapptrebaser.md) object for use in rebasing appointments in Outlook calendars.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="aed40-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="aed40-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="aed40-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="aed40-106">Header file:</span></span>  <br/> |<span data-ttu-id="aed40-107">tzmovelib。h</span><span class="sxs-lookup"><span data-stu-id="aed40-107">tzmovelib.h</span></span>  <br/> |
|<span data-ttu-id="aed40-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="aed40-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="aed40-109">tzmovelib。h</span><span class="sxs-lookup"><span data-stu-id="aed40-109">tzmovelib.dll</span></span>  <br/> |
|<span data-ttu-id="aed40-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="aed40-110">Called by:</span></span>  <br/> |<span data-ttu-id="aed40-111">MAPI 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="aed40-111">MAPI client applications</span></span>  <br/> |
|<span data-ttu-id="aed40-112">指针类型:</span><span class="sxs-lookup"><span data-stu-id="aed40-112">Pointer type:</span></span>  <br/> |<span data-ttu-id="aed40-113">**LPHRCREATEAPPTREBASER**</span><span class="sxs-lookup"><span data-stu-id="aed40-113">**LPHRCREATEAPPTREBASER**</span></span> <br/> |
|<span data-ttu-id="aed40-114">DLL 入口点:</span><span class="sxs-lookup"><span data-stu-id="aed40-114">DLL entry point:</span></span>  <br/> |<span data-ttu-id="aed40-115">**HrCreateApptRebaser @ 44**</span><span class="sxs-lookup"><span data-stu-id="aed40-115">**HrCreateApptRebaser@44**</span></span> <br/> |
   
```cpp
HRESULT HrCreateApptRebaser(  
    ULONG ulFlags, 
    IMAPISession *pSession, 
    IMsgStore *pCalendarMsgStore, 
    IMAPIFolder *pCalendarFolder, 
    LPCWSTR pwszUpdatePrefix, 
    const FILETIME *pftInstallDateUTC, 
    LONG lExpansionDepth, 
    const TZDEFINITION *pTZTo, 
    const TZDEFINITION *pTZMissing, 
    MAPIERROR **ppError, 
    IOlkApptRebaser **ppApptRebase); 

```

## <a name="parameters"></a><span data-ttu-id="aed40-116">参数</span><span class="sxs-lookup"><span data-stu-id="aed40-116">Parameters</span></span>

<span data-ttu-id="aed40-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="aed40-117">_ulFlags_</span></span>
  
> <span data-ttu-id="aed40-118">[中]所必需。</span><span class="sxs-lookup"><span data-stu-id="aed40-118">[in] Required.</span></span> <span data-ttu-id="aed40-119">用于控制如何执行重定的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="aed40-119">A bitmask of flags used to control how rebasing is performed.</span></span> <span data-ttu-id="aed40-120">可以在 tzmovelib.h 中设置和定义以下标志:</span><span class="sxs-lookup"><span data-stu-id="aed40-120">The following flags can be set and are defined in tzmovelib.h:</span></span>
    
   - <span data-ttu-id="aed40-121">**REBASE_FLAG_UPDATE_ORGANIZED_MEETINGS** —用户是会议组织者的约会项目是 rebased。</span><span class="sxs-lookup"><span data-stu-id="aed40-121">**REBASE_FLAG_UPDATE_ORGANIZED_MEETINGS** —Appointment items in which the user is the meeting organizer are rebased.</span></span> <span data-ttu-id="aed40-122">请注意, 默认情况下, 这会导致 Outlook 向任何正在 rebased 的会议的所有与会者发送会议更新。</span><span class="sxs-lookup"><span data-stu-id="aed40-122">Note that by default, this causes Outlook to send meeting updates to all attendees of any meeting being rebased.</span></span> <span data-ttu-id="aed40-123">您可以将此标志与**REBASE_FLAG_FORCE_NO_EX_UPDATES**或**REBASE_FLAG_FORCE_NO_UPDATES**结合使用, 以更改会议更新的处理方式。</span><span class="sxs-lookup"><span data-stu-id="aed40-123">You can combine this flag with either **REBASE_FLAG_FORCE_NO_EX_UPDATES** or **REBASE_FLAG_FORCE_NO_UPDATES** to change how meeting updates are handled.</span></span> 
    
   - <span data-ttu-id="aed40-124">**REBASE_FLAG_UPDATE_UNMARKED** —更新尚未使用时区标记的约会项目。</span><span class="sxs-lookup"><span data-stu-id="aed40-124">**REBASE_FLAG_UPDATE_UNMARKED** —Update appointment items that have not been marked with a time zone.</span></span> <span data-ttu-id="aed40-125">如果指定此标志, 则将*pTZMissing*值用作为没有时区数据的所有项目创建项目的时区。</span><span class="sxs-lookup"><span data-stu-id="aed40-125">If this flag is specified, the  *pTZMissing*  value is used as the time zone that an item is created in for all items that do not have time zone data.</span></span> 
    
   - <span data-ttu-id="aed40-126">**REBASE_FLAG_UPDATE_ONLYRECURRING** —仅更新定期约会项目。</span><span class="sxs-lookup"><span data-stu-id="aed40-126">**REBASE_FLAG_UPDATE_ONLYRECURRING** —Update only recurring appointment items.</span></span> 
    
   - <span data-ttu-id="aed40-127">**REBASE_FLAG_NO_UI** —不显示任何用户界面 (UI), 包括在打开邮件存储时通常会显示的登录对话框。</span><span class="sxs-lookup"><span data-stu-id="aed40-127">**REBASE_FLAG_NO_UI** —Do not show any user interface (UI), including logon dialog boxes generally displayed when opening a message store.</span></span> 
    
   - <span data-ttu-id="aed40-128">**REBASE_FLAG_UPDATE_MINIMIZEAPPTS** —不变基发生在过去的约会项。</span><span class="sxs-lookup"><span data-stu-id="aed40-128">**REBASE_FLAG_UPDATE_MINIMIZEAPPTS** —Do not rebase appointment items that occur in the past.</span></span> 
    
   - <span data-ttu-id="aed40-129">**REBASE_FLAG_FORCE_REBASE** —不检查组织者的重定决策, 但可变基约会项, 其中用户是与会者。</span><span class="sxs-lookup"><span data-stu-id="aed40-129">**REBASE_FLAG_FORCE_REBASE** —Do not check the organizer for rebasing decisions, but rebase appointment items in which the user is an attendee.</span></span> 
    
   - <span data-ttu-id="aed40-130">**REBASE_FLAG_FORCE_NO_EX_UPDATES** —仅当用户是组织者且收件人未连接到 Exchange 服务器时才发送更新。</span><span class="sxs-lookup"><span data-stu-id="aed40-130">**REBASE_FLAG_FORCE_NO_EX_UPDATES** —Send updates only if the user is the organizer and recipient is not connected to an Exchange Server.</span></span> 
    
   - <span data-ttu-id="aed40-131">**REBASE_FLAG_FORCE_NO_UPDATES** —从不发送更新。</span><span class="sxs-lookup"><span data-stu-id="aed40-131">**REBASE_FLAG_FORCE_NO_UPDATES** —Never send updates.</span></span> 
    
   - <span data-ttu-id="aed40-132">**REBASE_FLAG_ONLY_CREATED_PRE_PATCH** —仅在应用修补程序之前创建的单实例约会项目变基。</span><span class="sxs-lookup"><span data-stu-id="aed40-132">**REBASE_FLAG_ONLY_CREATED_PRE_PATCH** —Rebase only single-instance appointment items created before the patch was applied.</span></span> 
    
   - <span data-ttu-id="aed40-133">**REBASE_FLAG_REPORTING_MODE** —实际上不会变基, 只是报告将被 rebased 的约会项目。</span><span class="sxs-lookup"><span data-stu-id="aed40-133">**REBASE_FLAG_REPORTING_MODE** —Do not actually rebase, just report appointment items that would be rebased.</span></span> 
    
   - <span data-ttu-id="aed40-134">**REBASE_FLAG_SEND_RESOURCE_UPDATES** —将会议更新发送到资源。</span><span class="sxs-lookup"><span data-stu-id="aed40-134">**REBASE_FLAG_SEND_RESOURCE_UPDATES** —Send meeting updates to resources.</span></span> 
    
<span data-ttu-id="aed40-135">_pSession_</span><span class="sxs-lookup"><span data-stu-id="aed40-135">_pSession_</span></span>
  
> <span data-ttu-id="aed40-136">[中]所必需。</span><span class="sxs-lookup"><span data-stu-id="aed40-136">[in] Required.</span></span> <span data-ttu-id="aed40-137">指向 MAPI 会话接口的指针。</span><span class="sxs-lookup"><span data-stu-id="aed40-137">A pointer to a MAPI session interface.</span></span>
    
<span data-ttu-id="aed40-138">_pCalendarMsgStore_</span><span class="sxs-lookup"><span data-stu-id="aed40-138">_pCalendarMsgStore_</span></span>
  
> <span data-ttu-id="aed40-139">[中]所必需。</span><span class="sxs-lookup"><span data-stu-id="aed40-139">[in] Required.</span></span> <span data-ttu-id="aed40-140">指向邮件存储区的指针, 该存储区包含要 rebased 的约会项目。</span><span class="sxs-lookup"><span data-stu-id="aed40-140">A pointer to a message store containing appointment items to be rebased.</span></span>
    
<span data-ttu-id="aed40-141">_pCalendarFolder_</span><span class="sxs-lookup"><span data-stu-id="aed40-141">_pCalendarFolder_</span></span>
  
> <span data-ttu-id="aed40-142">[中]所必需。</span><span class="sxs-lookup"><span data-stu-id="aed40-142">[in] Required.</span></span> <span data-ttu-id="aed40-143">指向包含要 rebased 的约会项目的 "日历" 文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="aed40-143">A pointer to a calendar folder containing appointment items to be rebased.</span></span>
    
<span data-ttu-id="aed40-144">_pwszUpdatePrefix_</span><span class="sxs-lookup"><span data-stu-id="aed40-144">_pwszUpdatePrefix_</span></span>
  
> <span data-ttu-id="aed40-145">[中]可选。</span><span class="sxs-lookup"><span data-stu-id="aed40-145">[in] Optional.</span></span> <span data-ttu-id="aed40-146">指向包含前缀的字符串的指针, 该字符串将预置在会议请求上。</span><span class="sxs-lookup"><span data-stu-id="aed40-146">A pointer to a string containing the prefix to be prepended on meeting requests.</span></span> <span data-ttu-id="aed40-147">可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="aed40-147">May be NULL.</span></span>
    
<span data-ttu-id="aed40-148">_pftInstallDateUTC_</span><span class="sxs-lookup"><span data-stu-id="aed40-148">_pftInstallDateUTC_</span></span>
  
> <span data-ttu-id="aed40-149">[中]可选。</span><span class="sxs-lookup"><span data-stu-id="aed40-149">[in] Optional.</span></span> <span data-ttu-id="aed40-150">时区修补程序安装日期。</span><span class="sxs-lookup"><span data-stu-id="aed40-150">The time zone patch install date.</span></span> <span data-ttu-id="aed40-151">仅在设置**REBASE_FLAG_ONLY_CREATED_PRE_PATCH**标志时使用。</span><span class="sxs-lookup"><span data-stu-id="aed40-151">Used only if the **REBASE_FLAG_ONLY_CREATED_PRE_PATCH** flag is set.</span></span> 
    
<span data-ttu-id="aed40-152">_IExpansionDepth_</span><span class="sxs-lookup"><span data-stu-id="aed40-152">_IExpansionDepth_</span></span>
  
> <span data-ttu-id="aed40-153">[中]可选。</span><span class="sxs-lookup"><span data-stu-id="aed40-153">[in] Optional.</span></span> <span data-ttu-id="aed40-154">扩展通讯组列表以排除连接到 Exchange Server 的收件人时的扩展深度。</span><span class="sxs-lookup"><span data-stu-id="aed40-154">The expansion depth when expanding distribution lists to exclude recipients connected to Exchange Server.</span></span> <span data-ttu-id="aed40-155">仅在设置**REBASE_FLAG_FORCE_NO_EX_UPDATES**标志时使用。</span><span class="sxs-lookup"><span data-stu-id="aed40-155">Only used if the **REBASE_FLAG_FORCE_NO_EX_UPDATES** flag is set.</span></span> 
    
<span data-ttu-id="aed40-156">_pTZTo_</span><span class="sxs-lookup"><span data-stu-id="aed40-156">_pTZTo_</span></span>
  
> <span data-ttu-id="aed40-157">[中]所必需。</span><span class="sxs-lookup"><span data-stu-id="aed40-157">[in] Required.</span></span> <span data-ttu-id="aed40-158">指向描述要 rebased 的时区的**TZDEFINITION**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="aed40-158">A pointer to a **TZDEFINITION** structure describing the time zone to be rebased to.</span></span> <span data-ttu-id="aed40-159">**TZDEFINITION**是在 tzmovelib.h 中定义的。</span><span class="sxs-lookup"><span data-stu-id="aed40-159">**TZDEFINITION** is defined in tzmovelib.</span></span> 
    
<span data-ttu-id="aed40-160">pTZMissing</span><span class="sxs-lookup"><span data-stu-id="aed40-160">pTZMissing</span></span>
  
> <span data-ttu-id="aed40-161">[中]所必需。</span><span class="sxs-lookup"><span data-stu-id="aed40-161">[in] Required.</span></span> <span data-ttu-id="aed40-162">一个指向**TZDEFINITION**结构的指针, 该结构描述在不标记某一项的时区信息时要假定的时区。</span><span class="sxs-lookup"><span data-stu-id="aed40-162">A pointer to a **TZDEFINITION** structure describing the time zone to be assumed if time zone information is not stamped on an item.</span></span> <span data-ttu-id="aed40-163">不得为 NULL, 但仅在设置了**REBASE_FLAG_UPDATE_UNMARKED**标志的情况下使用。</span><span class="sxs-lookup"><span data-stu-id="aed40-163">Must not be NULL, but only used if the **REBASE_FLAG_UPDATE_UNMARKED** flag is set.</span></span> 
    
<span data-ttu-id="aed40-164">_ppError_</span><span class="sxs-lookup"><span data-stu-id="aed40-164">_ppError_</span></span>
  
> <span data-ttu-id="aed40-165">排除指向包含错误的版本、组件和上下文信息的**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="aed40-165">[out] A pointer to a pointer to a **MAPIERROR** structure containing version, component, and context information for the error.</span></span> <span data-ttu-id="aed40-166">如果不需要任何扩展的错误信息, 则可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="aed40-166">Can be NULL if no extended error information is desired.</span></span> <span data-ttu-id="aed40-167">使用[MAPIFreeBuffer](https://msdn.microsoft.com/library/9412594f-8acc-4c7e-a668-4ec1da0ad9cf%28Office.15%29.aspx)免费。</span><span class="sxs-lookup"><span data-stu-id="aed40-167">Free with [MAPIFreeBuffer](https://msdn.microsoft.com/library/9412594f-8acc-4c7e-a668-4ec1da0ad9cf%28Office.15%29.aspx).</span></span> 
    
<span data-ttu-id="aed40-168">_ppApptRebase_</span><span class="sxs-lookup"><span data-stu-id="aed40-168">_ppApptRebase_</span></span>
  
> <span data-ttu-id="aed40-169">排除指向返回的**IOlkApptRebaser**接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="aed40-169">[out] A pointer to a pointer to the returned **IOlkApptRebaser** interface.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="aed40-170">返回值</span><span class="sxs-lookup"><span data-stu-id="aed40-170">Return values</span></span>

<span data-ttu-id="aed40-171">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="aed40-171">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="aed40-172">注解</span><span class="sxs-lookup"><span data-stu-id="aed40-172">Remarks</span></span>

<span data-ttu-id="aed40-173">使用[GetProcAddress](https://msdn.microsoft.com/library/a0d7fc09-f888-4f46-a571-d3719a627597%28Office.15%29.aspx)在 tzmovelib.h 中查找此函数的地址时, 请指定**HrCreateApptRebaser @ 44**作为过程名称。</span><span class="sxs-lookup"><span data-stu-id="aed40-173">When using [GetProcAddress](https://msdn.microsoft.com/library/a0d7fc09-f888-4f46-a571-d3719a627597%28Office.15%29.aspx) to look for the address of this function in tzmovelib.dll, specify **HrCreateApptRebaser@44** as the procedure name.</span></span> <span data-ttu-id="aed40-174">并不是所有的标志相互组合。</span><span class="sxs-lookup"><span data-stu-id="aed40-174">Not all of the flags are valid in combination with each other.</span></span> 
  
<span data-ttu-id="aed40-175">有关各种选项的详细信息, 请参阅 KB 931667 中的 "Outlook 时区数据更新工具的命令行选项的术语表" 一节[: 如何使用 Microsoft Office Outlook 的时区数据更新工具来解决时区更改](https://support.microsoft.com/kb/931667/en-us)。</span><span class="sxs-lookup"><span data-stu-id="aed40-175">For more information about the various options, see the section "Glossary of command-line options for the Outlook Time Zone Data Update tool" in [KB 931667: How to address time zone changes by using the Time Zone Data Update Tool for Microsoft Office Outlook](https://support.microsoft.com/kb/931667/en-us).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aed40-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aed40-176">See also</span></span>

- [<span data-ttu-id="aed40-177">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="aed40-177">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

