---
title: PROP_ACCT_STAMP
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 70b6ecc8-6be3-0f05-3291-ac5b7f2ecfdb
description: 返回帐户戳。
ms.openlocfilehash: fe3c6e65e12ab62bd1c2ec0245e4a22502f610eb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327592"
---
# <a name="propacctstamp"></a>PROP_ACCT_STAMP

返回帐户戳。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x000D  <br/> |
|属性类型  <br/> |PT_UNICODE  <br/> |
|属性标记：  <br/> |0x000D001F  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>注解

使用[IOlkAccount:: GetProp](iolkaccount-getprop.md)获取此属性。 如果客户端尝试设置此属性, 则此属性返回**E_OLK_PROP_READ_ONLY**。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)  
- [常量 （帐户管理 API）](constants-account-management-api.md)

