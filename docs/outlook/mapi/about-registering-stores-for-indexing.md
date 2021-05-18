---
title: 关于注册用于索引的存储区
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
# <a name="about-registering-stores-for-indexing"></a><span data-ttu-id="fff78-103">关于注册用于索引的存储区</span><span class="sxs-lookup"><span data-stu-id="fff78-103">About Registering Stores for Indexing</span></span>

  
  
<span data-ttu-id="fff78-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fff78-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fff78-105">本主题特定于 Microsoft Office Outlook 2007 中的即时搜索。</span><span class="sxs-lookup"><span data-stu-id="fff78-105">This topic is specific to Instant Search in Microsoft Office Outlook 2007.</span></span>
  
<span data-ttu-id="fff78-106">通过即时搜索，可以快速查找Outlook。</span><span class="sxs-lookup"><span data-stu-id="fff78-106">Instant Search lets you quickly find items in Outlook.</span></span> <span data-ttu-id="fff78-107">它使用桌面Windows的组件。</span><span class="sxs-lookup"><span data-stu-id="fff78-107">It uses components of Windows Desktop Search.</span></span>
  
<span data-ttu-id="fff78-108">MAPI 协议处理程序Windows注册表中查找出于搜索目的应编制索引的存储区。</span><span class="sxs-lookup"><span data-stu-id="fff78-108">The MAPI Protocol Handler checks the Windows registry for stores that it should index for search purposes.</span></span> <span data-ttu-id="fff78-109">必须在注册表中注册要编制索引Windows提供程序。</span><span class="sxs-lookup"><span data-stu-id="fff78-109">Store providers that want to be indexed must be registered in the Windows registry.</span></span>
  
<span data-ttu-id="fff78-110">默认情况下，Windows搜索将以下四种类型的存储提供程序添加到Windows注册表中以允许编制索引：</span><span class="sxs-lookup"><span data-stu-id="fff78-110">By default, Windows Desktop Search adds the following four types of store providers to the Windows registry to allow indexing:</span></span>
  
- <span data-ttu-id="fff78-111">个人文件夹文件存储 (。PST) 。</span><span class="sxs-lookup"><span data-stu-id="fff78-111">Store for Personal Folders files (.PST).</span></span>
    
-  <span data-ttu-id="fff78-112">Microsoft Exchange存储，包括任何脱机文件夹 (.ost) 。</span><span class="sxs-lookup"><span data-stu-id="fff78-112">Microsoft Exchange store, including any Offline Folder files (.ost).</span></span> 
    
-  <span data-ttu-id="fff78-113">公用文件夹的存储区。</span><span class="sxs-lookup"><span data-stu-id="fff78-113">Store for public folders.</span></span> 
    
