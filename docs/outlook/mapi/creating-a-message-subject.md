---
title: 创建邮件主题
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 70e18534-054f-49e7-9a5d-10db0db132d0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 753834ba4df6d0239a484af380e4fe0aa45666b4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332961"
---
# <a name="creating-a-message-subject"></a>创建邮件主题

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件主题: **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 是一个可选属性, 用于汇总邮件的目的。 如果您选择设置它, 请将其设为128字节或更小的字符串。 128字节限制不是 MAPI 设定的限制;它是某些邮件存储提供程序施加的限制。 为了确保与对其施加强制的提供程序的互操作性, 请将主题限制为128个字节。 
  
请注意, 某些邮件存储提供程序不允许将**PR_SUBJECT**写入到具有[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口的 stream 中。 
  
请勿设置**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md));仅在答复和转发邮件上设置此属性。 
  

