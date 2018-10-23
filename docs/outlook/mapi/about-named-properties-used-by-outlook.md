---
title: 关于 Outlook 使用的命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8c245ec2-bb18-ecf0-b4ad-8c164c5924cf
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: aa4d52d25f120e8b3e2a4c0dcaa4845ad576127a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566227"
---
# <a name="about-named-properties-used-by-outlook"></a><span data-ttu-id="a77de-103">关于 Outlook 使用的命名属性</span><span class="sxs-lookup"><span data-stu-id="a77de-103">About Named Properties Used by Outlook</span></span>

  
  
<span data-ttu-id="a77de-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a77de-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a77de-105">MAPI 提供将名称分配给某些特定属性、将这些名称映射到唯一标识符以及使这个名称到标识符的映射跨会话保持不变的工具。</span><span class="sxs-lookup"><span data-stu-id="a77de-105">MAPI provides a facility for assigning names to certain properties, for mapping these names to unique identifiers, and for making this name-to-identifier mapping persistent across sessions.</span></span> <span data-ttu-id="a77de-106">命名属性由名称和属性集的全局唯一标识符 (GUID) 标识。</span><span class="sxs-lookup"><span data-stu-id="a77de-106">Named properties are identified by a name and a globally unique identifier (GUID) for a property set.</span></span> <span data-ttu-id="a77de-107">名称可以是数字或字符串。</span><span class="sxs-lookup"><span data-stu-id="a77de-107">The name can be a number or a string.</span></span> <span data-ttu-id="a77de-108">对于 Microsoft Outlook 2013 或 Microsoft Outlook 2010，属性集通常是由 Outlook 2013 或 Outlook 2010 定义的命名空间，如 **PSETID_Appointment**。</span><span class="sxs-lookup"><span data-stu-id="a77de-108">For Microsoft Outlook 2013 or Microsoft Outlook 2010, the property set is often a namespace defined by Outlook 2013 or Outlook 2010, such as **PSETID_Appointment**.</span></span> 
  
<span data-ttu-id="a77de-109">命名属性通过使用 [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) 函数和 [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) 函数进行操作。</span><span class="sxs-lookup"><span data-stu-id="a77de-109">Named properties are manipulated by using the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) function and the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) function.</span></span> <span data-ttu-id="a77de-110">将名称和属性集 GUID 传递给 [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) 函数以获取对当前 MAPI 会话有效的属性标识符。</span><span class="sxs-lookup"><span data-stu-id="a77de-110">The name and the property set GUID are passed to the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) function to obtain a property identifier that is valid for the current MAPI session.</span></span> <span data-ttu-id="a77de-111">由于此属性标识符可能因计算机而异，因此访问命名属性的唯一一致方法是知道其名称和属性集 GUID。</span><span class="sxs-lookup"><span data-stu-id="a77de-111">Because this property identifier can vary from computer to computer, the only consistent way to access a named property is to know its name and property set GUID.</span></span> <span data-ttu-id="a77de-112">标识符的范围始终位于 0x8000 到 0xFFFE 之间。</span><span class="sxs-lookup"><span data-stu-id="a77de-112">The range for identifiers is always in the 0x8000 and 0xFFFE range.</span></span> 
  
<span data-ttu-id="a77de-113">实现 [IMAPIProp: IUnknown](imapipropiunknown.md) 界面的任何对象可支持命名属性。</span><span class="sxs-lookup"><span data-stu-id="a77de-113">Any object that implements the [IMAPIProp : IUnknown](imapipropiunknown.md) interface can support named properties.</span></span> <span data-ttu-id="a77de-114">具体来说，MAPI 服务提供程序或 MAPI 客户端必须实现 [IMAPIProp::GetProps](imapiprop-getprops.md) 以获取命名属性的值。</span><span class="sxs-lookup"><span data-stu-id="a77de-114">Specifically, a MAPI service provider or a MAPI client must implement [IMAPIProp::GetProps](imapiprop-getprops.md) to get values of named properties.</span></span> <span data-ttu-id="a77de-115">不支持设置 Outlook 2013 或 Outlook 2010 使用的命名属性，因为存在损坏与其他 MAPI 提供程序或客户端共享的数据的风险。</span><span class="sxs-lookup"><span data-stu-id="a77de-115">Setting named properties used by Outlook 2013 or Outlook 2010 is not supported because of the risk of corrupting data that is shared with other MAPI providers or clients.</span></span> 
  
