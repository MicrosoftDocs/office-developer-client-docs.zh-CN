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
  
复制 API 为 MAPI 邮件存储提供程序提供了功能，以在服务器和为提供程序创建的基于 .pst 的专用本地存储之间同步 Microsoft Outlook 2013 或 Microsoft Outlook 2010 项。 
  
> [!NOTE]
> MAPI 邮件存储提供程序必须按照关于复制状态机 中的[说明实现复制 API。](about-the-replication-state-machine.md) 提供程序必须仅在为自身创建的个人存储（而非为其他提供程序创建的个人存储）上使用此 API，因为为其他提供程序创建的个人存储可能已经使用各自的服务器设置了自己的复制机制。 例如，脱机文件夹文件 (.ost) 与 Microsoft Exchange 服务器保持自己的复制关系。 
  
若要使用复制 API，MAPI 邮件存储提供程序必须先通过调用 **[NSTServiceEntry](nstserviceentry.md)** 打开并包装基于 .pst 的本地存储。 然后，提供程序可以使用 **[API、IOSTX](iostxiunknown.md)** 和 **[IPSTX](ipstxiunknown.md)** 的主要接口执行复制。 **IPSTX** 通过查询 [IMsgStore ： IMAPIProp](imsgstoreimapiprop.md)提供 **，IOSTX** 由 **[IPSTX：：GetSyncObject 提供](ipstx-getsyncobject.md)**。 
  
## <a name="the-iostx-interface"></a>IOSTX 接口

**IOSTX** 接口是在复制 API 中执行同步的主接口。 **IOSTX** 通过一系列状态移动本地存储，检索每个状态中有关本地存储更改的信息，并通知本地存储服务器上所做的更改。 复制 API 还指定许多支持同步的数据结构。 
  
存储提供程序作为此 API 的客户端，使用复制 API 包装本地存储并移动这些状态，将更改推送到本地存储 (例如更改文件夹层次结构或向服务器添加新项) ，以及检索有关服务器上更改的信息，以及向 **IOSTX** 接口提供该信息。 **IOSTX** 接口采用由) 提供的 ICS (增量更改Microsoft Exchange Server。 有关 ICS 详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。 通过 **IOSTX，** 客户端使用 ICS 监视并同步对层次结构或本地存储内容的增量更改。 
  
## <a name="the-ipstx-interface"></a>IPSTX 接口

 **从 IPSTX** 继承的 IPSTX 和另外五个 **IPSTX *n* ** 接口提供通过 **IOSTX** 接口执行复制时可以使用的帮助程序功能。  例如 **[，IPSTX：：EmulateSpooler](ipstx-emulatespooler.md)** 允许您使本地存储模拟 Outlook 协议管理器以将传出邮件后台打印到服务器。 
  
有关复制期间状态转换的信息，请参阅关于 [复制状态机](about-the-replication-state-machine.md)。
  
## <a name="the-replication-api"></a>复制 API

复制 API 提供以下定义、数据类型和接口。 有关包装的个人文件夹文件的存储提供程序的示例实现 (PST) ，请参阅关于封装 PST 存储 [提供程序示例](about-the-sample-wrapped-pst-store-provider.md)。
  
定义：
  
- [复制 API 的常量](mapi-constants.md)
    
函数：
  
- **[NSTServiceEntry](nstserviceentry.md)**
    
数据类型：
  
- **[DNHIER](dnhier.md)**
    
- **[DNTBL](dntbl.md)**
    
- **[DNTBLE](dntble.md)**
    
- **[FEID](feid.md)**
    
- **[HDRSYNC](hdrsync.md)**
    
- **[LTID](ltid.md)**
    
- **[MEID](meid.md)**
    
- **[OLFI](olfi.md)**
    
- **[SKEY](skey.md)**
    
- **[SYNC](sync.md)**
    
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
    