-  <span data-ttu-id="fff78-114">适用于 MSN Microsoft Office Outlook连接器存储。</span><span class="sxs-lookup"><span data-stu-id="fff78-114">Store for Microsoft Office Outlook Connector for MSN.</span></span> 
    
 <span data-ttu-id="fff78-115">要编制索引的第三方存储提供程序必须在注册表中Windows自身。</span><span class="sxs-lookup"><span data-stu-id="fff78-115">Third-party store providers that want to be indexed must register themselves in the Windows registry.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fff78-116">管理员和用户可以使用组策略设置来Windows桌面搜索对项目编制Outlook索引。</span><span class="sxs-lookup"><span data-stu-id="fff78-116">Administrators and users can use a Group Policy setting to prevent Windows Desktop Search from indexing Outlook items.</span></span> <span data-ttu-id="fff78-117">有关详细信息，请参阅扩展Windows[桌面搜索。](https://msdn.microsoft.com/library/2eab146a-8516-4b95-b73c-ca7f980ba233%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fff78-117">For more information, see [Extending Windows Desktop Search](https://msdn.microsoft.com/library/2eab146a-8516-4b95-b73c-ca7f980ba233%28Office.15%29.aspx).</span></span> 
  
## <a name="registry-keys"></a><span data-ttu-id="fff78-118">注册表项</span><span class="sxs-lookup"><span data-stu-id="fff78-118">Registry Keys</span></span>

<span data-ttu-id="fff78-119">在计算机上，所有要编制索引的存储区提供程序都必须在注册表中的以下三个注册表项之一Windows注册。</span><span class="sxs-lookup"><span data-stu-id="fff78-119">On a computer, all store providers that want to be indexed must be registered under only one of the following three registry keys in the Windows registry.</span></span> <span data-ttu-id="fff78-120">MAPI 协议处理程序按以下顺序查看其中每个键：</span><span class="sxs-lookup"><span data-stu-id="fff78-120">The MAPI Protocol Handler looks under each of these keys in the following order:</span></span>
  
1. <span data-ttu-id="fff78-121">[HKLM]\Software\Policies\Microsoft\Windows\Windows Search</span><span class="sxs-lookup"><span data-stu-id="fff78-121">[HKLM]\Software\Policies\Microsoft\Windows\Windows Search</span></span>\
    
2. <span data-ttu-id="fff78-122">[HKLM]\Software\Microsoft\Windows\Windows Search\Preferences</span><span class="sxs-lookup"><span data-stu-id="fff78-122">[HKLM]\Software\Microsoft\Windows\Windows Search\Preferences</span></span>\
    
3. <span data-ttu-id="fff78-123">[HKCU]\Software\Microsoft\Windows\Windows Search\Preferences</span><span class="sxs-lookup"><span data-stu-id="fff78-123">[HKCU]\Software\Microsoft\Windows\Windows Search\Preferences</span></span>\
    
 <span data-ttu-id="fff78-124">键下的每个值对应于将编制索引的存储区提供程序。</span><span class="sxs-lookup"><span data-stu-id="fff78-124">Each value under the key corresponds to a store provider that would be indexed.</span></span> <span data-ttu-id="fff78-125">值的名称是存储提供程序的全局唯一标识符 (GUID) ，其类型为 **DWORD，** 并且具有十六进制值0x00000001。</span><span class="sxs-lookup"><span data-stu-id="fff78-125">The name of the value is the Globally Unique Identifier (GUID) of the store provider, which is of the type **DWORD** and has the hexadecimal value 0x00000001.</span></span> 
  
## <a name="guids-for-store-providers"></a><span data-ttu-id="fff78-126">存储提供程序的 GUID</span><span class="sxs-lookup"><span data-stu-id="fff78-126">GUIDs for Store Providers</span></span>

<span data-ttu-id="fff78-127">MAPI 属性 **[PR_MDB_PROVIDER](pidtagstoreprovider-canonical-property.md)** 指定 MAPI 存储的 GUID。</span><span class="sxs-lookup"><span data-stu-id="fff78-127">The MAPI property **[PR_MDB_PROVIDER](pidtagstoreprovider-canonical-property.md)** specifies the GUID of a MAPI store.</span></span> <span data-ttu-id="fff78-128">下表介绍了存储提供程序的 GUID Outlook索引的 GUID。</span><span class="sxs-lookup"><span data-stu-id="fff78-128">The GUIDs for the store providers that Outlook indexes are described in the following table.</span></span> 
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="fff78-129">**存储提供程序的类型**</span><span class="sxs-lookup"><span data-stu-id="fff78-129">**Type of Store Provider**</span></span> <br/> |<span data-ttu-id="fff78-130">**GUID**</span><span class="sxs-lookup"><span data-stu-id="fff78-130">**GUID**</span></span> <br/> |<span data-ttu-id="fff78-131">**备注**</span><span class="sxs-lookup"><span data-stu-id="fff78-131">**Notes**</span></span> <br/> |
|<span data-ttu-id="fff78-132">个人文件夹文件 (。PST) </span><span class="sxs-lookup"><span data-stu-id="fff78-132">Personal Folders files (.PST)</span></span>  <br/> |<span data-ttu-id="fff78-133">{4154494E-BFF9-01B8-00AA-0037D96E0000}</span><span class="sxs-lookup"><span data-stu-id="fff78-133">{4154494E-BFF9-01B8-00AA-0037D96E0000}</span></span>  <br/> |<span data-ttu-id="fff78-134">GUID 作为文档记录在公共头文件 mspst.h **中MSPST_UID_PROVIDER**</span><span class="sxs-lookup"><span data-stu-id="fff78-134">GUID is documented in the public header file mspst.h as **MSPST_UID_PROVIDER**</span></span> <br/> |
|<span data-ttu-id="fff78-135">Exchange</span><span class="sxs-lookup"><span data-stu-id="fff78-135">Exchange</span></span>  <br/> |<span data-ttu-id="fff78-136">{C0A19454-7F29-1B10-A587-08002B2A2517}</span><span class="sxs-lookup"><span data-stu-id="fff78-136">{C0A19454-7F29-1B10-A587-08002B2A2517}</span></span>  <br/> |<span data-ttu-id="fff78-137">GUID 在公共头文件 edkmdb.h 中记录为 **pbExchangeProviderPrimaryUserGuid**</span><span class="sxs-lookup"><span data-stu-id="fff78-137">GUID is documented in the public header file edkmdb.h as **pbExchangeProviderPrimaryUserGuid**</span></span> <br/> |
|<span data-ttu-id="fff78-138">公用文件夹</span><span class="sxs-lookup"><span data-stu-id="fff78-138">Public folders</span></span>  <br/> |<span data-ttu-id="fff78-139">{70fab278-f7af-cd11-9bc8-00aa002fc45a}</span><span class="sxs-lookup"><span data-stu-id="fff78-139">{70fab278-f7af-cd11-9bc8-00aa002fc45a}</span></span>  <br/> |<span data-ttu-id="fff78-140">GUID 在公共头文件 edkmdb.h 中记录为 **pbExchangeProviderPublicGuid**</span><span class="sxs-lookup"><span data-stu-id="fff78-140">GUID is documented in the public header file edkmdb.h as **pbExchangeProviderPublicGuid**</span></span> <br/> |
|<span data-ttu-id="fff78-141">OutlookMSN 连接器</span><span class="sxs-lookup"><span data-stu-id="fff78-141">Outlook Connector for MSN</span></span>  <br/> |<span data-ttu-id="fff78-142">{c34f5c97-eb05-bb4b-b199-2a7570ec7cf9}</span><span class="sxs-lookup"><span data-stu-id="fff78-142">{c34f5c97-eb05-bb4b-b199-2a7570ec7cf9}</span></span>  <br/> |<span data-ttu-id="fff78-143">无</span><span class="sxs-lookup"><span data-stu-id="fff78-143">None</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fff78-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fff78-144">See also</span></span>



[<span data-ttu-id="fff78-145">关于存储 API</span><span class="sxs-lookup"><span data-stu-id="fff78-145">About the Store API</span></span>](about-the-store-api.md)