<span data-ttu-id="a77de-116">Outlook 2013 和 Outlook 2010 使用 MAPI 命名属性实现其许多功能，例如附件安全性和会议反建议。</span><span class="sxs-lookup"><span data-stu-id="a77de-116">Outlook 2013 and Outlook 2010 use MAPI named properties to implement many of their features, for example, attachment security and meeting counter-proposals.</span></span> <span data-ttu-id="a77de-117">在此基础数据之上，Outlook 2013 和 Outlook 2010 会公开这些属性中的某些属性作为 Outlook 2013 和 Outlook 2010 对象模型中的项属性。</span><span class="sxs-lookup"><span data-stu-id="a77de-117">Above this underlying data, Outlook 2013 and Outlook 2010 expose some of these properties as item properties in their Outlook 2013 and Outlook 2010 object models.</span></span> <span data-ttu-id="a77de-118">例如，对象模型中 **ContactItem** 对象的 **Email1Address** 属性与 **PSETID_Address** 命名空间中的命名 [PidLidEmail1EmailAddress 规范属性](pidlidemail1emailaddress-canonical-property.md)对应。</span><span class="sxs-lookup"><span data-stu-id="a77de-118">For example, the **Email1Address** property of the **ContactItem** object in the object model corresponds to the named [PidLidEmail1EmailAddress Canonical Property](pidlidemail1emailaddress-canonical-property.md) in the **PSETID_Address** namespace.</span></span> <span data-ttu-id="a77de-119">但一般情况下，由于兼容性和数据完整性问题，Outlook 2013 和 Outlook 2010 使用的许多 MAPI 属性不会在对象模型中公开。</span><span class="sxs-lookup"><span data-stu-id="a77de-119">But in general, due to concerns for compatibility and data integrity, many of the MAPI properties that are used by Outlook 2013 and Outlook 2010 are not exposed in the object model.</span></span> 
  
<span data-ttu-id="a77de-120">此参考描述了下面列出的许多命名属性。</span><span class="sxs-lookup"><span data-stu-id="a77de-120">This reference describes a number of named properties that are listed below.</span></span>
  
<span data-ttu-id="a77de-121">**PSETID_Address** 命名空间中的命名属性如下：</span><span class="sxs-lookup"><span data-stu-id="a77de-121">Named properties in the **PSETID_Address** namespace are the following:</span></span> 
  
