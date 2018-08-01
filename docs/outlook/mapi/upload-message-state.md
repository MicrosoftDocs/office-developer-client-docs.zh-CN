---
title: 上传邮件状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7fdc1494-4f40-38bd-d363-144ca70e5906
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 752756cbcf6c1ce487188dd4b9ba55eee6506cd4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779050"
---
# <a name="upload-message-state"></a>上传邮件状态

  
  
**适用于**： Outlook 
  
 本主题介绍上载邮件状态的复制状态机期间出现的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_UPLOAD_MESSAGE** <br/> |
|相关的数据结构：  <br/> |**[UPMSG](upmsg.md)** <br/> |
|从此状态：  <br/> |[上载表状态](upload-table-state.md) <br/> |
|为此状态：  <br/> |上载表状态  <br/> |
   
> [!NOTE]
> 复制状态机是确定性状态机。 从一种状态传出到另一个客户端从后者必须最终返回到前者。 
  
## <a name="description"></a>说明

此状态启动上载 Outlook 项目 （邮件、 日历、 联系人、 任务、 注释或日记） 的新增或已移动到当前文件夹，或已修改的。 Outlook 初始化 correpsonding **UPMSG**数据结构的项目的相应信息，如添加、 移动或修改。 
  
如果已添加或移动项目，客户端然后相应地添加或更新服务器上的项。 
  
如果已修改项目，Outlook 进一步指定**UPMSG**数据结构中修改的邮件头 （这种情况下该项目是邮件头）、 在项目属性，或本身需要冲突项目中解决方法。 然后，客户端更新服务器上的项。 
  
项目上载结束时，Outlook 备注，已上载邮件，以便将不会处理后续上载。 本地存储返回到上载表状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

