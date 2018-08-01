---
title: HrCreateApptRebaser
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 265028b7-a583-f6ba-0214-5a4322f98f35
description: 初始化 IOlkApptRebaser 对象用于在 Outlook 日历中定位约会。
ms.openlocfilehash: fec0407c3f129290d03f9b26b0b3f072a229b003
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774199"
---
# <a name="hrcreateapptrebaser"></a><span data-ttu-id="8f9d2-103">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="8f9d2-103">HrCreateApptRebaser</span></span>

<span data-ttu-id="8f9d2-104">初始化[IOlkApptRebaser](iolkapptrebaser.md)对象用于在 Outlook 日历中定位约会。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-104">Initializes an [IOlkApptRebaser](iolkapptrebaser.md) object for use in rebasing appointments in Outlook calendars.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="8f9d2-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="8f9d2-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8f9d2-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="8f9d2-106">Header file:</span></span>  <br/> |<span data-ttu-id="8f9d2-107">tzmovelib.h</span><span class="sxs-lookup"><span data-stu-id="8f9d2-107">tzmovelib.h</span></span>  <br/> |
|<span data-ttu-id="8f9d2-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="8f9d2-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="8f9d2-109">tzmovelib.dll</span><span class="sxs-lookup"><span data-stu-id="8f9d2-109">tzmovelib.dll</span></span>  <br/> |
|<span data-ttu-id="8f9d2-110">调用：</span><span class="sxs-lookup"><span data-stu-id="8f9d2-110">Called by:</span></span>  <br/> |<span data-ttu-id="8f9d2-111">MAPI 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="8f9d2-111">MAPI client applications</span></span>  <br/> |
|<span data-ttu-id="8f9d2-112">指针类型：</span><span class="sxs-lookup"><span data-stu-id="8f9d2-112">Pointer type:</span></span>  <br/> |<span data-ttu-id="8f9d2-113">**LPHRCREATEAPPTREBASER**</span><span class="sxs-lookup"><span data-stu-id="8f9d2-113">**LPHRCREATEAPPTREBASER**</span></span> <br/> |
|<span data-ttu-id="8f9d2-114">DLL 入口点：</span><span class="sxs-lookup"><span data-stu-id="8f9d2-114">DLL entry point:</span></span>  <br/> |<span data-ttu-id="8f9d2-115">**HrCreateApptRebaser@44**</span><span class="sxs-lookup"><span data-stu-id="8f9d2-115">**HrCreateApptRebaser@44**</span></span> <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="8f9d2-116">参数</span><span class="sxs-lookup"><span data-stu-id="8f9d2-116">Parameters</span></span>

<span data-ttu-id="8f9d2-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="8f9d2-117">_ulFlags_</span></span>
  
