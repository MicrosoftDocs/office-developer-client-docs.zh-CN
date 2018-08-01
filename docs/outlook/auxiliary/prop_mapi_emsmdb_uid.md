---
title: PROP_MAPI_EMSMDB_UID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8e5b42e3-844f-488c-ba6f-b74c447b1d59
description: 表示包含 Exchange 帐户的 UID ACCT_BIN 结构。
ms.openlocfilehash: 05e2e61601a08e0cb6f6dc99d265f12a10b19d3f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774457"
---
# <a name="propmapiemsmdbuid"></a>PROP_MAPI_EMSMDB_UID

表示包含 Exchange 帐户的 UID [ACCT_BIN](acct_bin.md)结构。 
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x2009  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|属性标记：  <br/> |0x20090102  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

通过使用[IOlkAccount::GetProp](iolkaccount-getprop.md)获取此属性。
  
使用[PROP_ACCT_IS_EXCH](prop_acct_is_exch.md)验证帐户是 Exchange 帐户。 如果是，**属性\_MAPI_EMSMDB_UID**是包含**emsmdbUID**，这是 Exchange 帐户的唯一 ID， **ACCT_BIN** 。 如果该帐户不是 Exchange 帐户，则此属性未定义。
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)
- [使用多个 Exchange 帐户](http://msdn.microsoft.com/library/4e1804bf-4c50-4942-a7ab-9a8caf1be7e5%28Office.15%29.aspx)  
- [PidTagExchangeProfileSectionId 规范属性](http://msdn.microsoft.com/library/4ad2f417-be8f-4fc8-9321-82097289074b%28Office.15%29.aspx)

