---
title: 关于忙/闲 API
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 17c5e44e-ae56-8de7-3579-90171d996411
description: 闲/忙 API 允许邮件提供程序为指定的时间范围内的指定用户帐户提供忙/闲状态信息。
ms.openlocfilehash: 1bcd191b57238771ede6f035216fe3997e82e03a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433757"
---
# <a name="about-the-freebusy-api"></a><span data-ttu-id="27f1a-103">关于忙/闲 API</span><span class="sxs-lookup"><span data-stu-id="27f1a-103">About the Free/Busy API</span></span>

<span data-ttu-id="27f1a-104">闲/忙 API 允许邮件提供程序为指定的时间范围内的指定用户帐户提供忙/闲状态信息。</span><span class="sxs-lookup"><span data-stu-id="27f1a-104">The Free/Busy API allows mail providers to provide free/busy status information for specified user accounts within a specified time range.</span></span> <span data-ttu-id="27f1a-105">用户日历上的一段时间的忙/闲状态为以下之一: 外出、忙碌、暂定或免费。</span><span class="sxs-lookup"><span data-stu-id="27f1a-105">The free/busy status of a block of time on a user's calendar is one of the following: out-of-office, busy, tentative, or free.</span></span>
  
## <a name="create-a-freebusy-provider"></a><span data-ttu-id="27f1a-106">创建忙/闲提供程序</span><span class="sxs-lookup"><span data-stu-id="27f1a-106">Create a free/busy provider</span></span>

<span data-ttu-id="27f1a-107">若要向邮件用户提供忙/闲信息, 邮件提供商将创建一个忙/闲提供商并将其注册到 Outlook。</span><span class="sxs-lookup"><span data-stu-id="27f1a-107">To provide free/busy information to mail users, a mail provider creates a free/busy provider and registers it with Outlook.</span></span> <span data-ttu-id="27f1a-108">忙/闲提供程序必须实现以下接口。</span><span class="sxs-lookup"><span data-stu-id="27f1a-108">The free/busy provider must implement the following interfaces.</span></span> <span data-ttu-id="27f1a-109">请注意, 这些接口中的多个成员不受支持, 必须返回指定的返回值。</span><span class="sxs-lookup"><span data-stu-id="27f1a-109">Note that a number of members in these interfaces are not supported and must return the specified return values.</span></span> <span data-ttu-id="27f1a-110">特别是, 闲/忙 API 不支持对忙/闲信息的写入访问权限, 并可委派帐户访问权限。</span><span class="sxs-lookup"><span data-stu-id="27f1a-110">In particular, the Free/Busy API does not support write access to free/busy information and delegate access to accounts.</span></span>
  
- <span data-ttu-id="27f1a-111">[IFreeBusySupport](ifreebusysupport.md) —此接口支持用于访问指定用户的忙/闲数据的接口的规范。</span><span class="sxs-lookup"><span data-stu-id="27f1a-111">[IFreeBusySupport](ifreebusysupport.md) —This interface supports specification of interfaces that access free/busy data for specified users.</span></span> <span data-ttu-id="27f1a-112">它使用[FBUser](fbuser.md)来标识用户。</span><span class="sxs-lookup"><span data-stu-id="27f1a-112">It uses [FBUser](fbuser.md) to identify a user.</span></span> 
    
- <span data-ttu-id="27f1a-113">[IFreeBusyData](ifreebusydata.md) —此接口获取并设置给定用户的时间范围, 并返回用于枚举此时间范围内的忙/闲数据块的接口。</span><span class="sxs-lookup"><span data-stu-id="27f1a-113">[IFreeBusyData](ifreebusydata.md) —This interface gets and sets a time range for a given user and returns an interface for enumerating free/busy blocks of data within this time range.</span></span> <span data-ttu-id="27f1a-114">它使用相对于获取和设置此时间范围的相对时间。</span><span class="sxs-lookup"><span data-stu-id="27f1a-114">It uses relative time to get and set this time range.</span></span> <span data-ttu-id="27f1a-115">有关详细信息, 请参阅[使用相对时间访问忙/闲数据](how-to-use-relative-time-to-access-free-busy-data.md)。</span><span class="sxs-lookup"><span data-stu-id="27f1a-115">For more information, see [Use relative time to access free/busy data](how-to-use-relative-time-to-access-free-busy-data.md).</span></span>
    