> <span data-ttu-id="8f9d2-118">[中]所必需。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-118">[in] Required.</span></span> <span data-ttu-id="8f9d2-119">用于控制定位的执行方式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-119">A bitmask of flags used to control how rebasing is performed.</span></span> <span data-ttu-id="8f9d2-120">以下标志可以设置，并在 tzmovelib.h 中定义：</span><span class="sxs-lookup"><span data-stu-id="8f9d2-120">The following flags can be set and are defined in tzmovelib.h:</span></span>
    
   - <span data-ttu-id="8f9d2-121">**REBASE_FLAG_UPDATE_ORGANIZED_MEETINGS** — 包含用户的会议组织者的约会项目重新设定基址。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-121">**REBASE_FLAG_UPDATE_ORGANIZED_MEETINGS** —Appointment items in which the user is the meeting organizer are rebased.</span></span> <span data-ttu-id="8f9d2-122">请注意，默认情况下，这会导致 Outlook 发送给所有与会者正在重新设定基址任何会议的会议更新。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-122">Note that by default, this causes Outlook to send meeting updates to all attendees of any meeting being rebased.</span></span> <span data-ttu-id="8f9d2-123">您可以将此标志与**REBASE_FLAG_FORCE_NO_EX_UPDATES**或**REBASE_FLAG_FORCE_NO_UPDATES**更改如何处理会议更新。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-123">You can combine this flag with either **REBASE_FLAG_FORCE_NO_EX_UPDATES** or **REBASE_FLAG_FORCE_NO_UPDATES** to change how meeting updates are handled.</span></span> 
    
   - <span data-ttu-id="8f9d2-124">**REBASE_FLAG_UPDATE_UNMARKED** — 更新尚未标记的约会项目所在的时区。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-124">**REBASE_FLAG_UPDATE_UNMARKED** —Update appointment items that have not been marked with a time zone.</span></span> <span data-ttu-id="8f9d2-125">如果指定此标志，则*pTZMissing*值用于中创建项目所在的时区作为没有所在的时区数据的所有项目。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-125">If this flag is specified, the  *pTZMissing*  value is used as the time zone that an item is created in for all items that do not have time zone data.</span></span> 
    
   - <span data-ttu-id="8f9d2-126">**REBASE_FLAG_UPDATE_ONLYRECURRING** — 更新仅定期约会项目。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-126">**REBASE_FLAG_UPDATE_ONLYRECURRING** —Update only recurring appointment items.</span></span> 
    
   - <span data-ttu-id="8f9d2-127">**REBASE_FLAG_NO_UI** — 不显示任何用户界面 (UI)，包括登录时打开的消息存储通常显示的对话框。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-127">**REBASE_FLAG_NO_UI** —Do not show any user interface (UI), including logon dialog boxes generally displayed when opening a message store.</span></span> 
    
   - <span data-ttu-id="8f9d2-128">**REBASE_FLAG_UPDATE_MINIMIZEAPPTS** — 不定在过去发生的约会项目。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-128">**REBASE_FLAG_UPDATE_MINIMIZEAPPTS** —Do not rebase appointment items that occur in the past.</span></span> 
    
   - <span data-ttu-id="8f9d2-129">**REBASE_FLAG_FORCE_REBASE** — 不检查的定位决策，组织者，但定顺序用户是与会者的约会项目。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-129">**REBASE_FLAG_FORCE_REBASE** —Do not check the organizer for rebasing decisions, but rebase appointment items in which the user is an attendee.</span></span> 
    
   - <span data-ttu-id="8f9d2-130">**REBASE_FLAG_FORCE_NO_EX_UPDATES** — 发送更新仅当用户是组织者和收件人未连接到 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-130">**REBASE_FLAG_FORCE_NO_EX_UPDATES** —Send updates only if the user is the organizer and recipient is not connected to an Exchange Server.</span></span> 
    
   - <span data-ttu-id="8f9d2-131">**REBASE_FLAG_FORCE_NO_UPDATES** — 从不发送更新。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-131">**REBASE_FLAG_FORCE_NO_UPDATES** —Never send updates.</span></span> 
    
   - <span data-ttu-id="8f9d2-132">**REBASE_FLAG_ONLY_CREATED_PRE_PATCH** — 定仅应用修补程序之前创建的单实例约会项目。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-132">**REBASE_FLAG_ONLY_CREATED_PRE_PATCH** —Rebase only single-instance appointment items created before the patch was applied.</span></span> 
    
   - <span data-ttu-id="8f9d2-133">**REBASE_FLAG_REPORTING_MODE** — 执行操作不实际重定基本值，只报告的约会项目将被重新设定基址。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-133">**REBASE_FLAG_REPORTING_MODE** —Do not actually rebase, just report appointment items that would be rebased.</span></span> 
    
   - <span data-ttu-id="8f9d2-134">**REBASE_FLAG_SEND_RESOURCE_UPDATES** — 会议更新发送到的资源。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-134">**REBASE_FLAG_SEND_RESOURCE_UPDATES** —Send meeting updates to resources.</span></span> 
    
<span data-ttu-id="8f9d2-135">_pSession_</span><span class="sxs-lookup"><span data-stu-id="8f9d2-135">_pSession_</span></span>
  
