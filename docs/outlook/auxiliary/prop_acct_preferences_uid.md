---
title: PROP_ACCT_PREFERENCES_UID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ec0aac33-624e-48f7-8177-8f7b8db6af7d
description: 检索存储的帐户首选项配置文件一节的唯一标识符 (UID)。
ms.openlocfilehash: 70e61264e5525f26e9f52e402bc785b544a0b90e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774441"
---
# <a name="propacctpreferencesuid"></a>PROP_ACCT_PREFERENCES_UID

检索存储的帐户首选项配置文件一节的唯一标识符 (UID)。 
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x0022  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|属性标记：  <br/> |0x00220102  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

使用中调用[IMAPISupport::OpenProfileSection](http://msdn.microsoft.com/library/cd1fa994-9531-46c4-94e5-505e7f90b884%28Office.15%29.aspx) **PROP_ACCT_PREFERENCES_UID**检索包含帐户首选项配置文件一节。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)
- [有关反垃圾邮件设置](about-anti-spam-settings.md)

