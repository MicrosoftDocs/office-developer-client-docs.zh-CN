---
title: 复制邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 01e8ad76-973a-42fa-96aa-f41aabc12b4f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7d1296ba74bbafcd26a8878dfb1eb2f359ab3e03
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774677"
---
# <a name="copying-a-message-service"></a>复制邮件服务

  
  
**适用于**： Outlook 
  
 **若要将邮件服务复制到一个配置文件**
  
- 调用[IMsgServiceAdmin::CopyMsgService](imsgserviceadmin-copymsgservice.md)。
    
复制的消息服务时中与原始完全相同的方式, 配置该服务的新实例。 有时**CopyMsgService**将返回错误 MAPI_E_ACCESS_DENIED。 此错误返回的最常见原因是不允许本身要重复的消息服务。 
  

