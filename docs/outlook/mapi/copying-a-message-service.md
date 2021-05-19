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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425391"
---
# <a name="copying-a-message-service"></a>复制邮件服务

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **将邮件服务复制到配置文件**
  
- 调用 [IMsgServiceAdmin：：CopyMsgService](imsgserviceadmin-copymsgservice.md)。
    
复制邮件服务时，将按照与原始实例完全相同的方式配置服务的新实例。 有时 **，CopyMsgService** 会返回错误MAPI_E_ACCESS_DENIED。 此错误返回的最常见原因是邮件服务不允许自我复制。 
  

