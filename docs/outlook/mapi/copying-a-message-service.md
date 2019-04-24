---
title: 复制邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 01e8ad76-973a-42fa-96aa-f41aabc12b4f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a4db4ed1c3098226891edca054621fe145daaa1f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32333052"
---
# <a name="copying-a-message-service"></a>复制邮件服务

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **将邮件服务复制到配置文件**
  
- 调用[IMsgServiceAdmin:: CopyMsgService](imsgserviceadmin-copymsgservice.md)。
    
复制邮件服务时, 该服务的新实例的配置方式与原始的完全相同。 有时**CopyMsgService**将返回错误 MAPI_E_ACCESS_DENIED。 此错误返回最常见的原因是不允许自身重复的邮件服务。 
  

