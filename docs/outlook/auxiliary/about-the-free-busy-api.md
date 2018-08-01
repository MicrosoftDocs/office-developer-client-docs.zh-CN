---
title: 关于忙/闲 API
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 17c5e44e-ae56-8de7-3579-90171d996411
description: 忙/闲 API 允许邮件提供商提供指定的用户帐户指定的时间范围内的忙/闲状态信息。
ms.openlocfilehash: 8b1559173297fbde9930b6f8f7fbc74f176273da
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774169"
---
# <a name="about-the-freebusy-api"></a><span data-ttu-id="45943-103">关于忙/闲 API</span><span class="sxs-lookup"><span data-stu-id="45943-103">About the Free/Busy API</span></span>

<span data-ttu-id="45943-104">忙/闲 API 允许邮件提供商提供指定的用户帐户指定的时间范围内的忙/闲状态信息。</span><span class="sxs-lookup"><span data-stu-id="45943-104">The Free/Busy API allows mail providers to provide free/busy status information for specified user accounts within a specified time range.</span></span> <span data-ttu-id="45943-105">某一用户的日历时间的忙/闲状态是以下项之一:-外出、 忙碌、 暂定、 或免费。</span><span class="sxs-lookup"><span data-stu-id="45943-105">The free/busy status of a block of time on a user's calendar is one of the following: out-of-office, busy, tentative, or free.</span></span>
  
## <a name="create-a-freebusy-provider"></a><span data-ttu-id="45943-106">创建一个忙/闲提供程序</span><span class="sxs-lookup"><span data-stu-id="45943-106">Create a free/busy provider</span></span>

<span data-ttu-id="45943-107">若要提供向邮件用户的忙/闲信息，邮件提供商创建忙/闲提供程序，并将其注册与 Outlook。</span><span class="sxs-lookup"><span data-stu-id="45943-107">To provide free/busy information to mail users, a mail provider creates a free/busy provider and registers it with Outlook.</span></span> <span data-ttu-id="45943-108">忙/闲提供程序必须实现以下接口。</span><span class="sxs-lookup"><span data-stu-id="45943-108">The free/busy provider must implement the following interfaces.</span></span> <span data-ttu-id="45943-109">请注意，这些接口中的成员数不受支持，并且必须返回指定的返回值。</span><span class="sxs-lookup"><span data-stu-id="45943-109">Note that a number of members in these interfaces are not supported and must return the specified return values.</span></span> <span data-ttu-id="45943-110">具体而言，忙/闲 API 不支持写访问权忙/闲信息和委派对帐户的访问。</span><span class="sxs-lookup"><span data-stu-id="45943-110">In particular, the Free/Busy API does not support write access to free/busy information and delegate access to accounts.</span></span>
  
- <span data-ttu-id="45943-111">[IFreeBusySupport](ifreebusysupport.md) — 此接口支持接口访问指定的用户的忙/闲数据的规范。</span><span class="sxs-lookup"><span data-stu-id="45943-111">[IFreeBusySupport](ifreebusysupport.md) —This interface supports specification of interfaces that access free/busy data for specified users.</span></span> <span data-ttu-id="45943-112">它使用[FBUser](fbuser.md)标识用户。</span><span class="sxs-lookup"><span data-stu-id="45943-112">It uses [FBUser](fbuser.md) to identify a user.</span></span> 
    
- <span data-ttu-id="45943-113">[IFreeBusyData](ifreebusydata.md) — 此接口获取和设置给定用户的时间范围并返回枚举忙/闲此时间范围内的数据块界面。</span><span class="sxs-lookup"><span data-stu-id="45943-113">[IFreeBusyData](ifreebusydata.md) —This interface gets and sets a time range for a given user and returns an interface for enumerating free/busy blocks of data within this time range.</span></span> <span data-ttu-id="45943-114">它使用相对时间来获取和设置此时间范围。</span><span class="sxs-lookup"><span data-stu-id="45943-114">It uses relative time to get and set this time range.</span></span> <span data-ttu-id="45943-115">有关详细信息，请参阅[使用相对时间访问忙/闲数据](how-to-use-relative-time-to-access-free-busy-data.md)。</span><span class="sxs-lookup"><span data-stu-id="45943-115">For more information, see [Use relative time to access free/busy data](how-to-use-relative-time-to-access-free-busy-data.md).</span></span>
    