- [<span data-ttu-id="a77de-122">PidLidEmail1AddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-122">PidLidEmail1AddressType canonical property</span></span>](pidlidemail1addresstype-canonical-property.md)
    
- [<span data-ttu-id="a77de-123">PidLidEmail1EmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-123">PidLidEmail1EmailAddress canonical property</span></span>](pidlidemail1emailaddress-canonical-property.md)
    
- [<span data-ttu-id="a77de-124">PidLidEmail1OriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-124">PidLidEmail1OriginalEntryId canonical property</span></span>](pidlidemail1originalentryid-canonical-property.md)
    
- [<span data-ttu-id="a77de-125">PidLidEmail2AddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-125">PidLidEmail2AddressType canonical property</span></span>](pidlidemail2addresstype-canonical-property.md)
    
- [<span data-ttu-id="a77de-126">PidLidEmail2DisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-126">PidLidEmail2DisplayName canonical property</span></span>](pidlidemail2displayname-canonical-property.md)
    
- [<span data-ttu-id="a77de-127">PidLidEmail2EmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-127">PidLidEmail2EmailAddress canonical property</span></span>](pidlidemail2emailaddress-canonical-property.md)
    
- [<span data-ttu-id="a77de-128">PidLidEmail2OriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-128">PidLidEmail2OriginalDisplayName canonical property</span></span>](pidlidemail2originaldisplayname-canonical-property.md)
    
- [<span data-ttu-id="a77de-129">PidLidEmail2OriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-129">PidLidEmail2OriginalEntryId canonical property</span></span>](pidlidemail2originalentryid-canonical-property.md)
    
- [<span data-ttu-id="a77de-130">PidLidEmail3AddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-130">PidLidEmail3AddressType canonical property</span></span>](pidlidemail3addresstype-canonical-property.md)
    
- [<span data-ttu-id="a77de-131">PidLidEmail3DisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-131">PidLidEmail3DisplayName canonical property</span></span>](pidlidemail3displayname-canonical-property.md)
    
- [<span data-ttu-id="a77de-132">PidLidEmail3EmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-132">PidLidEmail3EmailAddress canonical property</span></span>](pidlidemail3emailaddress-canonical-property.md)
    
- [<span data-ttu-id="a77de-133">PidLidEmail3OriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-133">PidLidEmail3OriginalDisplayName canonical property</span></span>](pidlidemail3originaldisplayname-canonical-property.md)
    
- [<span data-ttu-id="a77de-134">PidLidEmail3OriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-134">PidLidEmail3OriginalEntryId canonical property</span></span>](pidlidemail3originalentryid-canonical-property.md)
    
- [<span data-ttu-id="a77de-135">PidLidEmail1DisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-135">PidLidEmail1DisplayName canonical property</span></span>](pidlidemail1displayname-canonical-property.md)
    
- [<span data-ttu-id="a77de-136">PidLidEmail1OriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-136">PidLidEmail1OriginalDisplayName canonical property</span></span>](pidlidemail1originaldisplayname-canonical-property.md)
    
- [<span data-ttu-id="a77de-137">PidLidFileUnder 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-137">PidLidFileUnder canonical property</span></span>](pidlidfileunder-canonical-property.md)
    
- [<span data-ttu-id="a77de-138">PidLidInstantMessagingAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-138">PidLidInstantMessagingAddress canonical property</span></span>](pidlidinstantmessagingaddress-canonical-property.md)
    
- [<span data-ttu-id="a77de-139">PidLidWorkAddressCity 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-139">PidLidWorkAddressCity canonical property</span></span>](pidlidworkaddresscity-canonical-property.md)
    
- [<span data-ttu-id="a77de-140">PidLidWorkAddressCountry 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-140">PidLidWorkAddressCountry canonical property</span></span>](pidlidworkaddresscountry-canonical-property.md)
    
- [<span data-ttu-id="a77de-141">PidLidWorkAddressPostalCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-141">PidLidWorkAddressPostalCode canonical property</span></span>](pidlidworkaddresspostalcode-canonical-property.md)
    
- [<span data-ttu-id="a77de-142">PidLidWorkAddressPostOfficeBox 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-142">PidLidWorkAddressPostOfficeBox canonical property</span></span>](pidlidworkaddresspostofficebox-canonical-property.md)
    
- [<span data-ttu-id="a77de-143">PidLidWorkAddressState 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-143">PidLidWorkAddressState canonical property</span></span>](pidlidworkaddressstate-canonical-property.md)
    
- [<span data-ttu-id="a77de-144">PidLidWorkAddressStreet 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-144">PidLidWorkAddressStreet canonical property</span></span>](pidlidworkaddressstreet-canonical-property.md)
    
- [<span data-ttu-id="a77de-145">PidLidYomiCompanyName 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-145">PidLidYomiCompanyName canonical property</span></span>](pidlidyomicompanyname-canonical-property.md)
    
- [<span data-ttu-id="a77de-146">PidLidYomiFirstName 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-146">PidLidYomiFirstName canonical property</span></span>](pidlidyomifirstname-canonical-property.md)
    
- [<span data-ttu-id="a77de-147">PidLidYomiLastName 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-147">PidLidYomiLastName canonical property</span></span>](pidlidyomilastname-canonical-property.md)
    
<span data-ttu-id="a77de-148">**PSETID_Appointment** 命名空间中的命名属性如下：</span><span class="sxs-lookup"><span data-stu-id="a77de-148">Named properties in the **PSETID_Appointment** namespace are the following:</span></span> 
  
- [<span data-ttu-id="a77de-149">PidLidAllAttendeesString 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-149">PidLidAllAttendeesString canonical property</span></span>](pidlidallattendeesstring-canonical-property.md)
    
- [<span data-ttu-id="a77de-150">PidLidAppointmentCounterProposal 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-150">PidLidAppointmentCounterProposal canonical property</span></span>](pidlidappointmentcounterproposal-canonical-property.md)
    
- [<span data-ttu-id="a77de-151">PidLidAppointmentDuration 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-151">PidLidAppointmentDuration canonical property</span></span>](pidlidappointmentduration-canonical-property.md)
    
- [<span data-ttu-id="a77de-152">PidLidAppointmentEndWhole 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-152">PidLidAppointmentEndWhole canonical property</span></span>](pidlidappointmentendwhole-canonical-property.md)
    
- [<span data-ttu-id="a77de-153">PidLidAppointmentStartWhole 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-153">PidLidAppointmentStartWhole canonical property</span></span>](pidlidappointmentstartwhole-canonical-property.md)
    
- [<span data-ttu-id="a77de-154">PidLidBusyStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-154">PidLidBusyStatus canonical property</span></span>](pidlidbusystatus-canonical-property.md)
    
- [<span data-ttu-id="a77de-155">PidLidCcAttendeesString 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-155">PidLidCcAttendeesString canonical property</span></span>](pidlidccattendeesstring-canonical-property.md)
    
- [<span data-ttu-id="a77de-156">PidLidLocation 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-156">PidLidLocation canonical property</span></span>](pidlidlocation-canonical-property.md)
    
- [<span data-ttu-id="a77de-157">PidLidRecurring 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-157">PidLidRecurring canonical property</span></span>](pidlidrecurring-canonical-property.md)
    
- [<span data-ttu-id="a77de-158">PidLidToAttendeesString 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-158">PidLidToAttendeesString canonical property</span></span>](pidlidtoattendeesstring-canonical-property.md)
    
<span data-ttu-id="a77de-159">**PSETID_Common** 命名空间中的命名属性如下：</span><span class="sxs-lookup"><span data-stu-id="a77de-159">Named properties in the **PSETID_Common** namespace are the following:</span></span> 
  
- [<span data-ttu-id="a77de-160">PidLidCommonEnd 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-160">PidLidCommonEnd canonical property</span></span>](pidlidcommonend-canonical-property.md)
    
- [<span data-ttu-id="a77de-161">PidLidCommonStart 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-161">PidLidCommonStart canonical property</span></span>](pidlidcommonstart-canonical-property.md)
    
- [<span data-ttu-id="a77de-162">PidLidCompanies 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-162">PidLidCompanies canonical property</span></span>](pidlidcompanies-canonical-property.md)
    
- [<span data-ttu-id="a77de-163">PidLidContacts 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-163">PidLidContacts canonical property</span></span>](pidlidcontacts-canonical-property.md)
    
- [<span data-ttu-id="a77de-164">PidLidCustomFlag 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-164">PidLidCustomFlag canonical property</span></span>](pidlidcustomflag-canonical-property.md)
    
- [<span data-ttu-id="a77de-165">PidLidFormPropStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-165">PidLidFormPropStream canonical property</span></span>](pidlidformpropstream-canonical-property.md)
    
- [<span data-ttu-id="a77de-166">PidLidFormStorage 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-166">PidLidFormStorage canonical property</span></span>](pidlidformstorage-canonical-property.md)
    
- [<span data-ttu-id="a77de-167">PidLidHeaderItem 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-167">PidLidHeaderItem canonical property</span></span>](pidlidheaderitem-canonical-property.md)
    
- [<span data-ttu-id="a77de-168">PidLidPageDirStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-168">PidLidPageDirStream canonical property</span></span>](pidlidpagedirstream-canonical-property.md)
    
- [<span data-ttu-id="a77de-169">PidLidPropertyDefinitionStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-169">PidLidPropertyDefinitionStream canonical property</span></span>](pidlidpropertydefinitionstream-canonical-property.md)
    
- [<span data-ttu-id="a77de-170">PidLidReminderSet 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-170">PidLidReminderSet canonical property</span></span>](pidlidreminderset-canonical-property.md)
    
- [<span data-ttu-id="a77de-171">PidLidReminderTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-171">PidLidReminderTime canonical property</span></span>](pidlidremindertime-canonical-property.md)
    
- [<span data-ttu-id="a77de-172">PidLidFlagRequest 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-172">PidLidFlagRequest canonical property</span></span>](pidlidflagrequest-canonical-property.md)
    
- [<span data-ttu-id="a77de-173">PidLidScriptStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-173">PidLidScriptStream canonical property</span></span>](pidlidscriptstream-canonical-property.md)
    
- [<span data-ttu-id="a77de-174">PidLidSmartNoAttach 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-174">PidLidSmartNoAttach canonical property</span></span>](pidlidsmartnoattach-canonical-property.md)
    
- [<span data-ttu-id="a77de-175">PidLidToDoTitle 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-175">PidLidToDoTitle canonical property</span></span>](pidlidtodotitle-canonical-property.md)
    
- [<span data-ttu-id="a77de-176">PidLidUseTnef 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-176">PidLidUseTnef canonical property</span></span>](pidlidusetnef-canonical-property.md)
    
<span data-ttu-id="a77de-177">**PSETID_Meeting** 命名空间中的命名属性如下：</span><span class="sxs-lookup"><span data-stu-id="a77de-177">Named properties in the **PSETID_Meeting** namespace are the following:</span></span> 
  
- [<span data-ttu-id="a77de-178">PidLidMeetingType 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-178">PidLidMeetingType canonical property</span></span>](pidlidmeetingtype-canonical-property.md)
    
<span data-ttu-id="a77de-179">**PSETID_Task** 命名空间中的命名属性如下：</span><span class="sxs-lookup"><span data-stu-id="a77de-179">Named properties in the **PSETID_Task** namespace are the following:</span></span> 
  
- [<span data-ttu-id="a77de-180">PidLidTaskActualEffort 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-180">PidLidTaskActualEffort canonical property</span></span>](pidlidtaskactualeffort-canonical-property.md)
    
- [<span data-ttu-id="a77de-181">PidLidTaskDueDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-181">PidLidTaskDueDate canonical property</span></span>](pidlidtaskduedate-canonical-property.md)
    
- [<span data-ttu-id="a77de-182">PidLidTaskEstimatedEffort 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-182">PidLidTaskEstimatedEffort canonical property</span></span>](pidlidtaskestimatedeffort-canonical-property.md)
    
- [<span data-ttu-id="a77de-183">PidLidTaskFRecurring 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-183">PidLidTaskFRecurring canonical property</span></span>](pidlidtaskfrecurring-canonical-property.md)
    
- [<span data-ttu-id="a77de-184">PidLidTaskStartDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-184">PidLidTaskStartDate canonical property</span></span>](pidlidtaskstartdate-canonical-property.md)
    
- [<span data-ttu-id="a77de-185">PidLidTaskStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-185">PidLidTaskStatus canonical property</span></span>](pidlidtaskstatus-canonical-property.md)
    
<span data-ttu-id="a77de-186">**PS_INTERNET_HEADERS** 命名空间中的命名属性如下：</span><span class="sxs-lookup"><span data-stu-id="a77de-186">Named properties in the **PS_INTERNET_HEADERS** namespace are the following:</span></span> 
  
- [<span data-ttu-id="a77de-187">PidTagInternetReturnPath 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-187">PidTagInternetReturnPath canonical property</span></span>](pidtaginternetreturnpath-canonical-property.md)
    
<span data-ttu-id="a77de-188">**PSETID_Log** 命名空间中的命名属性如下：</span><span class="sxs-lookup"><span data-stu-id="a77de-188">Named properties in the **PSETID_Log** namespace are the following:</span></span> 
  
- [<span data-ttu-id="a77de-189">PidLidLogDuration 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-189">PidLidLogDuration canonical property</span></span>](pidlidlogduration-canonical-property.md)
    
- [<span data-ttu-id="a77de-190">PidLidLogEnd 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-190">PidLidLogEnd canonical property</span></span>](pidlidlogend-canonical-property.md)
    
- [<span data-ttu-id="a77de-191">PidLidLogStart 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-191">PidLidLogStart canonical property</span></span>](pidlidlogstart-canonical-property.md)
    
- [<span data-ttu-id="a77de-192">PidLidLogType 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-192">PidLidLogType canonical property</span></span>](pidlidlogtype-canonical-property.md)
    
<span data-ttu-id="a77de-193">**PS_PUBLIC_STRINGS** 命名空间中的命名属性如下：</span><span class="sxs-lookup"><span data-stu-id="a77de-193">Named properties in the **PS_PUBLIC_STRINGS** namespace are the following:</span></span> 
  
- [<span data-ttu-id="a77de-194">PidNameKeywords 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-194">PidNameKeywords canonical property</span></span>](pidnamekeywords-canonical-property.md)
    
- [<span data-ttu-id="a77de-195">PidNameExchangeJunkEmailMoveStamp 规范属性</span><span class="sxs-lookup"><span data-stu-id="a77de-195">PidNameExchangeJunkEmailMoveStamp canonical property</span></span>](pidnameexchangejunkemailmovestamp-canonical-property.md)
    
## <a name="see-also"></a><span data-ttu-id="a77de-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a77de-196">See also</span></span>



[<span data-ttu-id="a77de-197">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="a77de-197">MAPI constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="a77de-198">确定 Outlook 是否仅下载邮件头</span><span class="sxs-lookup"><span data-stu-id="a77de-198">Determine if Outlook downloaded only the header of a message</span></span>](how-to-determine-if-outlook-downloaded-only-the-header-of-a-message.md)
  
[<span data-ttu-id="a77de-199">获取联系人项的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="a77de-199">Get the email address of a Contact item</span></span>](how-to-get-the-email-address-of-a-contact-item.md)
  
[<span data-ttu-id="a77de-200">删除随邮件一起保存的自定义表单定义</span><span class="sxs-lookup"><span data-stu-id="a77de-200">Remove custom form definition saved with a message</span></span>](how-to-remove-custom-form-definition-saved-with-a-message.md)