- <span data-ttu-id="27f1a-116">[IEnumFBBlock](ienumfbblock.md) —此接口支持在某个时间范围内访问和枚举用户的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="27f1a-116">[IEnumFBBlock](ienumfbblock.md) —This interface supports accessing and enumerating free/busy blocks of data for a user within a time range.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="27f1a-117">枚举包含用于指示用户日历上某个时间范围内 (由[IFreeBusyData:: EnumBlocks](ifreebusydata-enumblocks.md)) 指定的时间段内的忙/闲状态的忙/闲块。</span><span class="sxs-lookup"><span data-stu-id="27f1a-117">An enumeration contains free/busy blocks that indicate the free/busy status of periods of time on a user's calendar, within a time range (specified by [IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md)).</span></span> <span data-ttu-id="27f1a-118">日历中的项目 (如约会和会议请求) 枚举中的窗体块。</span><span class="sxs-lookup"><span data-stu-id="27f1a-118">Items on a calendar, such as appointments and meeting requests, form blocks in the enumeration.</span></span> <span data-ttu-id="27f1a-119">在日历上彼此相邻的项目和具有相同的忙/闲状态的项目组合在一起形成一个单独的块。</span><span class="sxs-lookup"><span data-stu-id="27f1a-119">Items that are adjacent to one another on the calendar and have the same free/busy status are combined to form one single block.</span></span> <span data-ttu-id="27f1a-120">日历上的一段空闲时间也会形成一个块。</span><span class="sxs-lookup"><span data-stu-id="27f1a-120">A free period of time on a calendar also forms a block.</span></span> <span data-ttu-id="27f1a-121">因此, 枚举中的任何两个连续块都不会具有相同的忙/闲状态。</span><span class="sxs-lookup"><span data-stu-id="27f1a-121">Therefore, no two consecutive blocks in an enumeration would have the same free/busy status.</span></span> <span data-ttu-id="27f1a-122">这些块不会及时重叠。</span><span class="sxs-lookup"><span data-stu-id="27f1a-122">These blocks do not overlap in time.</span></span> <span data-ttu-id="27f1a-123">当日历上有重叠项目时, Outlook 将基于此优先级顺序, 合并这些项目以形成枚举中不重叠的忙/闲块: 外出、忙碌、暂定。</span><span class="sxs-lookup"><span data-stu-id="27f1a-123">When there are overlapping items on a calendar, Outlook merges these items to form non-overlapping free/busy blocks in the enumeration based on this order of precedence: out-of-office, busy, tentative.</span></span> 
  
<span data-ttu-id="27f1a-124">若要在 Outlook 中注册闲/忙提供商, 邮件提供商应执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="27f1a-124">To register the free/busy provider with Outlook, the mail provider should do the following:</span></span>
  
1. <span data-ttu-id="27f1a-125">向 COM 注册闲/忙提供程序, 提供一个 CLSID, 以允许访问提供程序对**IFreeBusySupport**的实现。</span><span class="sxs-lookup"><span data-stu-id="27f1a-125">Register the free/busy provider with COM, providing a CLSID that allows access to the provider's implementation of **IFreeBusySupport**.</span></span> 
    
2. <span data-ttu-id="27f1a-126">通过在系统注册表中设置以下项 (其中`<xx.x>`表示 Outlook 的版本), 让 Outlook 知道闲/忙提供程序存在:</span><span class="sxs-lookup"><span data-stu-id="27f1a-126">Let Outlook know that the free/busy provider exists by setting the following key (where `<xx.x>` represents the version of Outlook) in the system registry:</span></span> 
    
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\<xx.x>\Outlook\SchedulingInformation\FreeBusySupport`
    
   <span data-ttu-id="27f1a-127">例如, 如果传输提供程序是 SMTP, 若要向 Microsoft Outlook 2010 注册提供程序, 请将以下注册表项设置为下表中的数据:</span><span class="sxs-lookup"><span data-stu-id="27f1a-127">For example, if the transport provider is SMTP, to register the provider with Microsoft Outlook 2010, set the following key to the data in the following table:</span></span> 
    
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook\SchedulingInformation\FreeBusySupport`
    
   |<span data-ttu-id="27f1a-128">名称</span><span class="sxs-lookup"><span data-stu-id="27f1a-128">Name</span></span> |<span data-ttu-id="27f1a-129">类型</span><span class="sxs-lookup"><span data-stu-id="27f1a-129">Type</span></span> |<span data-ttu-id="27f1a-130">值</span><span class="sxs-lookup"><span data-stu-id="27f1a-130">Value</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="27f1a-131">SMTP</span><span class="sxs-lookup"><span data-stu-id="27f1a-131">SMTP</span></span>  |<span data-ttu-id="27f1a-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="27f1a-132">REG_SZ</span></span>  |<span data-ttu-id="27f1a-133">{CLSID for IFreeBusySupport 的各个实现}</span><span class="sxs-lookup"><span data-stu-id="27f1a-133">{CLSID for respective implementation of IFreeBusySupport}</span></span>  |
   
   <span data-ttu-id="27f1a-134">在这种情况下, Outlook 将共同创建 COM 类, 并使用它来检索任何 SMTP 邮件用户的忙/闲信息。</span><span class="sxs-lookup"><span data-stu-id="27f1a-134">In this scenario, Outlook co-creates the COM class and uses it to retrieve free/busy information for any SMTP mail users.</span></span>
    
