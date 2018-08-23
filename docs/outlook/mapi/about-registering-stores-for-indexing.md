---
title: 关于注册用于建立索引的存储区
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: dd2aa06a-96e8-1291-18b5-fc3c40b74e4d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 195812f53c4c0aaf20e4ed6e215d15b0295c9a07
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584182"
---
# <a name="about-registering-stores-for-indexing"></a><span data-ttu-id="3e910-103">关于注册用于建立索引的存储区</span><span class="sxs-lookup"><span data-stu-id="3e910-103">About Registering Stores for Indexing</span></span>

  
  
<span data-ttu-id="3e910-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3e910-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3e910-105">本主题是特定于 Microsoft Office Outlook 2007 中的即时搜索。</span><span class="sxs-lookup"><span data-stu-id="3e910-105">This topic is specific to Instant Search in Microsoft Office Outlook 2007.</span></span>
  
<span data-ttu-id="3e910-106">即时搜索允许您快速查找在 Outlook 中的项目。</span><span class="sxs-lookup"><span data-stu-id="3e910-106">Instant Search lets you quickly find items in Outlook.</span></span> <span data-ttu-id="3e910-107">它使用 Windows 桌面搜索的组件。</span><span class="sxs-lookup"><span data-stu-id="3e910-107">It uses components of Windows Desktop Search.</span></span>
  
<span data-ttu-id="3e910-108">MAPI 协议处理程序检查 Windows 注册表中以便它应该索引搜索目的的存储。</span><span class="sxs-lookup"><span data-stu-id="3e910-108">The MAPI Protocol Handler checks the Windows registry for stores that it should index for search purposes.</span></span> <span data-ttu-id="3e910-109">想要编制索引的存储提供程序必须在 Windows 注册表中注册。</span><span class="sxs-lookup"><span data-stu-id="3e910-109">Store providers that want to be indexed must be registered in the Windows registry.</span></span>
  
<span data-ttu-id="3e910-110">默认情况下，Windows 桌面搜索将以下四种存储提供程序添加到 Windows 注册表以允许索引：</span><span class="sxs-lookup"><span data-stu-id="3e910-110">By default, Windows Desktop Search adds the following four types of store providers to the Windows registry to allow indexing:</span></span>
  
- <span data-ttu-id="3e910-111">存储个人文件夹文件 (。PST)。</span><span class="sxs-lookup"><span data-stu-id="3e910-111">Store for Personal Folders files (.PST).</span></span>
    
-  <span data-ttu-id="3e910-112">Microsoft Exchange 存储中，包括任何脱机文件夹文件 (.ost)。</span><span class="sxs-lookup"><span data-stu-id="3e910-112">Microsoft Exchange store, including any Offline Folder files (.ost).</span></span> 
    
-  <span data-ttu-id="3e910-113">公用文件夹存储区。</span><span class="sxs-lookup"><span data-stu-id="3e910-113">Store for public folders.</span></span> 
    
