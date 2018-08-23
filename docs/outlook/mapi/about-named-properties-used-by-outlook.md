---
title: 关于 Outlook 使用的命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8c245ec2-bb18-ecf0-b4ad-8c164c5924cf
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: aa4d52d25f120e8b3e2a4c0dcaa4845ad576127a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566227"
---
# <a name="about-named-properties-used-by-outlook"></a><span data-ttu-id="f7fb2-103">关于 Outlook 使用的命名属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-103">About Named Properties Used by Outlook</span></span>

  
  
<span data-ttu-id="f7fb2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f7fb2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f7fb2-105">MAPI 提供的工具，将名称分配给特定属性、 将这些名称映射到唯一标识符，以及使此名称为标识符映射各个会话持久性。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-105">MAPI provides a facility for assigning names to certain properties, for mapping these names to unique identifiers, and for making this name-to-identifier mapping persistent across sessions.</span></span> <span data-ttu-id="f7fb2-106">命名的属性标识的名称和属性集的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-106">Named properties are identified by a name and a globally unique identifier (GUID) for a property set.</span></span> <span data-ttu-id="f7fb2-107">名称可以是数字或字符串。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-107">The name can be a number or a string.</span></span> <span data-ttu-id="f7fb2-108">对于 Microsoft Outlook 2013 或 Microsoft Outlook 2010，属性设置通常由 Outlook 2013 或 Outlook 2010 中，如**PSETID_Appointment**定义的命名空间。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-108">For Microsoft Outlook 2013 or Microsoft Outlook 2010, the property set is often a namespace defined by Outlook 2013 or Outlook 2010, such as **PSETID_Appointment**.</span></span> 
  
<span data-ttu-id="f7fb2-109">通过使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)函数和[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)函数操作时命名的属性。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-109">Named properties are manipulated by using the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) function and the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) function.</span></span> <span data-ttu-id="f7fb2-110">名称和属性集 GUID 传递到[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)函数获取当前的 MAPI 会话是有效的属性标识符。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-110">The name and the property set GUID are passed to the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) function to obtain a property identifier that is valid for the current MAPI session.</span></span> <span data-ttu-id="f7fb2-111">因为此属性标识符可以不同计算机到计算机，仅一致的方式访问的命名的属性是知道其名称和属性集 GUID。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-111">Because this property identifier can vary from computer to computer, the only consistent way to access a named property is to know its name and property set GUID.</span></span> <span data-ttu-id="f7fb2-112">始终位于 0x8000 和 0xFFFE 区域标识符的范围。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-112">The range for identifiers is always in the 0x8000 and 0xFFFE range.</span></span> 
  
<span data-ttu-id="f7fb2-113">实现任何对象[IMAPIProp: IUnknown](imapipropiunknown.md)接口可支持命名的属性。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-113">Any object that implements the [IMAPIProp : IUnknown](imapipropiunknown.md) interface can support named properties.</span></span> <span data-ttu-id="f7fb2-114">具体而言，MAPI 服务提供商或 MAPI 客户端必须实现[IMAPIProp::GetProps](imapiprop-getprops.md)获取的命名属性的值。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-114">Specifically, a MAPI service provider or a MAPI client must implement [IMAPIProp::GetProps](imapiprop-getprops.md) to get values of named properties.</span></span> <span data-ttu-id="f7fb2-115">名为 Outlook 2013 或 Outlook 2010 中使用的属性的设置不支持由于破坏其他 MAPI 提供程序或客户端与共享的数据的风险。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-115">Setting named properties used by Outlook 2013 or Outlook 2010 is not supported because of the risk of corrupting data that is shared with other MAPI providers or clients.</span></span> 
  
<span data-ttu-id="f7fb2-116">Outlook 2013 和 Outlook 2010 使用 MAPI 命名属性，以实现多个及其功能，例如、 附件安全性和会议反建议。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-116">Outlook 2013 and Outlook 2010 use MAPI named properties to implement many of their features, for example, attachment security and meeting counter-proposals.</span></span> <span data-ttu-id="f7fb2-117">上面这些基础数据，Outlook 2013 和 Outlook 2010 公开这些属性的一些作为其 Outlook 2013 和 Outlook 2010 对象模型中的项目属性。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-117">Above this underlying data, Outlook 2013 and Outlook 2010 expose some of these properties as item properties in their Outlook 2013 and Outlook 2010 object models.</span></span> <span data-ttu-id="f7fb2-118">例如，对象模型中的**ContactItem**对象的**Email1Address**属性对应于**PSETID_Address**命名空间中的命名[PidLidEmail1EmailAddress 规范属性](pidlidemail1emailaddress-canonical-property.md)。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-118">For example, the **Email1Address** property of the **ContactItem** object in the object model corresponds to the named [PidLidEmail1EmailAddress Canonical Property](pidlidemail1emailaddress-canonical-property.md) in the **PSETID_Address** namespace.</span></span> <span data-ttu-id="f7fb2-119">但一般情况下，由于兼容性和数据完整性的问题，许多使用 Outlook 2013 和 Outlook 2010 MAPI 属性中未公开的对象模型。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-119">But in general, due to concerns for compatibility and data integrity, many of the MAPI properties that are used by Outlook 2013 and Outlook 2010 are not exposed in the object model.</span></span> 
  
