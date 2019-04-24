---
title: 关于复制 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5133045a-b1e2-7728-5cd5-6d85eb940cf9
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: 532c01d6885e72753067b2d30bf2bd5f88207176
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329517"
---
# <a name="about-the-replication-api"></a>关于复制 API

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
复制 API 提供 MAPI 邮件存储提供程序的功能, 以在服务器和为该提供程序创建的基于 .pst 的专用本地存储之间同步 microsoft outlook 2013 或 microsoft outlook 2010 项目。 
  
> [!NOTE]
> MAPI 邮件存储提供程序必须根据[复制状态计算机](about-the-replication-state-machine.md)中的说明实现复制 API。 提供程序只能在为自己创建的个人存储区上使用 API, 而不能在为其他提供程序创建的个人存储区上使用该 API, 因为为其他提供程序创建的个人存储可能已经使用各自的服务器设置了自己的复制机制。 例如, 脱机文件夹文件 (.ost) 与 Microsoft Exchange server 保持自己的复制关系。 
  
若要使用复制 API, MAPI 邮件存储提供程序必须先通过调用**[NSTServiceEntry](nstserviceentry.md)** 打开并包装基于 .pst 的本地存储。 然后, 提供程序可以使用 API 的主要接口**[IOSTX](iostxiunknown.md)** 和**[IPSTX](ipstxiunknown.md)** 来执行复制。 **IPSTX**是通过[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)中的查询提供的, **IOSTX**由**[IPSTX:: GetSyncObject](ipstx-getsyncobject.md)** 提供。 
  
## <a name="the-iostx-interface"></a>IOSTX 接口

**IOSTX**接口是在复制 API 中执行同步的主要接口。 **IOSTX**通过一系列状态移动本地存储, 在每个状态中检索有关本地存储中的更改的信息, 并在服务器上通知本地存储区更改。 复制 API 还指定了许多支持同步的数据结构。 
  
作为此 API 的客户端, 存储提供程序使用复制 API 来包装本地存储并在这些状态中移动, 并将本地存储中的更改 (如对文件夹层次结构的更改或添加新项目) 推送到服务器, 同时检索有关服务器上的更改以及将该信息提供给**IOSTX**接口的信息。 **IOSTX**接口采用由 Microsoft Exchange Server 提供的增量更改同步 (ICS)。 有关 ics 的详细信息, 请参阅[ics 评估标准](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。 通过**IOSTX**, 客户端使用 ICS 监视和同步对本地存储上的层次结构或内容的增量更改。 
  
## <a name="the-ipstx-interface"></a>IPSTX 接口

 **IPSTX**和5个其他 * * IPSTX *n* * * 从**IPSTX**继承的接口提供可在通过**IOSTX**接口执行复制时使用的帮助程序功能。 例如, **[IPSTX:: EmulateSpooler](ipstx-emulatespooler.md)** 允许您让本地存储模拟 Outlook 协议管理器, 以将传出邮件假脱机到服务器。 
  
有关复制期间状态转换的详细信息, 请参阅[关于复制状态机](about-the-replication-state-machine.md)。
  
## <a name="the-replication-api"></a>复制 API

复制 API 提供以下 defintions、数据类型和接口。 有关包装的个人文件夹文件 (PST) 的存储提供程序的示例实现, 请参阅[关于包装的 PST 存储提供程序的相关](about-the-sample-wrapped-pst-store-provider.md)示例。
  
定义：
  
- [复制 API 的常量](mapi-constants.md)
    
函数：
  
- **[NSTServiceEntry](nstserviceentry.md)**
    
数据类型:
  
- **[DNHIER](dnhier.md)**
    
- **[DNTBL](dntbl.md)**
    
- **[DNTBLE](dntble.md)**
    
- **[FEID](feid.md)**
    
- **[HDRSYNC](hdrsync.md)**
    
- **[LTID](ltid.md)**
    
- **[MEID](meid.md)**
    
- **[OLFI](olfi.md)**
    
- **[SKEY](skey.md)**
    
- **[同步](sync.md)**
    
- **[SYNCCONT](synccont.md)**
    
- **[SYNCSTATE](syncstate.md)**
    
- **[UPDEL](updel.md)**
    
- **[UPDELE](updele.md)**
    
- **[UPFLD](upfld.md)**
    
- **[UPHIER](uphier.md)**
    
- **[UPMOV](upmov.md)**
    
- **[UPMSG](upmsg.md)**
    
- **[UPREAD](upread.md)**
    
- **[UPREADE](upreade.md)**
    
- **[UPTBL](uptbl.md)**
    
- **[UPTBLE](uptble.md)**
    
接口：
  
- **[IOSTX](iostxiunknown.md)**
    
- **[IPSTX](ipstxiunknown.md)**
    
- **[IPSTX2](ipstx2ipstx.md)**
    
- **[IPSTX3](ipstx3ipstx2.md)**
    
- **[IPSTX4](ipstx4ipstx3.md)**
    
- **[IPSTX5](ipstx5ipstx4.md)**
    
- **[IPSTX6](ipstx6ipstx5.md)**
    

