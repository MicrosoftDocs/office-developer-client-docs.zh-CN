---
title: 关于忙/闲 API
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 17c5e44e-ae56-8de7-3579-90171d996411
description: 忙/闲 API 允许邮件提供程序提供指定时间范围内指定用户帐户的忙/闲状态信息。
ms.openlocfilehash: 1bcd191b57238771ede6f035216fe3997e82e03a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433757"
---
# <a name="about-the-freebusy-api"></a><span data-ttu-id="aba5f-103">关于忙/闲 API</span><span class="sxs-lookup"><span data-stu-id="aba5f-103">About the Free/Busy API</span></span>

<span data-ttu-id="aba5f-104">忙/闲 API 允许邮件提供程序提供指定时间范围内指定用户帐户的忙/闲状态信息。</span><span class="sxs-lookup"><span data-stu-id="aba5f-104">The Free/Busy API allows mail providers to provide free/busy status information for specified user accounts within a specified time range.</span></span> <span data-ttu-id="aba5f-105">用户日历上某一个时间块的忙/闲状态如下：外出、忙碌、暂定或空闲。</span><span class="sxs-lookup"><span data-stu-id="aba5f-105">The free/busy status of a block of time on a user's calendar is one of the following: out-of-office, busy, tentative, or free.</span></span>
  
## <a name="create-a-freebusy-provider"></a><span data-ttu-id="aba5f-106">创建忙/闲提供程序</span><span class="sxs-lookup"><span data-stu-id="aba5f-106">Create a free/busy provider</span></span>

<span data-ttu-id="aba5f-107">为了向邮件用户提供忙/闲信息，邮件提供程序会创建一个忙/闲提供程序，并注册Outlook。</span><span class="sxs-lookup"><span data-stu-id="aba5f-107">To provide free/busy information to mail users, a mail provider creates a free/busy provider and registers it with Outlook.</span></span> <span data-ttu-id="aba5f-108">忙/闲提供程序必须实现以下接口。</span><span class="sxs-lookup"><span data-stu-id="aba5f-108">The free/busy provider must implement the following interfaces.</span></span> <span data-ttu-id="aba5f-109">请注意，这些接口中的许多成员不受支持，必须返回指定的返回值。</span><span class="sxs-lookup"><span data-stu-id="aba5f-109">Note that a number of members in these interfaces are not supported and must return the specified return values.</span></span> <span data-ttu-id="aba5f-110">特别是，忙/闲 API 不支持对忙/闲信息的写访问和委派对帐户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="aba5f-110">In particular, the Free/Busy API does not support write access to free/busy information and delegate access to accounts.</span></span>
  
- <span data-ttu-id="aba5f-111">[IFreeBusySupport](ifreebusysupport.md) - 此接口支持指定接口，这些接口访问指定用户的忙/闲数据。</span><span class="sxs-lookup"><span data-stu-id="aba5f-111">[IFreeBusySupport](ifreebusysupport.md) —This interface supports specification of interfaces that access free/busy data for specified users.</span></span> <span data-ttu-id="aba5f-112">它使用 [FBUser](fbuser.md) 标识用户。</span><span class="sxs-lookup"><span data-stu-id="aba5f-112">It uses [FBUser](fbuser.md) to identify a user.</span></span> 
    
- <span data-ttu-id="aba5f-113">[IFreeBusyData](ifreebusydata.md) - 此接口获取和设置给定用户的一个时间范围，并返回用于枚举此时间范围内的忙/闲数据块的接口。</span><span class="sxs-lookup"><span data-stu-id="aba5f-113">[IFreeBusyData](ifreebusydata.md) —This interface gets and sets a time range for a given user and returns an interface for enumerating free/busy blocks of data within this time range.</span></span> <span data-ttu-id="aba5f-114">它使用相对时间获取和设置此时间范围。</span><span class="sxs-lookup"><span data-stu-id="aba5f-114">It uses relative time to get and set this time range.</span></span> <span data-ttu-id="aba5f-115">有关详细信息，请参阅使用 [相对时间访问忙/闲数据](how-to-use-relative-time-to-access-free-busy-data.md)。</span><span class="sxs-lookup"><span data-stu-id="aba5f-115">For more information, see [Use relative time to access free/busy data](how-to-use-relative-time-to-access-free-busy-data.md).</span></span>
    