-  <span data-ttu-id="3e910-114">Microsoft Office Outlook Connector for MSN 存储区。</span><span class="sxs-lookup"><span data-stu-id="3e910-114">Store for Microsoft Office Outlook Connector for MSN.</span></span> 
    
 <span data-ttu-id="3e910-115">想要编制索引的第三方存储提供程序必须在 Windows 注册表中进行注册。</span><span class="sxs-lookup"><span data-stu-id="3e910-115">Third-party store providers that want to be indexed must register themselves in the Windows registry.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3e910-116">管理员和用户可以使用组策略设置阻止 Windows 桌面搜索索引 Outlook 项目。</span><span class="sxs-lookup"><span data-stu-id="3e910-116">Administrators and users can use a Group Policy setting to prevent Windows Desktop Search from indexing Outlook items.</span></span> <span data-ttu-id="3e910-117">有关详细信息，请参阅[扩展 Windows 桌面搜索](http://msdn.microsoft.com/library/2eab146a-8516-4b95-b73c-ca7f980ba233%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3e910-117">For more information, see [Extending Windows Desktop Search](http://msdn.microsoft.com/library/2eab146a-8516-4b95-b73c-ca7f980ba233%28Office.15%29.aspx).</span></span> 
  
## <a name="registry-keys"></a><span data-ttu-id="3e910-118">注册表项</span><span class="sxs-lookup"><span data-stu-id="3e910-118">Registry Keys</span></span>

<span data-ttu-id="3e910-119">计算机上，要编制索引的所有存储提供程序必须只有一个 Windows 注册表中的以下三个注册表项下都注册。</span><span class="sxs-lookup"><span data-stu-id="3e910-119">On a computer, all store providers that want to be indexed must be registered under only one of the following three registry keys in the Windows registry.</span></span> <span data-ttu-id="3e910-120">每个按以下顺序这些项下查找 MAPI 协议处理程序：</span><span class="sxs-lookup"><span data-stu-id="3e910-120">The MAPI Protocol Handler looks under each of these keys in the following order:</span></span>
  
1. <span data-ttu-id="3e910-121">[HKLM] \Software\Policies\Microsoft\Windows\Windows Search\\</span><span class="sxs-lookup"><span data-stu-id="3e910-121">[HKLM]\Software\Policies\Microsoft\Windows\Windows Search\\</span></span>
    
2. <span data-ttu-id="3e910-122">[HKLM] \Software\Microsoft\Windows\Windows Search\Preferences\\</span><span class="sxs-lookup"><span data-stu-id="3e910-122">[HKLM]\Software\Microsoft\Windows\Windows Search\Preferences\\</span></span>
    
3. <span data-ttu-id="3e910-123">[HKCU] \Software\Microsoft\Windows\Windows Search\Preferences\\</span><span class="sxs-lookup"><span data-stu-id="3e910-123">[HKCU]\Software\Microsoft\Windows\Windows Search\Preferences\\</span></span>
    
 <span data-ttu-id="3e910-124">每个注册表项下的值对应于将编制索引的存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="3e910-124">Each value under the key corresponds to a store provider that would be indexed.</span></span> <span data-ttu-id="3e910-125">全局唯一标识符 (GUID) 的存储提供程序，其中的类型为**DWORD**具有 0x00000001 的十六进制值的值的名称。</span><span class="sxs-lookup"><span data-stu-id="3e910-125">The name of the value is the Globally Unique Identifier (GUID) of the store provider, which is of the type **DWORD** and has the hexadecimal value 0x00000001.</span></span> 
  
## <a name="guids-for-store-providers"></a><span data-ttu-id="3e910-126">存储提供程序的 Guid</span><span class="sxs-lookup"><span data-stu-id="3e910-126">GUIDs for Store Providers</span></span>

<span data-ttu-id="3e910-127">MAPI 属性**[PR_MDB_PROVIDER](pidtagstoreprovider-canonical-property.md)** 指定的 MAPI 存储区的 GUID。</span><span class="sxs-lookup"><span data-stu-id="3e910-127">The MAPI property **[PR_MDB_PROVIDER](pidtagstoreprovider-canonical-property.md)** specifies the GUID of a MAPI store.</span></span> <span data-ttu-id="3e910-128">下表中描述了 Outlook 索引的存储提供程序的 Guid。</span><span class="sxs-lookup"><span data-stu-id="3e910-128">The GUIDs for the store providers that Outlook indexes are described in the following table.</span></span> 
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="3e910-129">**存储提供程序类型**</span><span class="sxs-lookup"><span data-stu-id="3e910-129">**Type of Store Provider**</span></span> <br/> |<span data-ttu-id="3e910-130">**GUID**</span><span class="sxs-lookup"><span data-stu-id="3e910-130">**GUID**</span></span> <br/> |<span data-ttu-id="3e910-131">**备注**</span><span class="sxs-lookup"><span data-stu-id="3e910-131">**Notes**</span></span> <br/> |
|<span data-ttu-id="3e910-132">个人文件夹文件 (。PST)</span><span class="sxs-lookup"><span data-stu-id="3e910-132">Personal Folders files (.PST)</span></span>  <br/> |<span data-ttu-id="3e910-133">{4154494E-BFF9-01B8-00AA-0037D96E0000}</span><span class="sxs-lookup"><span data-stu-id="3e910-133">{4154494E-BFF9-01B8-00AA-0037D96E0000}</span></span>  <br/> |<span data-ttu-id="3e910-134">GUID 为**MSPST_UID_PROVIDER**述公共头文件 mspst.h</span><span class="sxs-lookup"><span data-stu-id="3e910-134">GUID is documented in the public header file mspst.h as **MSPST_UID_PROVIDER**</span></span> <br/> |
|<span data-ttu-id="3e910-135">Exchange</span><span class="sxs-lookup"><span data-stu-id="3e910-135">Exchange</span></span>  <br/> |<span data-ttu-id="3e910-136">{C0A19454-7F29-1B10-A587-08002B2A2517}</span><span class="sxs-lookup"><span data-stu-id="3e910-136">{C0A19454-7F29-1B10-A587-08002B2A2517}</span></span>  <br/> |<span data-ttu-id="3e910-137">GUID 为**pbExchangeProviderPrimaryUserGuid**述公共头文件 edkmdb.h</span><span class="sxs-lookup"><span data-stu-id="3e910-137">GUID is documented in the public header file edkmdb.h as **pbExchangeProviderPrimaryUserGuid**</span></span> <br/> |
|<span data-ttu-id="3e910-138">公用文件夹</span><span class="sxs-lookup"><span data-stu-id="3e910-138">Public folders</span></span>  <br/> |<span data-ttu-id="3e910-139">{70fab278-f7af-cd11-9bc8-00aa002fc45a}</span><span class="sxs-lookup"><span data-stu-id="3e910-139">{70fab278-f7af-cd11-9bc8-00aa002fc45a}</span></span>  <br/> |<span data-ttu-id="3e910-140">GUID 为**pbExchangeProviderPublicGuid**述公共头文件 edkmdb.h</span><span class="sxs-lookup"><span data-stu-id="3e910-140">GUID is documented in the public header file edkmdb.h as **pbExchangeProviderPublicGuid**</span></span> <br/> |
|<span data-ttu-id="3e910-141">MSN 的 outlook Connector</span><span class="sxs-lookup"><span data-stu-id="3e910-141">Outlook Connector for MSN</span></span>  <br/> |<span data-ttu-id="3e910-142">{c34f5c97-eb05-bb4b-b199-2a7570ec7cf9}</span><span class="sxs-lookup"><span data-stu-id="3e910-142">{c34f5c97-eb05-bb4b-b199-2a7570ec7cf9}</span></span>  <br/> |<span data-ttu-id="3e910-143">无</span><span class="sxs-lookup"><span data-stu-id="3e910-143">None</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3e910-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e910-144">See also</span></span>



[<span data-ttu-id="3e910-145">关于存储区 API</span><span class="sxs-lookup"><span data-stu-id="3e910-145">About the Store API</span></span>](about-the-store-api.md)

