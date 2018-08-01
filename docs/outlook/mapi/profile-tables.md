---
title: 配置文件表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cd8d60df-98fb-4e08-b547-0836bb31be79
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 84c2d02da840dfcad077462954cb10894ba153d9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778555"
---
# <a name="profile-tables"></a>配置文件表

  
  
**适用于**： Outlook 
  
配置文件表列出了有关与特定客户端应用程序关联的所有配置文件信息。 一个配置文件表是为每个会话，由 MAPI 客户端使用的实现。 
  
客户端通过调用[IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md)方法访问配置文件表。 
  
配置文件表是一个静态表。 配置文件表中不包含已标记为删除的配置文件。
  
为与大多数表实现，如果调用**GetProfileTable** ，并且没有配置文件供客户端，表创建零行。 
  
以下属性构成 profile 表中所需的列：
  
 **PR_DEFAULT_PROFILE**([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 
  
 **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