- <span data-ttu-id="aba5f-116">[IEnumFBBlock](ienumfbblock.md) - 此接口支持在一个时间范围内访问和枚举用户的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="aba5f-116">[IEnumFBBlock](ienumfbblock.md) —This interface supports accessing and enumerating free/busy blocks of data for a user within a time range.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="aba5f-117">枚举包含指示用户日历上时间段的忙/闲状态（在 [IFreeBusyData：：EnumBlocks](ifreebusydata-enumblocks.md) (指定的时间范围内）的忙/闲) 。</span><span class="sxs-lookup"><span data-stu-id="aba5f-117">An enumeration contains free/busy blocks that indicate the free/busy status of periods of time on a user's calendar, within a time range (specified by [IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md)).</span></span> <span data-ttu-id="aba5f-118">枚举中的日历项目（如约会和会议请求）表单块。</span><span class="sxs-lookup"><span data-stu-id="aba5f-118">Items on a calendar, such as appointments and meeting requests, form blocks in the enumeration.</span></span> <span data-ttu-id="aba5f-119">日历上彼此相邻且具有相同的忙/闲状态的项目组合在一起形成一个块。</span><span class="sxs-lookup"><span data-stu-id="aba5f-119">Items that are adjacent to one another on the calendar and have the same free/busy status are combined to form one single block.</span></span> <span data-ttu-id="aba5f-120">日历上的空闲时段也会形成一个块。</span><span class="sxs-lookup"><span data-stu-id="aba5f-120">A free period of time on a calendar also forms a block.</span></span> <span data-ttu-id="aba5f-121">因此，枚举中的两个连续块不会具有相同的忙/闲状态。</span><span class="sxs-lookup"><span data-stu-id="aba5f-121">Therefore, no two consecutive blocks in an enumeration would have the same free/busy status.</span></span> <span data-ttu-id="aba5f-122">这些块不会在时间上重叠。</span><span class="sxs-lookup"><span data-stu-id="aba5f-122">These blocks do not overlap in time.</span></span> <span data-ttu-id="aba5f-123">当日历上存在重叠项目时，Outlook合并这些项目以基于以下优先顺序在枚举中形成非重叠的忙/闲块：外出、忙碌、暂定。</span><span class="sxs-lookup"><span data-stu-id="aba5f-123">When there are overlapping items on a calendar, Outlook merges these items to form non-overlapping free/busy blocks in the enumeration based on this order of precedence: out-of-office, busy, tentative.</span></span> 
  
<span data-ttu-id="aba5f-124">若要向用户注册忙/Outlook，邮件提供程序应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aba5f-124">To register the free/busy provider with Outlook, the mail provider should do the following:</span></span>
  
1. <span data-ttu-id="aba5f-125">使用 COM 注册忙/闲提供程序，提供允许访问提供程序实现 **IFreeBusySupport** 的 CLSID。</span><span class="sxs-lookup"><span data-stu-id="aba5f-125">Register the free/busy provider with COM, providing a CLSID that allows access to the provider's implementation of **IFreeBusySupport**.</span></span> 
    
2. <span data-ttu-id="aba5f-126">请Outlook设置以下注册表项来了解忙/闲提供程序是否存在 (其中表示系统注册表中的Outlook) `<xx.x>` 版本：</span><span class="sxs-lookup"><span data-stu-id="aba5f-126">Let Outlook know that the free/busy provider exists by setting the following key (where `<xx.x>` represents the version of Outlook) in the system registry:</span></span> 
    
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\<xx.x>\Outlook\SchedulingInformation\FreeBusySupport`
    
   <span data-ttu-id="aba5f-127">例如，如果传输提供程序是 SMTP，若要向 Microsoft Outlook 2010，请对下表中的数据设置以下键：</span><span class="sxs-lookup"><span data-stu-id="aba5f-127">For example, if the transport provider is SMTP, to register the provider with Microsoft Outlook 2010, set the following key to the data in the following table:</span></span> 
    
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook\SchedulingInformation\FreeBusySupport`
    
   |<span data-ttu-id="aba5f-128">名称</span><span class="sxs-lookup"><span data-stu-id="aba5f-128">Name</span></span> |<span data-ttu-id="aba5f-129">类型</span><span class="sxs-lookup"><span data-stu-id="aba5f-129">Type</span></span> |<span data-ttu-id="aba5f-130">值</span><span class="sxs-lookup"><span data-stu-id="aba5f-130">Value</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="aba5f-131">SMTP</span><span class="sxs-lookup"><span data-stu-id="aba5f-131">SMTP</span></span>  |<span data-ttu-id="aba5f-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="aba5f-132">REG_SZ</span></span>  |<span data-ttu-id="aba5f-133">{CLSID，用于实现 IFreeBusySupport}</span><span class="sxs-lookup"><span data-stu-id="aba5f-133">{CLSID for respective implementation of IFreeBusySupport}</span></span>  |
   
   <span data-ttu-id="aba5f-134">在此方案中，Outlook COM 类并使用它检索任何 SMTP 邮件用户的忙/闲信息。</span><span class="sxs-lookup"><span data-stu-id="aba5f-134">In this scenario, Outlook co-creates the COM class and uses it to retrieve free/busy information for any SMTP mail users.</span></span>
    
