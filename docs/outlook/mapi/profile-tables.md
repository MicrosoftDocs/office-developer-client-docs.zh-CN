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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424348"
---
# <a name="profile-tables"></a>配置文件表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
配置文件表列出了有关与特定客户端应用程序关联的所有配置文件的信息。 每个会话都有一个配置文件表，由 MAPI 实现供客户端使用。 
  
客户端通过调用 [IProfAdmin：：GetProfileTable 方法访问配置文件](iprofadmin-getprofiletable.md) 表。 
  
配置文件表是静态表。 配置文件表中不包含已标记为删除的配置文件。
  
与大多数表实现一样，如果 **调用了 GetProfileTable** 并且客户端没有可用的配置文件，则使用零行创建表。 
  
以下属性将包含配置文件表中所需的列集：
  
 **PR_DEFAULT_PROFILE (** [PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md))  
  
 **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))  
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

