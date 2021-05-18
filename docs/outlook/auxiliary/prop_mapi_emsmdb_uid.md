---
title: PROP_MAPI_EMSMDB_UID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8e5b42e3-844f-488c-ba6f-b74c447b1d59
description: 表示ACCT_BIN Exchange 帐户的 UID 的自定义结构。
ms.openlocfilehash: 6bb529da82cc24e41ddc70c5031f84050a2ece25
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326549"
---
# <a name="prop_mapi_emsmdb_uid"></a>PROP_MAPI_EMSMDB_UID

表示 [ACCT_BIN](acct_bin.md) Exchange 帐户的 UID 的自定义结构。 
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x2009  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|属性标记：  <br/> |0x20090102  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>备注

使用 [IOlkAccount：：GetProp 获取此属性](iolkaccount-getprop.md)。
  
使用 [PROP_ACCT_IS_EXCH](prop_acct_is_exch.md) 验证该帐户是否为 Exchange 帐户。 如果是 **，PROP \_ MAPI_EMSMDB_UID** 是包含 **emsmdbUID** 的 ACCT_BIN，这是 Exchange 帐户的唯一 ID。  如果该帐户不是 Exchange 帐户，则此属性未定义。
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)
- [使用多个 Exchange 帐户](https://msdn.microsoft.com/library/4e1804bf-4c50-4942-a7ab-9a8caf1be7e5%28Office.15%29.aspx)  
- [PidTagExchangeProfileSectionId 规范属性](https://msdn.microsoft.com/library/4ad2f417-be8f-4fc8-9321-82097289074b%28Office.15%29.aspx)