<span data-ttu-id="aba5f-135">若要支持使用 SMTP 地址条目类型的通讯簿和传输提供程序，请相应地更改 *Name。*</span><span class="sxs-lookup"><span data-stu-id="aba5f-135">To support an address book and transport provider that use an address entry type other than SMTP, change the  *Name* accordingly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="aba5f-136">在安装过程中，忙/闲提供程序应检查同一地址条目类型的注册表设置是否已经存在。</span><span class="sxs-lookup"><span data-stu-id="aba5f-136">During installation, free/busy providers should check whether a registry setting for the the same address entry type already exists.</span></span> <span data-ttu-id="aba5f-137">如果是，则忙/闲提供程序应覆盖该地址条目类型的当前提供程序，在卸载时还原到该提供程序。</span><span class="sxs-lookup"><span data-stu-id="aba5f-137">If it does, the free/busy provider should overwrite the current provider for that address entry type, and restore to that provider when it uninstalls.</span></span> <span data-ttu-id="aba5f-138">但是，如果用户为同一地址输入类型安装了多个忙/闲提供程序，则用户应按安装 (（即始终卸载最新的提供程序）的相反顺序卸载这些提供程序) 。</span><span class="sxs-lookup"><span data-stu-id="aba5f-138">However, if a user has installed more than one free/busy provider for the same address entry type, the user should uninstall these providers in the reverse order as installation (that is, always uninstall the latest provider).</span></span> <span data-ttu-id="aba5f-139">否则，注册表可能指向已卸载的提供程序。</span><span class="sxs-lookup"><span data-stu-id="aba5f-139">Otherwise, the registry may point to a provider that has already been uninstalled.</span></span> 
  
## <a name="api-components"></a><span data-ttu-id="aba5f-140">API 组件</span><span class="sxs-lookup"><span data-stu-id="aba5f-140">API components</span></span>

<span data-ttu-id="aba5f-141">忙/闲 API 包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="aba5f-141">The Free/Busy API includes the following components:</span></span>
  
### <a name="definitions"></a><span data-ttu-id="aba5f-142">定义</span><span class="sxs-lookup"><span data-stu-id="aba5f-142">Definitions</span></span>

- [<span data-ttu-id="aba5f-143">常量 (忙/闲 API) </span><span class="sxs-lookup"><span data-stu-id="aba5f-143">Constants (Free/busy API)</span></span>](constants-free-busy-api.md)
    
### <a name="data-types"></a><span data-ttu-id="aba5f-144">数据类型</span><span class="sxs-lookup"><span data-stu-id="aba5f-144">Data types</span></span>

- [<span data-ttu-id="aba5f-145">FBBlock_1</span><span class="sxs-lookup"><span data-stu-id="aba5f-145">FBBlock_1</span></span>](fbblock_1.md)
- [<span data-ttu-id="aba5f-146">FBStatus</span><span class="sxs-lookup"><span data-stu-id="aba5f-146">FBStatus</span></span>](fbstatus.md)
- [<span data-ttu-id="aba5f-147">FBUser</span><span class="sxs-lookup"><span data-stu-id="aba5f-147">FBUser</span></span>](fbuser.md)
    
### <a name="interfaces"></a><span data-ttu-id="aba5f-148">接口</span><span class="sxs-lookup"><span data-stu-id="aba5f-148">Interfaces</span></span>

- [<span data-ttu-id="aba5f-149">IEnumFBBlock</span><span class="sxs-lookup"><span data-stu-id="aba5f-149">IEnumFBBlock</span></span>](ienumfbblock.md)
- [<span data-ttu-id="aba5f-150">IFreeBusyData</span><span class="sxs-lookup"><span data-stu-id="aba5f-150">IFreeBusyData</span></span>](ifreebusydata.md)
- [<span data-ttu-id="aba5f-151">IFreeBusySupport</span><span class="sxs-lookup"><span data-stu-id="aba5f-151">IFreeBusySupport</span></span>](ifreebusysupport.md)
    

