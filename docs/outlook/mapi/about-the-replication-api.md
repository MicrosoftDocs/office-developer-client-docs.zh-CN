---
title: 关于复制 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5133045a-b1e2-7728-5cd5-6d85eb940cf9
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: 50b36ee60d00e06a1f5baa8726b5f27c4a3e6ce7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774466"
---
# <a name="about-the-replication-api"></a>关于复制 API

  
  
**适用于**： Outlook 
  
复制 API 提供了 MAPI 消息存储提供程序同步 Microsoft Outlook 2013 或 Microsoft Outlook 2010 之间的服务器和专用基于.pst 本地存储该提供程序创建的项目的功能。 
  
> [!NOTE]
> MAPI 消息存储提供程序必须实现中[有关复制状态机](about-the-replication-state-machine.md)根据说明复制 API。 提供程序必须在个人存储为本身，创建仅使用 API 和不在为其他提供程序创建的个人存储，因为个人存储为创建其他提供程序可能已经安装了各自的服务器与自己复制机制。 例如，脱机文件夹文件 (.ost) 维护与 Microsoft Exchange server 自己复制关系。 
  
若要使用复制 API，MAPI 消息存储提供程序必须首先打开并通过调用**[NSTServiceEntry](nstserviceentry.md)** 环绕基于.pst 的本地存储区。 提供程序然后可以使用 API、 **[IOSTX](iostxiunknown.md)** 和**[IPSTX](ipstxiunknown.md)** 的主要接口执行复制。 由查询提供**IPSTX** [IMsgStore: IMAPIProp](imsgstoreimapiprop.md)，并由**[IPSTX::GetSyncObject](ipstx-getsyncobject.md)** 提供**IOSTX** 。 
  
## <a name="the-iostx-interface"></a>IOSTX 接口

**IOSTX**接口是执行同步复制 API 中的主要接口。 **IOSTX**移动一系列状态，通过本地存储检索中每种状态信息的本地存储中的更改以及告知本地存储的服务器上的更改。 复制 API 还指定支持的同步的许多数据结构。 
  
存储提供程序，为此 API 的客户端使用复制 API 包装本地存储，并将更改 （如对文件夹层次结构或添加新项的更改） 对本地存储推送到服务器，并还检索移动这些状态，有关更改服务器和的信息提供给**IOSTX**接口上的信息。 **IOSTX**接口采用增量更改同步 (ICS) 提供的 Microsoft Exchange Server。 有关 ICS 的详细信息，请参阅[ICS 评价标准](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx)。 通过**IOSTX**，客户端使用 ICS 监视和同步到层次结构或本地存储区上的内容的增量更改。 
  
## <a name="the-ipstx-interface"></a>IPSTX 接口

 **IPSTX**和其他第五 * * IPSTX *n* * * 继承**IPSTX**的接口提供了执行复制通过**IOSTX**界面时可以使用的帮助器功能。 例如， **[IPSTX::EmulateSpooler](ipstx-emulatespooler.md)** 可以使本地存储模拟 Outlook 协议管理器后台打印到的服务器的传出邮件。 
  
在复制过程状态切换的详细信息，请参阅[有关复制状态机](about-the-replication-state-machine.md)。
  
## <a name="the-replication-api"></a>复制 API

复制 API 提供了以下定义、 数据类型和接口。 示例实现的存储提供程序换行个人文件夹文件 (PST)，请参阅[有关示例自动换行 PST 存储提供程序](about-the-sample-wrapped-pst-store-provider.md)。
  
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
    