> <span data-ttu-id="8f9d2-136">[中]所必需。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-136">[in] Required.</span></span> <span data-ttu-id="8f9d2-137">指向 MAPI 会话接口的指针。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-137">A pointer to a MAPI session interface.</span></span>
    
<span data-ttu-id="8f9d2-138">_pCalendarMsgStore_</span><span class="sxs-lookup"><span data-stu-id="8f9d2-138">_pCalendarMsgStore_</span></span>
  
> <span data-ttu-id="8f9d2-139">[中]所必需。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-139">[in] Required.</span></span> <span data-ttu-id="8f9d2-140">指向包含要在重新设定基址的约会项的消息存储的指针。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-140">A pointer to a message store containing appointment items to be rebased.</span></span>
    
<span data-ttu-id="8f9d2-141">_pCalendarFolder_</span><span class="sxs-lookup"><span data-stu-id="8f9d2-141">_pCalendarFolder_</span></span>
  
> <span data-ttu-id="8f9d2-142">[中]所必需。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-142">[in] Required.</span></span> <span data-ttu-id="8f9d2-143">包含约会项目重新设定基址的日历文件夹指向的指针。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-143">A pointer to a calendar folder containing appointment items to be rebased.</span></span>
    
<span data-ttu-id="8f9d2-144">_pwszUpdatePrefix_</span><span class="sxs-lookup"><span data-stu-id="8f9d2-144">_pwszUpdatePrefix_</span></span>
  
> <span data-ttu-id="8f9d2-145">[中]可选。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-145">[in] Optional.</span></span> <span data-ttu-id="8f9d2-146">一个包含要预置在会议请求的前缀字符串指向的指针。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-146">A pointer to a string containing the prefix to be prepended on meeting requests.</span></span> <span data-ttu-id="8f9d2-147">可能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-147">May be NULL.</span></span>
    
<span data-ttu-id="8f9d2-148">_pftInstallDateUTC_</span><span class="sxs-lookup"><span data-stu-id="8f9d2-148">_pftInstallDateUTC_</span></span>
  
> <span data-ttu-id="8f9d2-149">[中]可选。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-149">[in] Optional.</span></span> <span data-ttu-id="8f9d2-150">所在的时区修补程序安装日期。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-150">The time zone patch install date.</span></span> <span data-ttu-id="8f9d2-151">设置了**REBASE_FLAG_ONLY_CREATED_PRE_PATCH**标志的情况下，才使用。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-151">Used only if the **REBASE_FLAG_ONLY_CREATED_PRE_PATCH** flag is set.</span></span> 
    
<span data-ttu-id="8f9d2-152">_IExpansionDepth_</span><span class="sxs-lookup"><span data-stu-id="8f9d2-152">_IExpansionDepth_</span></span>
  
> <span data-ttu-id="8f9d2-153">[中]可选。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-153">[in] Optional.</span></span> <span data-ttu-id="8f9d2-154">展开通讯组列表来排除收件人时的扩展深度连接到 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-154">The expansion depth when expanding distribution lists to exclude recipients connected to Exchange Server.</span></span> <span data-ttu-id="8f9d2-155">如果设置了**REBASE_FLAG_FORCE_NO_EX_UPDATES**标志，仅使用。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-155">Only used if the **REBASE_FLAG_FORCE_NO_EX_UPDATES** flag is set.</span></span> 
    
<span data-ttu-id="8f9d2-156">_pTZTo_</span><span class="sxs-lookup"><span data-stu-id="8f9d2-156">_pTZTo_</span></span>
  
> <span data-ttu-id="8f9d2-157">[中]所必需。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-157">[in] Required.</span></span> <span data-ttu-id="8f9d2-158">指向描述时区重新到设定基址**TZDEFINITION**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-158">A pointer to a **TZDEFINITION** structure describing the time zone to be rebased to.</span></span> <span data-ttu-id="8f9d2-159">**TZDEFINITION** tzmovelib 中定义。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-159">**TZDEFINITION** is defined in tzmovelib.</span></span> 
    
