---
title: 有关脱机通讯簿的上次更新时间
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: d8c554c5-89ac-9b32-5561-8d8178d2525a
description: 脱机通讯簿 (OAB) 提供 Outlook 用户在断开连接的状态访问目录信息从全局地址列表 (GAL) 以及从其他通讯簿中。
ms.openlocfilehash: b1e3ff012606615e5e962c400f86ab5ee2fbed83
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774187"
---
# <a name="about-the-last-update-time-of-an-offline-address-book"></a>有关脱机通讯簿的上次更新时间

脱机通讯簿 (OAB) 提供 Outlook 用户在断开连接的状态访问目录信息从全局地址列表 (GAL) 以及从其他通讯簿中。它是从提供脱机访问 Exchange 服务器下载了 Outlook 通讯簿的副本。
  
Exchange 管理员可以选择可用于脱机工作的用户的通讯簿。创建通讯簿的副本，Exchange 生成新 OAB 文件、 压缩文件，并将其放置在一个本地共享。根据如何配置 Outlook，Outlook 将下载 OAB 文件从 Web 或者从公用文件夹的客户端计算机使用断开连接的状态中。Outlook 将定期检查并下载 OAB 更新。
  
Outlook 解决方案需要为用户提供对 OAB 的脱机访问可能需要了解何时从 Exchange 服务器上次更新 OAB。 若要查找 OAB 的上次更新时间，解决方案可以使用下面的项在 Windows 注册表中: **HKCU\Software\Microsoft\Exchange\Exchange Provider\OAB 最后修改时间** 。此注册表项的类型为 **REG_BINARY** 。数据是大小为 8 个字节。您可以将数据转换为 64 位 [FILETIME](http://msdn.microsoft.com/library/9baf8a0e-59e3-4fbd-9616-2ec9161520d1%28Office.15%29.aspx)结构，它指定协调通用时间 (UTC) 值，Outlook 上次下载 OAB 文件从 Exchange 服务器到客户端计算机。 
  
## <a name="see-also"></a>另请参阅

- [Managing Offline Address Books](http://msdn.microsoft.com/library/b7f26eca-b93b-4834-ba50-11febdefbb18.aspx)

