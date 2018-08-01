---
title: 设置默认配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1d1e862d-ba49-48a1-bb51-0af861323b7b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ea21e735dba8690a392629b92b636b834d7d57d7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778749"
---
# <a name="setting-a-default-profile"></a>设置默认配置文件

  
  
**适用于**： Outlook 
  
如果您不明确指定一个对[MAPILogonEx](mapilogonex.md)，而设置 MAPI_USE_DEFAULT 标志的调用中使用的配置文件的默认配置文件。
  
 **建立默认配置文件**
  
1. 调用[MAPIAdminProfiles](mapiadminprofiles.md)函数以检索**IProfAdmin**接口的指针。 
    
2. 调用[IProfAdmin::SetDefaultProfile](iprofadmin-setdefaultprofile.md)。 **SetDefaultProfile**设置新的默认配置文件的**PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 属性，并删除以前的默认配置文件的设置。
    