<span data-ttu-id="f7fb2-120">此参考介绍数下面列出的命名属性。</span><span class="sxs-lookup"><span data-stu-id="f7fb2-120">This reference describes a number of named properties that are listed below.</span></span>
  
<span data-ttu-id="f7fb2-121">**PSETID_Address**命名空间中的命名的属性如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7fb2-121">Named properties in the **PSETID_Address** namespace are the following:</span></span> 
  
- [<span data-ttu-id="f7fb2-122">PidLidEmail1AddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-122">PidLidEmail1AddressType Canonical Property</span></span>](pidlidemail1addresstype-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-123">PidLidEmail1EmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-123">PidLidEmail1EmailAddress Canonical Property</span></span>](pidlidemail1emailaddress-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-124">PidLidEmail1OriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-124">PidLidEmail1OriginalEntryId Canonical Property</span></span>](pidlidemail1originalentryid-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-125">PidLidEmail2AddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-125">PidLidEmail2AddressType Canonical Property</span></span>](pidlidemail2addresstype-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-126">PidLidEmail2DisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-126">PidLidEmail2DisplayName Canonical Property</span></span>](pidlidemail2displayname-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-127">PidLidEmail2EmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-127">PidLidEmail2EmailAddress Canonical Property</span></span>](pidlidemail2emailaddress-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-128">PidLidEmail2OriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-128">PidLidEmail2OriginalDisplayName Canonical Property</span></span>](pidlidemail2originaldisplayname-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-129">PidLidEmail2OriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-129">PidLidEmail2OriginalEntryId Canonical Property</span></span>](pidlidemail2originalentryid-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-130">PidLidEmail3AddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-130">PidLidEmail3AddressType Canonical Property</span></span>](pidlidemail3addresstype-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-131">PidLidEmail3DisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-131">PidLidEmail3DisplayName Canonical Property</span></span>](pidlidemail3displayname-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-132">PidLidEmail3EmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-132">PidLidEmail3EmailAddress Canonical Property</span></span>](pidlidemail3emailaddress-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-133">PidLidEmail3OriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-133">PidLidEmail3OriginalDisplayName Canonical Property</span></span>](pidlidemail3originaldisplayname-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-134">PidLidEmail3OriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-134">PidLidEmail3OriginalEntryId Canonical Property</span></span>](pidlidemail3originalentryid-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-135">PidLidEmail1DisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-135">PidLidEmail1DisplayName Canonical Property</span></span>](pidlidemail1displayname-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-136">PidLidEmail1OriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-136">PidLidEmail1OriginalDisplayName Canonical Property</span></span>](pidlidemail1originaldisplayname-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-137">PidLidFileUnder 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-137">PidLidFileUnder Canonical Property</span></span>](pidlidfileunder-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-138">PidLidInstantMessagingAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-138">PidLidInstantMessagingAddress Canonical Property</span></span>](pidlidinstantmessagingaddress-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-139">PidLidWorkAddressCity 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-139">PidLidWorkAddressCity Canonical Property</span></span>](pidlidworkaddresscity-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-140">PidLidWorkAddressCountry 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-140">PidLidWorkAddressCountry Canonical Property</span></span>](pidlidworkaddresscountry-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-141">PidLidWorkAddressPostalCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-141">PidLidWorkAddressPostalCode Canonical Property</span></span>](pidlidworkaddresspostalcode-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-142">PidLidWorkAddressPostOfficeBox 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-142">PidLidWorkAddressPostOfficeBox Canonical Property</span></span>](pidlidworkaddresspostofficebox-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-143">PidLidWorkAddressState 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-143">PidLidWorkAddressState Canonical Property</span></span>](pidlidworkaddressstate-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-144">PidLidWorkAddressStreet 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-144">PidLidWorkAddressStreet Canonical Property</span></span>](pidlidworkaddressstreet-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-145">PidLidYomiCompanyName 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-145">PidLidYomiCompanyName Canonical Property</span></span>](pidlidyomicompanyname-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-146">PidLidYomiFirstName 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-146">PidLidYomiFirstName Canonical Property</span></span>](pidlidyomifirstname-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-147">PidLidYomiLastName 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-147">PidLidYomiLastName Canonical Property</span></span>](pidlidyomilastname-canonical-property.md)
    
<span data-ttu-id="f7fb2-148">**PSETID_Appointment**命名空间中的命名的属性如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7fb2-148">Named properties in the **PSETID_Appointment** namespace are the following:</span></span> 
  
- [<span data-ttu-id="f7fb2-149">PidLidAllAttendeesString 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-149">PidLidAllAttendeesString Canonical Property</span></span>](pidlidallattendeesstring-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-150">PidLidAppointmentCounterProposal 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-150">PidLidAppointmentCounterProposal Canonical Property</span></span>](pidlidappointmentcounterproposal-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-151">PidLidAppointmentDuration 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-151">PidLidAppointmentDuration Canonical Property</span></span>](pidlidappointmentduration-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-152">PidLidAppointmentEndWhole 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-152">PidLidAppointmentEndWhole Canonical Property</span></span>](pidlidappointmentendwhole-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-153">PidLidAppointmentStartWhole 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-153">PidLidAppointmentStartWhole Canonical Property</span></span>](pidlidappointmentstartwhole-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-154">PidLidBusyStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-154">PidLidBusyStatus Canonical Property</span></span>](pidlidbusystatus-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-155">PidLidCcAttendeesString 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-155">PidLidCcAttendeesString Canonical Property</span></span>](pidlidccattendeesstring-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-156">PidLidLocation 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-156">PidLidLocation Canonical Property</span></span>](pidlidlocation-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-157">PidLidRecurring 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-157">PidLidRecurring Canonical Property</span></span>](pidlidrecurring-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-158">PidLidToAttendeesString 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-158">PidLidToAttendeesString Canonical Property</span></span>](pidlidtoattendeesstring-canonical-property.md)
    
<span data-ttu-id="f7fb2-159">**PSETID_Common**命名空间中的命名的属性如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7fb2-159">Named properties in the **PSETID_Common** namespace are the following:</span></span> 
  
- [<span data-ttu-id="f7fb2-160">PidLidCommonEnd 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-160">PidLidCommonEnd Canonical Property</span></span>](pidlidcommonend-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-161">PidLidCommonStart 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-161">PidLidCommonStart Canonical Property</span></span>](pidlidcommonstart-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-162">PidLidCompanies 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-162">PidLidCompanies Canonical Property</span></span>](pidlidcompanies-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-163">PidLidContacts 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-163">PidLidContacts Canonical Property</span></span>](pidlidcontacts-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-164">PidLidCustomFlag 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-164">PidLidCustomFlag Canonical Property</span></span>](pidlidcustomflag-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-165">PidLidFormPropStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-165">PidLidFormPropStream Canonical Property</span></span>](pidlidformpropstream-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-166">PidLidFormStorage 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-166">PidLidFormStorage Canonical Property</span></span>](pidlidformstorage-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-167">PidLidHeaderItem 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-167">PidLidHeaderItem Canonical Property</span></span>](pidlidheaderitem-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-168">PidLidPageDirStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-168">PidLidPageDirStream Canonical Property</span></span>](pidlidpagedirstream-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-169">PidLidPropertyDefinitionStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-169">PidLidPropertyDefinitionStream Canonical Property</span></span>](pidlidpropertydefinitionstream-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-170">PidLidReminderSet 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-170">PidLidReminderSet Canonical Property</span></span>](pidlidreminderset-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-171">PidLidReminderTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-171">PidLidReminderTime Canonical Property</span></span>](pidlidremindertime-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-172">PidLidFlagRequest 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-172">PidLidFlagRequest Canonical Property</span></span>](pidlidflagrequest-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-173">PidLidScriptStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-173">PidLidScriptStream Canonical Property</span></span>](pidlidscriptstream-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-174">PidLidSmartNoAttach 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-174">PidLidSmartNoAttach Canonical Property</span></span>](pidlidsmartnoattach-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-175">PidLidToDoTitle 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-175">PidLidToDoTitle Canonical Property</span></span>](pidlidtodotitle-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-176">PidLidUseTnef 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-176">PidLidUseTnef Canonical Property</span></span>](pidlidusetnef-canonical-property.md)
    
<span data-ttu-id="f7fb2-177">**PSETID_Meeting**命名空间中的命名的属性如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7fb2-177">Named properties in the **PSETID_Meeting** namespace are the following:</span></span> 
  
- [<span data-ttu-id="f7fb2-178">PidLidMeetingType 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-178">PidLidMeetingType Canonical Property</span></span>](pidlidmeetingtype-canonical-property.md)
    
<span data-ttu-id="f7fb2-179">**PSETID_Task**命名空间中的命名的属性如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7fb2-179">Named properties in the **PSETID_Task** namespace are the following:</span></span> 
  
- [<span data-ttu-id="f7fb2-180">PidLidTaskActualEffort 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-180">PidLidTaskActualEffort Canonical Property</span></span>](pidlidtaskactualeffort-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-181">PidLidTaskDueDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-181">PidLidTaskDueDate Canonical Property</span></span>](pidlidtaskduedate-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-182">PidLidTaskEstimatedEffort 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-182">PidLidTaskEstimatedEffort Canonical Property</span></span>](pidlidtaskestimatedeffort-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-183">PidLidTaskFRecurring 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-183">PidLidTaskFRecurring Canonical Property</span></span>](pidlidtaskfrecurring-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-184">PidLidTaskStartDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-184">PidLidTaskStartDate Canonical Property</span></span>](pidlidtaskstartdate-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-185">PidLidTaskStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-185">PidLidTaskStatus Canonical Property</span></span>](pidlidtaskstatus-canonical-property.md)
    
<span data-ttu-id="f7fb2-186">**PS_INTERNET_HEADERS**命名空间中的命名的属性如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7fb2-186">Named properties in the **PS_INTERNET_HEADERS** namespace are the following:</span></span> 
  
- [<span data-ttu-id="f7fb2-187">PidTagInternetReturnPath 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-187">PidTagInternetReturnPath Canonical Property</span></span>](pidtaginternetreturnpath-canonical-property.md)
    
<span data-ttu-id="f7fb2-188">**PSETID_Log**命名空间中的命名的属性如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7fb2-188">Named properties in the **PSETID_Log** namespace are the following:</span></span> 
  
- [<span data-ttu-id="f7fb2-189">PidLidLogDuration 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-189">PidLidLogDuration Canonical Property</span></span>](pidlidlogduration-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-190">PidLidLogEnd 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-190">PidLidLogEnd Canonical Property</span></span>](pidlidlogend-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-191">PidLidLogStart 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-191">PidLidLogStart Canonical Property</span></span>](pidlidlogstart-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-192">PidLidLogType 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-192">PidLidLogType Canonical Property</span></span>](pidlidlogtype-canonical-property.md)
    
<span data-ttu-id="f7fb2-193">**PS_PUBLIC_STRINGS**命名空间中的命名的属性如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7fb2-193">Named properties in the **PS_PUBLIC_STRINGS** namespace are the following:</span></span> 
  
- [<span data-ttu-id="f7fb2-194">PidNameKeywords 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-194">PidNameKeywords Canonical Property</span></span>](pidnamekeywords-canonical-property.md)
    
- [<span data-ttu-id="f7fb2-195">PidNameExchangeJunkEmailMoveStamp 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7fb2-195">PidNameExchangeJunkEmailMoveStamp Canonical Property</span></span>](pidnameexchangejunkemailmovestamp-canonical-property.md)
    
## <a name="see-also"></a><span data-ttu-id="f7fb2-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7fb2-196">See also</span></span>



[<span data-ttu-id="f7fb2-197">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="f7fb2-197">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="f7fb2-198">确定 Outlook 是否仅下载邮件头</span><span class="sxs-lookup"><span data-stu-id="f7fb2-198">Determine if Outlook Downloaded Only the Header of a Message</span></span>](how-to-determine-if-outlook-downloaded-only-the-header-of-a-message.md)
  
[<span data-ttu-id="f7fb2-199">获取联系人项的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="f7fb2-199">Get the Email Address of a Contact Item</span></span>](how-to-get-the-email-address-of-a-contact-item.md)
  
[<span data-ttu-id="f7fb2-200">删除随邮件保存的自定义表单定义</span><span class="sxs-lookup"><span data-stu-id="f7fb2-200">Remove Custom Form Definition Saved With a Message</span></span>](how-to-remove-custom-form-definition-saved-with-a-message.md)

