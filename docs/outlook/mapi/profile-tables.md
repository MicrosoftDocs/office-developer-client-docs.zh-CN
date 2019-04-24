---
title: 配置文件表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cd8d60df-98fb-4e08-b547-0836bb31be79
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 15c07c05af82389bce697c300cd9b1d504e98736
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328558"
---
# <a name="profile-tables"></a>配置文件表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
配置文件表列出了与特定客户端应用程序相关联的所有配置文件的相关信息。 每个会话都有一个配置文件表, 由 MAPI 实现, 以供客户端使用。 
  
客户端通过调用[IProfAdmin:: GetProfileTable](iprofadmin-getprofiletable.md)方法访问配置文件表。 
  
配置文件表是静态表。 已标记为删除的配置文件不包含在配置文件表中。
  
与大多数表实现一样, 如果调用了**GetProfileTable**并且没有可用于客户端的配置文件, 则会创建表, 其中包含零行。 
  
以下属性构成了 profile 表中的必需列集:
  
 **PR_DEFAULT_PROFILE**([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 
  
 **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