<span data-ttu-id="8f9d2-160">pTZMissing</span><span class="sxs-lookup"><span data-stu-id="8f9d2-160">pTZMissing</span></span>
  
> <span data-ttu-id="8f9d2-161">[中]所必需。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-161">[in] Required.</span></span> <span data-ttu-id="8f9d2-162">指向描述时区假定如果时区信息不标记的项的**TZDEFINITION**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-162">A pointer to a **TZDEFINITION** structure describing the time zone to be assumed if time zone information is not stamped on an item.</span></span> <span data-ttu-id="8f9d2-163">不能为空，但只能使用如果设置了**REBASE_FLAG_UPDATE_UNMARKED**标志。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-163">Must not be NULL, but only used if the **REBASE_FLAG_UPDATE_UNMARKED** flag is set.</span></span> 
    
<span data-ttu-id="8f9d2-164">_ppError_</span><span class="sxs-lookup"><span data-stu-id="8f9d2-164">_ppError_</span></span>
  
> <span data-ttu-id="8f9d2-165">[输出]指向包含用于错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-165">[out] A pointer to a pointer to a **MAPIERROR** structure containing version, component, and context information for the error.</span></span> <span data-ttu-id="8f9d2-166">可以为 NULL，如果需要未扩展的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-166">Can be NULL if no extended error information is desired.</span></span> <span data-ttu-id="8f9d2-167">释放与[MAPIFreeBuffer](http://msdn.microsoft.com/library/9412594f-8acc-4c7e-a668-4ec1da0ad9cf%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-167">Free with [MAPIFreeBuffer](http://msdn.microsoft.com/library/9412594f-8acc-4c7e-a668-4ec1da0ad9cf%28Office.15%29.aspx).</span></span> 
    
<span data-ttu-id="8f9d2-168">_ppApptRebase_</span><span class="sxs-lookup"><span data-stu-id="8f9d2-168">_ppApptRebase_</span></span>
  
> <span data-ttu-id="8f9d2-169">[输出]指向返回**IOlkApptRebaser**接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-169">[out] A pointer to a pointer to the returned **IOlkApptRebaser** interface.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="8f9d2-170">返回值</span><span class="sxs-lookup"><span data-stu-id="8f9d2-170">Return values</span></span>

<span data-ttu-id="8f9d2-171">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-171">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8f9d2-172">注释</span><span class="sxs-lookup"><span data-stu-id="8f9d2-172">Remarks</span></span>

<span data-ttu-id="8f9d2-173">当使用[GetProcAddress](http://msdn.microsoft.com/library/a0d7fc09-f888-4f46-a571-d3719a627597%28Office.15%29.aspx)查找 tzmovelib.dll 中此函数的地址，指定**HrCreateApptRebaser@44**作为过程名称。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-173">When using [GetProcAddress](http://msdn.microsoft.com/library/a0d7fc09-f888-4f46-a571-d3719a627597%28Office.15%29.aspx) to look for the address of this function in tzmovelib.dll, specify **HrCreateApptRebaser@44** as the procedure name.</span></span> <span data-ttu-id="8f9d2-174">并非所有标记都有效与每个其他结合使用。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-174">Not all of the flags are valid in combination with each other.</span></span> 
  
<span data-ttu-id="8f9d2-175">有关的各种选项的详细信息，请参阅"command-line options for Outlook 所在的时区数据更新工具词汇表"一节中的[KB 931667： 如何使用 Microsoft Office outlook 的时区数据更新工具地址时区更改](http://support.microsoft.com/kb/931667/en-us)。</span><span class="sxs-lookup"><span data-stu-id="8f9d2-175">For more information about the various options, see the section "Glossary of command-line options for the Outlook Time Zone Data Update tool" in [KB 931667: How to address time zone changes by using the Time Zone Data Update Tool for Microsoft Office Outlook](http://support.microsoft.com/kb/931667/en-us).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8f9d2-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f9d2-176">See also</span></span>

- [<span data-ttu-id="8f9d2-177">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="8f9d2-177">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