<span data-ttu-id="27f1a-135">若要支持使用 SMTP 之外的地址条目类型的通讯簿和传输提供程序, 请相应地更改*名称*。</span><span class="sxs-lookup"><span data-stu-id="27f1a-135">To support an address book and transport provider that use an address entry type other than SMTP, change the  *Name* accordingly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="27f1a-136">在安装过程中, 忙/闲提供商应检查是否已存在相同地址条目类型的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="27f1a-136">During installation, free/busy providers should check whether a registry setting for the the same address entry type already exists.</span></span> <span data-ttu-id="27f1a-137">如果是这样, 则忙/闲提供程序应覆盖该地址条目类型的当前提供程序, 并在卸载时还原到该提供程序。</span><span class="sxs-lookup"><span data-stu-id="27f1a-137">If it does, the free/busy provider should overwrite the current provider for that address entry type, and restore to that provider when it uninstalls.</span></span> <span data-ttu-id="27f1a-138">但是, 如果用户为同一地址条目类型安装了多个忙/闲提供程序, 则用户应按相反的顺序卸载这些提供程序 (即, 始终卸载最新的提供程序)。</span><span class="sxs-lookup"><span data-stu-id="27f1a-138">However, if a user has installed more than one free/busy provider for the same address entry type, the user should uninstall these providers in the reverse order as installation (that is, always uninstall the latest provider).</span></span> <span data-ttu-id="27f1a-139">否则, 注册表可能指向已卸载的提供程序。</span><span class="sxs-lookup"><span data-stu-id="27f1a-139">Otherwise, the registry may point to a provider that has already been uninstalled.</span></span> 
  
## <a name="api-components"></a><span data-ttu-id="27f1a-140">API 组件</span><span class="sxs-lookup"><span data-stu-id="27f1a-140">API components</span></span>

<span data-ttu-id="27f1a-141">忙/闲 API 包括以下组件:</span><span class="sxs-lookup"><span data-stu-id="27f1a-141">The Free/Busy API includes the following components:</span></span>
  
### <a name="definitions"></a><span data-ttu-id="27f1a-142">定义</span><span class="sxs-lookup"><span data-stu-id="27f1a-142">Definitions</span></span>

- [<span data-ttu-id="27f1a-143">常量 (忙/闲 API)</span><span class="sxs-lookup"><span data-stu-id="27f1a-143">Constants (Free/busy API)</span></span>](constants-free-busy-api.md)
    
### <a name="data-types"></a><span data-ttu-id="27f1a-144">数据类型</span><span class="sxs-lookup"><span data-stu-id="27f1a-144">Data types</span></span>

- [<span data-ttu-id="27f1a-145">FBBlock_1</span><span class="sxs-lookup"><span data-stu-id="27f1a-145">FBBlock_1</span></span>](fbblock_1.md)
- [<span data-ttu-id="27f1a-146">FBStatus</span><span class="sxs-lookup"><span data-stu-id="27f1a-146">FBStatus</span></span>](fbstatus.md)
- [<span data-ttu-id="27f1a-147">FBUser</span><span class="sxs-lookup"><span data-stu-id="27f1a-147">FBUser</span></span>](fbuser.md)
    
### <a name="interfaces"></a><span data-ttu-id="27f1a-148">接口</span><span class="sxs-lookup"><span data-stu-id="27f1a-148">Interfaces</span></span>

- [<span data-ttu-id="27f1a-149">IEnumFBBlock</span><span class="sxs-lookup"><span data-stu-id="27f1a-149">IEnumFBBlock</span></span>](ienumfbblock.md)
- [<span data-ttu-id="27f1a-150">IFreeBusyData</span><span class="sxs-lookup"><span data-stu-id="27f1a-150">IFreeBusyData</span></span>](ifreebusydata.md)
- [<span data-ttu-id="27f1a-151">IFreeBusySupport</span><span class="sxs-lookup"><span data-stu-id="27f1a-151">IFreeBusySupport</span></span>](ifreebusysupport.md)
    

