---
title: 设置默认配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1d1e862d-ba49-48a1-bb51-0af861323b7b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f6bf8f88fa3e87ae619fa32d759fc182290998ad
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439812"
---
# <a name="setting-a-default-profile"></a>设置默认配置文件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果未在对[MAPILogonEx](mapilogonex.md)的调用中显式指定一个配置文件, 则将使用默认配置文件, 而改为设置 MAPI_USE_DEFAULT 标志。
  
 **建立默认配置文件**
  
1. 调用[MAPIAdminProfiles](mapiadminprofiles.md)函数以检索**IProfAdmin**接口指针。 
    
2. 调用[IProfAdmin:: SetDefaultProfile](iprofadmin-setdefaultprofile.md)。 **SetDefaultProfile**设置新的默认配置文件的**PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 属性, 并删除以前的默认配置文件的设置。
    

