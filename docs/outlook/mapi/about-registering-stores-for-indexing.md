---
title: 关于注册用于编制索引的存储
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: dd2aa06a-96e8-1291-18b5-fc3c40b74e4d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96322d12b3b7b334b5f78f81910dcf34c3fc78e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321824"
---
# <a name="about-registering-stores-for-indexing"></a><span data-ttu-id="6e16e-103">关于注册用于编制索引的存储</span><span class="sxs-lookup"><span data-stu-id="6e16e-103">About Registering Stores for Indexing</span></span>

  
  
<span data-ttu-id="6e16e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6e16e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6e16e-105">本主题特定于 Microsoft Office Outlook 2007 中的 "即时搜索"。</span><span class="sxs-lookup"><span data-stu-id="6e16e-105">This topic is specific to Instant Search in Microsoft Office Outlook 2007.</span></span>
  
<span data-ttu-id="6e16e-106">即时搜索允许您在 Outlook 中快速查找项目。</span><span class="sxs-lookup"><span data-stu-id="6e16e-106">Instant Search lets you quickly find items in Outlook.</span></span> <span data-ttu-id="6e16e-107">它使用 Windows 桌面搜索的组件。</span><span class="sxs-lookup"><span data-stu-id="6e16e-107">It uses components of Windows Desktop Search.</span></span>
  
<span data-ttu-id="6e16e-108">MAPI 协议处理程序将检查 Windows 注册表, 以查找它应为搜索而编制索引的存储。</span><span class="sxs-lookup"><span data-stu-id="6e16e-108">The MAPI Protocol Handler checks the Windows registry for stores that it should index for search purposes.</span></span> <span data-ttu-id="6e16e-109">必须在 Windows 注册表中注册要编制索引的存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="6e16e-109">Store providers that want to be indexed must be registered in the Windows registry.</span></span>
  
<span data-ttu-id="6e16e-110">默认情况下, windows Desktop Search 将以下四种类型的存储提供程序添加到 Windows 注册表中, 以允许进行索引:</span><span class="sxs-lookup"><span data-stu-id="6e16e-110">By default, Windows Desktop Search adds the following four types of store providers to the Windows registry to allow indexing:</span></span>
  
- <span data-ttu-id="6e16e-111">存储个人文件夹文件 (。PST)。</span><span class="sxs-lookup"><span data-stu-id="6e16e-111">Store for Personal Folders files (.PST).</span></span>
    
-  <span data-ttu-id="6e16e-112">Microsoft Exchange 存储, 包括任何脱机文件夹文件 (.ost)。</span><span class="sxs-lookup"><span data-stu-id="6e16e-112">Microsoft Exchange store, including any Offline Folder files (.ost).</span></span> 
    
-  <span data-ttu-id="6e16e-113">公用文件夹的存储。</span><span class="sxs-lookup"><span data-stu-id="6e16e-113">Store for public folders.</span></span> 
    
