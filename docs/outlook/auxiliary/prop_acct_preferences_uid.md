---
title: PROP_ACCT_PREFERENCES_UID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ec0aac33-624e-48f7-8177-8f7b8db6af7d
description: 检索存储帐户首选项的 "配置文件" 部分的唯一标识符 (UID)。
ms.openlocfilehash: 97f1a858c8f58e13b72b8d5f052b35359581b718
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327634"
---
# <a name="propacctpreferencesuid"></a>PROP_ACCT_PREFERENCES_UID

检索存储帐户首选项的 "配置文件" 部分的唯一标识符 (UID)。 
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x0022  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|属性标记：  <br/> |0x00220102  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>注解

在调用[IMAPISupport:: OpenProfileSection](https://msdn.microsoft.com/library/cd1fa994-9531-46c4-94e5-505e7f90b884%28Office.15%29.aspx)以检索包含帐户首选项的 profile 节时, 请使用**PROP_ACCT_PREFERENCES_UID** 。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)
- [有关反垃圾邮件设置](about-anti-spam-settings.md)