- <span data-ttu-id="45943-116">[IEnumFBBlock](ienumfbblock.md) — 此接口支持访问和枚举忙/闲时间范围内的用户数据块。</span><span class="sxs-lookup"><span data-stu-id="45943-116">[IEnumFBBlock](ienumfbblock.md) —This interface supports accessing and enumerating free/busy blocks of data for a user within a time range.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="45943-117">枚举包含指示在用户的日历上，在 （指定[IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md)） 的时间范围内的时间段内的忙/闲状态的忙/闲块。</span><span class="sxs-lookup"><span data-stu-id="45943-117">An enumeration contains free/busy blocks that indicate the free/busy status of periods of time on a user's calendar, within a time range (specified by [IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md)).</span></span> <span data-ttu-id="45943-118">在日历上，如约会和会议请求项目表单块枚举中。</span><span class="sxs-lookup"><span data-stu-id="45943-118">Items on a calendar, such as appointments and meeting requests, form blocks in the enumeration.</span></span> <span data-ttu-id="45943-119">紧邻日历上的另一且具有相同的忙/闲状态的项目组合到一个单个块的窗体。</span><span class="sxs-lookup"><span data-stu-id="45943-119">Items that are adjacent to one another on the calendar and have the same free/busy status are combined to form one single block.</span></span> <span data-ttu-id="45943-120">一段空闲时期的日历时间也形成块。</span><span class="sxs-lookup"><span data-stu-id="45943-120">A free period of time on a calendar also forms a block.</span></span> <span data-ttu-id="45943-121">因此，无枚举中的两个连续块会具有相同的忙/闲状态。</span><span class="sxs-lookup"><span data-stu-id="45943-121">Therefore, no two consecutive blocks in an enumeration would have the same free/busy status.</span></span> <span data-ttu-id="45943-122">这些块不时间重叠。</span><span class="sxs-lookup"><span data-stu-id="45943-122">These blocks do not overlap in time.</span></span> <span data-ttu-id="45943-123">当日历上存在重叠的项目时，Outlook 将合并这些项目以形成枚举基于以下优先顺序中的非重叠忙/闲基块:-外出、 忙碌、 暂定。</span><span class="sxs-lookup"><span data-stu-id="45943-123">When there are overlapping items on a calendar, Outlook merges these items to form non-overlapping free/busy blocks in the enumeration based on this order of precedence: out-of-office, busy, tentative.</span></span> 
  
<span data-ttu-id="45943-124">若要注册与 Outlook 的忙/闲提供程序，邮件提供商应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="45943-124">To register the free/busy provider with Outlook, the mail provider should do the following:</span></span>
  
1. <span data-ttu-id="45943-125">将忙/闲提供程序注册 COM，提供允许访问提供程序的实现**IFreeBusySupport**CLSID。</span><span class="sxs-lookup"><span data-stu-id="45943-125">Register the free/busy provider with COM, providing a CLSID that allows access to the provider's implementation of **IFreeBusySupport**.</span></span> 
    
2. <span data-ttu-id="45943-126">让知道的忙/闲提供程序存在通过设置以下项的 Outlook (其中`<xx.x>`表示的 Outlook 版本) 系统注册表中：</span><span class="sxs-lookup"><span data-stu-id="45943-126">Let Outlook know that the free/busy provider exists by setting the following key (where `<xx.x>` represents the version of Outlook) in the system registry:</span></span> 
    
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\<xx.x>\Outlook\SchedulingInformation\FreeBusySupport`
    
   <span data-ttu-id="45943-127">例如，如果 SMTP 传输提供程序，可提供程序注册到 Microsoft Outlook 2010 中，设置以下项下表中的数据：</span><span class="sxs-lookup"><span data-stu-id="45943-127">For example, if the transport provider is SMTP, to register the provider with Microsoft Outlook 2010, set the following key to the data in the following table:</span></span> 
    
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook\SchedulingInformation\FreeBusySupport`
    
   |<span data-ttu-id="45943-128">名称</span><span class="sxs-lookup"><span data-stu-id="45943-128">Name</span></span> |<span data-ttu-id="45943-129">类型</span><span class="sxs-lookup"><span data-stu-id="45943-129">Type</span></span> |<span data-ttu-id="45943-130">值</span><span class="sxs-lookup"><span data-stu-id="45943-130">Value</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="45943-131">SMTP</span><span class="sxs-lookup"><span data-stu-id="45943-131">SMTP</span></span>  |<span data-ttu-id="45943-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="45943-132">REG_SZ</span></span>  |<span data-ttu-id="45943-133">{CLSID 各自实现 IFreeBusySupport}</span><span class="sxs-lookup"><span data-stu-id="45943-133">{CLSID for respective implementation of IFreeBusySupport}</span></span>  |
   
   <span data-ttu-id="45943-134">在此方案中，Outlook 共同创建 COM 类，并使用它来检索任何 SMTP 邮件用户的忙/闲信息。</span><span class="sxs-lookup"><span data-stu-id="45943-134">In this scenario, Outlook co-creates the COM class and uses it to retrieve free/busy information for any SMTP mail users.</span></span>
    
