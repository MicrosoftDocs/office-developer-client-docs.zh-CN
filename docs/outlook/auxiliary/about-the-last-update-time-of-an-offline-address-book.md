---
title: 有关脱机通讯簿的上次更新时间
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: d8c554c5-89ac-9b32-5561-8d8178d2525a
description: 脱机通讯簿 (OAB) 提供 Outlook 用户在断开连接的状态访问目录信息从全局地址列表 (GAL) 以及从其他通讯簿中。
ms.openlocfilehash: 3374f87cd62d46a80ed823bff0516115a58c155c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392282"
---
# <a name="about-the-last-update-time-of-an-offline-address-book"></a><span data-ttu-id="e4f48-103">有关脱机通讯簿的上次更新时间</span><span class="sxs-lookup"><span data-stu-id="e4f48-103">About the last update time of an Offline Address Book</span></span>

<span data-ttu-id="e4f48-p101">脱机通讯簿 (OAB) 提供 Outlook 用户在断开连接的状态访问目录信息从全局地址列表 (GAL) 以及从其他通讯簿中。它是从提供脱机访问 Exchange 服务器下载了 Outlook 通讯簿的副本。</span><span class="sxs-lookup"><span data-stu-id="e4f48-p101">An Offline Address Book (OAB) provides Outlook users in a disconnected state access to directory information from the Global Address List (GAL) and from other address books. It is a copy of an Address Book that Outlook has downloaded from an Exchange server to provide offline access.</span></span>
  
<span data-ttu-id="e4f48-p102">Exchange 管理员可以选择可用于脱机工作的用户的通讯簿。创建通讯簿的副本，Exchange 生成新 OAB 文件、 压缩文件，并将其放置在一个本地共享。根据如何配置 Outlook，Outlook 将下载 OAB 文件从 Web 或者从公用文件夹的客户端计算机使用断开连接的状态中。Outlook 将定期检查并下载 OAB 更新。</span><span class="sxs-lookup"><span data-stu-id="e4f48-p102">Exchange administrators can choose which Address Books to make available for users who work offline. To create a copy of an Address Book, Exchange generates new OAB files, compresses the files, and places them on a local share. Depending on how Outlook is configured, Outlook downloads the OAB files either from the Web or from a Public Folder to a client computer for use in a disconnected state. Outlook periodically checks for and downloads OAB updates.</span></span>
  
<span data-ttu-id="e4f48-p103">Outlook 解决方案需要为用户提供对 OAB 的脱机访问可能需要了解何时从 Exchange 服务器上次更新 OAB。 若要查找 OAB 的上次更新时间，解决方案可以使用下面的项在 Windows 注册表中: **HKCU\Software\Microsoft\Exchange\Exchange Provider\OAB 最后修改时间** 。此注册表项的类型为 **REG_BINARY** 。数据是大小为 8 个字节。您可以将数据转换为 64 位 [FILETIME](https://msdn.microsoft.com/library/9baf8a0e-59e3-4fbd-9616-2ec9161520d1%28Office.15%29.aspx)结构，它指定协调通用时间 (UTC) 值，Outlook 上次下载 OAB 文件从 Exchange 服务器到客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="e4f48-p103">Outlook solutions that want to provide their users offline access to an OAB may need to find out when the OAB was last updated from the Exchange server. To find the last update time of an OAB, solutions can use the following entry in the Windows registry: **HKCU\Software\Microsoft\Exchange\Exchange Provider\OAB Last Modified Time**. The type of this registry entry is **REG_BINARY**. The data is 8 bytes in size. You can convert the data to a 64-bit [FILETIME](https://msdn.microsoft.com/library/9baf8a0e-59e3-4fbd-9616-2ec9161520d1%28Office.15%29.aspx) structure specifying a Universal Coordinated Time (UTC) value that Outlook last downloaded the OAB files from the Exchange server to the client computer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e4f48-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4f48-115">See also</span></span>

- [<span data-ttu-id="e4f48-116">Managing Offline Address Books</span><span class="sxs-lookup"><span data-stu-id="e4f48-116">Managing Offline Address Books</span></span>](https://msdn.microsoft.com/library/b7f26eca-b93b-4834-ba50-11febdefbb18.aspx)

