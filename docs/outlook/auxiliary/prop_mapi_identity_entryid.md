---
title: PROP_MAPI_IDENTITY_ENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c64db8ea-d6ad-4fb9-97aa-958e5a0daf8f
description: 检索或设置的帐户的地址簿条目 ID。
ms.openlocfilehash: d85a779da36c2780fe058f906086f61cfc47d5d1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774437"
---
# <a name="propmapiidentityentryid"></a>PROP_MAPI_IDENTITY_ENTRYID

检索或设置的帐户的地址簿条目 ID。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x2002  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|属性标记：  <br/> |0x20020102  <br/> |
|访问权限  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>备注

 **属性\_MAPI\_IDENTITY\_ENTRYID**不应存在于每个帐户上。 例如，可以有一个 Exchange 帐户**属性\_MAPI\_IDENTITY\_ENTRYID**设置，而不[属性\_ACCT_USER_EMAIL_ADDR](prop_acct_user_email_addr.md)，而 SMTP/POP3 帐户的情况下将被颠倒。 **属性\_MAPI_IDENTITY_ENTRYID**返回类似于_lppEntryID_ [IMAPISession::QueryIdentity](http://msdn.microsoft.com/library/a2cdda90-5457-49a7-b98c-7273ffe5cbbc%28Office.15%29.aspx)中返回的值的条目 ID。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)