-  <span data-ttu-id="6e16e-114">microsoft Office Outlook Connector for MSN 的存储。</span><span class="sxs-lookup"><span data-stu-id="6e16e-114">Store for Microsoft Office Outlook Connector for MSN.</span></span> 
    
 <span data-ttu-id="6e16e-115">要编制索引的第三方存储提供程序必须在 Windows 注册表中注册自己。</span><span class="sxs-lookup"><span data-stu-id="6e16e-115">Third-party store providers that want to be indexed must register themselves in the Windows registry.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6e16e-116">管理员和用户可以使用组策略设置阻止 Windows Desktop Search 对 Outlook 项目编制索引。</span><span class="sxs-lookup"><span data-stu-id="6e16e-116">Administrators and users can use a Group Policy setting to prevent Windows Desktop Search from indexing Outlook items.</span></span> <span data-ttu-id="6e16e-117">有关详细信息, 请参阅[扩展 Windows 桌面搜索](https://msdn.microsoft.com/library/2eab146a-8516-4b95-b73c-ca7f980ba233%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6e16e-117">For more information, see [Extending Windows Desktop Search](https://msdn.microsoft.com/library/2eab146a-8516-4b95-b73c-ca7f980ba233%28Office.15%29.aspx).</span></span> 
  
## <a name="registry-keys"></a><span data-ttu-id="6e16e-118">注册表项</span><span class="sxs-lookup"><span data-stu-id="6e16e-118">Registry Keys</span></span>

<span data-ttu-id="6e16e-119">在计算机上, 要编制索引的所有存储提供程序都必须在 Windows 注册表中的以下三个注册表项中仅注册一个。</span><span class="sxs-lookup"><span data-stu-id="6e16e-119">On a computer, all store providers that want to be indexed must be registered under only one of the following three registry keys in the Windows registry.</span></span> <span data-ttu-id="6e16e-120">MAPI 协议处理程序将按以下顺序在其中的每个注册表项下查找:</span><span class="sxs-lookup"><span data-stu-id="6e16e-120">The MAPI Protocol Handler looks under each of these keys in the following order:</span></span>
  
1. <span data-ttu-id="6e16e-121">[hklm\] \Software\Policies\Microsoft\Windows\Windows Search \\</span><span class="sxs-lookup"><span data-stu-id="6e16e-121">[HKLM]\Software\Policies\Microsoft\Windows\Windows Search\\</span></span>
    
2. <span data-ttu-id="6e16e-122">[hklm\] \Software\Microsoft\Windows\Windows Search\Preferences\\</span><span class="sxs-lookup"><span data-stu-id="6e16e-122">[HKLM]\Software\Microsoft\Windows\Windows Search\Preferences\\</span></span>
    
3. <span data-ttu-id="6e16e-123">[HKCU] \Software\Microsoft\Windows\Windows Search\Preferences\\</span><span class="sxs-lookup"><span data-stu-id="6e16e-123">[HKCU]\Software\Microsoft\Windows\Windows Search\Preferences\\</span></span>
    
 <span data-ttu-id="6e16e-124">键下的每个值都对应于要编制索引的存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="6e16e-124">Each value under the key corresponds to a store provider that would be indexed.</span></span> <span data-ttu-id="6e16e-125">值的名称是存储提供程序的全局唯一标识符 (GUID), 它的类型为**DWORD** , 且具有十六进制值0x00000001。</span><span class="sxs-lookup"><span data-stu-id="6e16e-125">The name of the value is the Globally Unique Identifier (GUID) of the store provider, which is of the type **DWORD** and has the hexadecimal value 0x00000001.</span></span> 
  
## <a name="guids-for-store-providers"></a><span data-ttu-id="6e16e-126">存储提供程序的 guid</span><span class="sxs-lookup"><span data-stu-id="6e16e-126">GUIDs for Store Providers</span></span>

<span data-ttu-id="6e16e-127">mapi 属性**[PR_MDB_PROVIDER](pidtagstoreprovider-canonical-property.md)** 指定 mapi 存储的 GUID。</span><span class="sxs-lookup"><span data-stu-id="6e16e-127">The MAPI property **[PR_MDB_PROVIDER](pidtagstoreprovider-canonical-property.md)** specifies the GUID of a MAPI store.</span></span> <span data-ttu-id="6e16e-128">下表描述了适用于 Outlook 索引的存储提供程序的 guid。</span><span class="sxs-lookup"><span data-stu-id="6e16e-128">The GUIDs for the store providers that Outlook indexes are described in the following table.</span></span> 
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="6e16e-129">**存储提供程序的类型**</span><span class="sxs-lookup"><span data-stu-id="6e16e-129">**Type of Store Provider**</span></span> <br/> |<span data-ttu-id="6e16e-130">**GUID**</span><span class="sxs-lookup"><span data-stu-id="6e16e-130">**GUID**</span></span> <br/> |<span data-ttu-id="6e16e-131">**Notes**</span><span class="sxs-lookup"><span data-stu-id="6e16e-131">**Notes**</span></span> <br/> |
|<span data-ttu-id="6e16e-132">个人文件夹文件 (。.pst</span><span class="sxs-lookup"><span data-stu-id="6e16e-132">Personal Folders files (.PST)</span></span>  <br/> |<span data-ttu-id="6e16e-133">{4154494E-BFF9-01B8-00AA-0037D96E0000}</span><span class="sxs-lookup"><span data-stu-id="6e16e-133">{4154494E-BFF9-01B8-00AA-0037D96E0000}</span></span>  <br/> |<span data-ttu-id="6e16e-134">GUID 在公用头文件 mspst 中记录为**MSPST_UID_PROVIDER**</span><span class="sxs-lookup"><span data-stu-id="6e16e-134">GUID is documented in the public header file mspst.h as **MSPST_UID_PROVIDER**</span></span> <br/> |
|<span data-ttu-id="6e16e-135">Exchange</span><span class="sxs-lookup"><span data-stu-id="6e16e-135">Exchange</span></span>  <br/> |<span data-ttu-id="6e16e-136">{C0A19454-7F29-1B10-A587-08002B2A2517}</span><span class="sxs-lookup"><span data-stu-id="6e16e-136">{C0A19454-7F29-1B10-A587-08002B2A2517}</span></span>  <br/> |<span data-ttu-id="6e16e-137">GUID 在公用头文件 edkmdb 中记录为**pbExchangeProviderPrimaryUserGuid**</span><span class="sxs-lookup"><span data-stu-id="6e16e-137">GUID is documented in the public header file edkmdb.h as **pbExchangeProviderPrimaryUserGuid**</span></span> <br/> |
|<span data-ttu-id="6e16e-138">公用文件夹</span><span class="sxs-lookup"><span data-stu-id="6e16e-138">Public folders</span></span>  <br/> |<span data-ttu-id="6e16e-139">{70fab278-f7af-cd11-9bc8-00aa002fc45a}</span><span class="sxs-lookup"><span data-stu-id="6e16e-139">{70fab278-f7af-cd11-9bc8-00aa002fc45a}</span></span>  <br/> |<span data-ttu-id="6e16e-140">GUID 在公用头文件 edkmdb 中记录为**pbExchangeProviderPublicGuid**</span><span class="sxs-lookup"><span data-stu-id="6e16e-140">GUID is documented in the public header file edkmdb.h as **pbExchangeProviderPublicGuid**</span></span> <br/> |
|<span data-ttu-id="6e16e-141">Outlook Connector for MSN</span><span class="sxs-lookup"><span data-stu-id="6e16e-141">Outlook Connector for MSN</span></span>  <br/> |<span data-ttu-id="6e16e-142">{c34f5c97-eb05-bb4b-b199-2a7570ec7cf9}</span><span class="sxs-lookup"><span data-stu-id="6e16e-142">{c34f5c97-eb05-bb4b-b199-2a7570ec7cf9}</span></span>  <br/> |<span data-ttu-id="6e16e-143">无</span><span class="sxs-lookup"><span data-stu-id="6e16e-143">None</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6e16e-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e16e-144">See also</span></span>



[<span data-ttu-id="6e16e-145">关于存储 API</span><span class="sxs-lookup"><span data-stu-id="6e16e-145">About the Store API</span></span>](about-the-store-api.md)