<span data-ttu-id="45943-135">若要支持使用之外的 SMTP 地址条目类型的通讯簿和传输提供程序，相应地更改*名称*。</span><span class="sxs-lookup"><span data-stu-id="45943-135">To support an address book and transport provider that use an address entry type other than SMTP, change the  *Name* accordingly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="45943-136">安装过程中，应检查忙/闲提供程序，是否的注册表设置相同的地址条目类型已存在。</span><span class="sxs-lookup"><span data-stu-id="45943-136">During installation, free/busy providers should check whether a registry setting for the the same address entry type already exists.</span></span> <span data-ttu-id="45943-137">如果是这样的忙/闲提供程序应覆盖的当前提供程序的地址条目类型，并还原到该提供程序，它卸载时。</span><span class="sxs-lookup"><span data-stu-id="45943-137">If it does, the free/busy provider should overwrite the current provider for that address entry type, and restore to that provider when it uninstalls.</span></span> <span data-ttu-id="45943-138">但是，如果用户具有安装相同的地址条目类型的多个忙/闲提供程序，用户应卸载这些提供程序安装的相反的顺序 （即，始终卸载的最新的提供程序）。</span><span class="sxs-lookup"><span data-stu-id="45943-138">However, if a user has installed more than one free/busy provider for the same address entry type, the user should uninstall these providers in the reverse order as installation (that is, always uninstall the latest provider).</span></span> <span data-ttu-id="45943-139">否则，注册表可能会导致的提供程序已卸载。</span><span class="sxs-lookup"><span data-stu-id="45943-139">Otherwise, the registry may point to a provider that has already been uninstalled.</span></span> 
  
## <a name="api-components"></a><span data-ttu-id="45943-140">API 组件</span><span class="sxs-lookup"><span data-stu-id="45943-140">API components</span></span>

<span data-ttu-id="45943-141">忙/闲 API 包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="45943-141">The Free/Busy API includes the following components:</span></span>
  
### <a name="definitions"></a><span data-ttu-id="45943-142">定义</span><span class="sxs-lookup"><span data-stu-id="45943-142">Definitions</span></span>

- [<span data-ttu-id="45943-143">常量 (忙/闲 API)</span><span class="sxs-lookup"><span data-stu-id="45943-143">Constants (Free/busy API)</span></span>](constants-free-busy-api.md)
    
### <a name="data-types"></a><span data-ttu-id="45943-144">数据类型</span><span class="sxs-lookup"><span data-stu-id="45943-144">Data types</span></span>

- [<span data-ttu-id="45943-145">FBBlock_1</span><span class="sxs-lookup"><span data-stu-id="45943-145">FBBlock_1</span></span>](fbblock_1.md)
- [<span data-ttu-id="45943-146">FBStatus</span><span class="sxs-lookup"><span data-stu-id="45943-146">FBStatus</span></span>](fbstatus.md)
- [<span data-ttu-id="45943-147">FBUser</span><span class="sxs-lookup"><span data-stu-id="45943-147">FBUser</span></span>](fbuser.md)
    
### <a name="interfaces"></a><span data-ttu-id="45943-148">接口</span><span class="sxs-lookup"><span data-stu-id="45943-148">Interfaces</span></span>

- [<span data-ttu-id="45943-149">IEnumFBBlock</span><span class="sxs-lookup"><span data-stu-id="45943-149">IEnumFBBlock</span></span>](ienumfbblock.md)
- [<span data-ttu-id="45943-150">IFreeBusyData</span><span class="sxs-lookup"><span data-stu-id="45943-150">IFreeBusyData</span></span>](ifreebusydata.md)
- [<span data-ttu-id="45943-151">IFreeBusySupport</span><span class="sxs-lookup"><span data-stu-id="45943-151">IFreeBusySupport</span></span>](ifreebusysupport.md)
    

