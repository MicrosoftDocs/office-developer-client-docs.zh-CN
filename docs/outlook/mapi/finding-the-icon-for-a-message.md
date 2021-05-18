---
title: 查找邮件图标
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 80a97c3d-4bca-4819-9da4-ca0fbf3a686f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b351cc68e3c3d9f9c01acb4b3d0e52158e302d7a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409151"
---
# <a name="finding-the-icon-for-a-message"></a>查找邮件图标

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **查找与邮件关联的图标**
  
1. 调用邮件的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法以 **检索其** PR_MESSAGE_CLASS ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性。
    
2. 调用 [MAPIOpenFormMgr](mapiopenformmgr.md) 以检索 **IMAPIFormMgr** 接口指针。 在 **pSession** 参数中传递 IMAPISession 指针。  
    
3. 调用 [IMAPIFormMgr：：ResolveMessageClass](imapiformmgr-resolvemessageclass.md) 以检索 **IMAPIFormInfo** 接口指针。 
    
4. 使用 **IMAPIFormInfo** 指针调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 并检索 **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 和/或 **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性。 
    

